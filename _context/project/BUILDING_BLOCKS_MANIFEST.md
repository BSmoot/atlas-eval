# Embedded Agentic Platform - Building Blocks Manifest

**Status:** Active Reference Document
**Created:** 2026-01-25
**Sources:** joe, bricks, upstack_web codebases + AI Strategy notes

---

## Executive Summary

UPSTACK has three interconnected systems that together form the foundation of an embedded agentic platform:

| System | Purpose | Maturity |
|--------|---------|----------|
| **Joe** | Agentic service platform (agents, flows, MCP, Teams) | Production |
| **Bricks** | Agent Builder infrastructure (auth, hosting, deployment) | Foundation Complete |
| **upstack_web** | Client Portal (user-facing, admin, inventory) | Production |

This manifest catalogs all available building blocks and identifies gaps for the platform vision.

---

## 1. AGENTS (Specialized AI Modules)

### Currently Available in Joe

| Agent | Purpose | Data Access | Status |
|-------|---------|-------------|--------|
| `sql` | Natural language → SQL, execute queries, visualizations | PostgreSQL (warehouse) | Production |
| `catalog` | Schema discovery, data quality assessment, annotation | PostgreSQL metadata | Production |
| `kb/docs` | Document repository, ingestion, retrieval, summarization | S3, DynamoDB | Production |
| `kb/guard` | Content moderation, security filtering | - | Production |
| `kb/supplier` | Supplier documentation, knowledge base | S3, DynamoDB | Production |
| `kb/hr` | HR document processing, summarization | S3 | Production |
| `internet` | Web search (`search_web`), webpage loading (`load_webpage`) | External web | Production |
| `pdf` | PDF document processing, content extraction | S3, Tesseract Lambda | Production |
| `feedback` | System feedback collection for improvement | DynamoDB | Production |
| `utils` | Utility functions (date/time, etc.) | - | Production |
| `weather` | Weather information and forecasts | External API | Production |
| `python` | Sandboxed Python code execution | Isolated | Production |
| `mcp` | MCP server interactions | MCP Protocol | Production |
| `customer` | Customer context and intelligence | Salesforce (read) | Beta |
| `flows` | Workflow orchestration agent | All (via steps) | Production |

### Agent Architecture Principles (from IRIS design)

- No fixed pipelines — model chooses which agent to use
- Agents = Tools + Models + Instructions (Prompts)
- One specific task per agent = higher accuracy
- End users don't write prompts — team tests, experiments, controls
- Agents can expose REST APIs or capabilities to IRIS
- Self-learning: agents fix errors and persist corrections

---

## 2. INSTRUCTION PROMPTS

### Prompt Architecture

| Location | Purpose | Format |
|----------|---------|--------|
| `joe/service/agents/*/prompts/*.md` | Agent system prompts | Markdown |
| `joe/service/agents/flows/AGENT_CAPABILITY.md` | Flow agent capability spec | Markdown |
| `joe/service/agents/document/prompt/*.md` | Document parsing prompts | Markdown |
| `joe/service/agents/catalog/prompts/*.md` | Catalog annotation prompts | Markdown |

### Prompt Templates Available

- **SQL Generation**: Natural language → SQL with schema context
- **Document Classification**: `classify.md` - document type detection
- **Document Parsing**: `parse.md` - structured extraction
- **Catalog Annotation**: `usage.md` - table/column descriptions
- **Flow Clarification**: `clarify.md` - user intent disambiguation

### Model Configuration

Environment variable override pattern for per-feature model selection:
```
DEFAULT_MODEL_ASSISTANT="claude_4_sonnet_v2_br"
DEFAULT_MODEL_ANNOTATION="claude_4_sonnet_v2_br"
DEFAULT_MODEL_AGENT_INTERNET="claude_4_sonnet_v2_br"
DEFAULT_MODEL_AGENT_KB_DOCS="claude_4_sonnet_v2_br"
DEFAULT_MODEL_AGENT_SQL="claude_4_sonnet_v2_br"
DEFAULT_DOCUMENT_MODEL="claude_4_5_sonnet_v2_br"
```

---

## 3. SHARED CONTEXT

### Knowledge Base System

| Component | Storage | Capabilities |
|-----------|---------|--------------|
| Document Collections | S3 + DynamoDB | Upload, ingest, retrieve, summarize |
| Supplier Knowledge | S3 + DynamoDB | Supplier documentation, metadata |
| Data Catalog | PostgreSQL | Schema, table, column annotations |
| Semantic Annotations | DynamoDB | Business descriptions, relationships |

### Catalog/Semantic Layer

**Current State:**
- Schema discovery via `catalog` agent
- Annotation system for tables/columns
- Quality scoring per table/column
- Business descriptions as catalog entries
- 7k of 60k docs currently fed to AI

**Architecture:**
- Semantic layer between raw data and agents (not just SQL)
- Business descriptions of tables/columns
- Performance, fiscal year, etc. defined as concepts

### Session/Memory

| System | Memory Type | Duration |
|--------|-------------|----------|
| Joe Teams Bot | Conversation context | Session |
| Joe Chat | Session-based | Session |
| MCP Protocol | Session manager (DynamoDB) | Configurable |
| Flow Execution | Step outputs (S3) | Persistent |

---

## 4. PROMPT IMPROVEMENT & EVALUATION

### Feedback System

- `feedback` agent collects system limitations/knowledge gaps
- Agents report when they encounter errors
- Human feedback collection via API

### Observability (Langfuse)

| Metric | Available |
|--------|-----------|
| Latency tracking | Yes |
| Token usage | Yes |
| Cost tracking | Yes |
| Trace/span hierarchy | Yes |
| LLM generation logging | Yes |

### Quality Scoring

- Catalog quality scores per table/column
- Document processing status tracking
- Flow execution status and error tracking

---

## 5. TOOLS (Function Definitions)

### SQL Agent Tools
- `execute_query` - Run SQL against warehouse
- `get_available_tables` - List accessible tables
- `get_table_details` - Schema information
- `create_visualization` - Charts from query results

### Internet Agent Tools
- `search_web` - Web search (query, num_results)
- `load_webpage` - Extract webpage content (url, max_length)

### Python Agent Tools
- `execute_python` - Sandboxed code execution (code, input_data, timeout)
- Available modules: json, math, datetime, re, collections, itertools, statistics
- Security: No file I/O, no network, timeout enforced

### KB/Docs Agent Tools
- `search` - Document search
- `upload` - Document upload
- `get_document` - Document retrieval

### Utils Agent Tools
- `get_date_and_time` - Current timestamp

### Flow Agent Tools
- Flow management (create, list, update, delete)
- Execution control (execute, status, logs)
- Catalog discovery for flow building

---

## 6. SKILLS (Higher-Order Capabilities)

### Document Intelligence
- OCR processing (Tesseract Lambda)
- PDF analysis with page-level extraction
- Multi-method document processing:
  - Direct text extraction
  - Tabular data with structure preservation
  - OCR for scanned documents
  - Vision-based analysis (multi-modal models)

### Data Analysis
- Natural language to SQL
- Schema understanding
- Query visualization
- Data quality assessment

### Workflow Automation (Flows)
- Step types: tool, agent, conditional, parallel, flow_composition, api_call
- Dependency resolution (topological sort)
- Parallel execution (static & dynamic)
- Scheduling (cron-based via EventBridge)

---

## 7. ORCHESTRATION

### Flow Execution Engine

```
joe/service/agents/flows/
├── agent.py          # Conversational design agent
├── executor.py       # Orchestration engine
├── validator.py      # Flow validation
├── storage.py        # DynamoDB + S3 persistence
├── chat_session.py   # Chat-based flow building
└── steps/
    ├── base.py       # Base executor
    ├── tool.py       # Tool step execution
    ├── agent.py      # Agent step execution
    ├── conditional.py # Branching logic
    ├── parallel.py   # Static & dynamic parallelism
    └── factory.py    # Step creation
```

### Step Types

| Type | Purpose | AI Involved |
|------|---------|-------------|
| `tool` | Execute specific tool with known params | No |
| `agent` | AI decides which tools to call | Yes |
| `conditional` | If/else branching | No |
| `parallel` | Concurrent execution (static/dynamic) | No |
| `flow_composition` | Call another flow | No |
| `api_call` | External HTTP requests | No |

### Orchestration Features
- Dependency graph resolution
- Execution locking (prevent concurrent runs)
- State persistence across steps
- Error handling strategies (fail/continue/retry)
- Step output chaining
- Template variable substitution

### Scheduling
- Cron-based expressions
- EventBridge trigger (hourly)
- DynamoDB schedule storage
- UTC timezone

---

## 8. MCP (Model Context Protocol)

### Server Implementation

**Location:** `joe/service/mcp_protocol/`

| Component | Purpose |
|-----------|---------|
| `protocol/mcp.py` | Lambda MCP server class |
| `protocol/types.py` | MCP type definitions |
| `protocol/session.py` | Session manager (DynamoDB) |

### MCP Capabilities
- Streamable HTTP transport
- Tool registration via decorator
- Session management with expiry
- JSON-RPC 2.0 protocol
- MCP Version 0.6

### MCP in Context
- Salesforce working on MCP as offering (beta Q1 2026)
- Agent can choose SQL vs MCP based on task
- IRIS can already do read-only via SQL

---

## 9. WEB INTERFACE

### Joe Web Apps

| App | Location | Purpose |
|-----|----------|---------|
| KB Interface | `joe/service/www/kb/` | Knowledge base, catalog, supplier, flows |
| Chat Interface | `joe/service/www/chat/` | Joe Assistant, Prompt Tester |
| Typewriter | `joe/service/www/typewriter/` | Document parser testing |

### KB Interface Features
- Token-based authentication
- Document upload/processing
- Real-time status updates
- Material-UI design
- Flow builder with visual graph
- Execution monitoring

### Bricks Web App

| Tech | Purpose |
|------|---------|
| React 19 + TypeScript | Frontend framework |
| Vite | Build tool |
| MSAL | Microsoft authentication |

### upstack_web Portal

| Feature | Description |
|---------|-------------|
| Inventory management | Customer asset tracking |
| Order management | Order workflow |
| Case management | Support tickets |
| Admin pages | Users, teams, accounts |
| Datadog integration | Logging, RUM |
| Pendo integration | User analytics |

---

## 10. TEAMS INTERFACE

### Microsoft Teams Bot

**Location:** `joe/service/teams/`

| Component | Purpose |
|-----------|---------|
| Bot Framework integration | Conversational AI in Teams |
| Natural language access | All Joe agents via chat |
| Rich card responses | Interactive elements |

### Configuration
- Teams Developer Portal app configuration
- Azure Bot Service registration
- Local testing via ngrok

---

## 11. SALESFORCE INTERFACE

### Current Capabilities
- Read-only access via SQL (direct PostgreSQL)
- Salesforce enrichment for documents
- Customer/supplier lookup and linking

### Integration Points
- `joe/service/clients/salesforce.py` - SF client
- `joe/service/agents/catalog/salesforce_enrichment.py`
- Document linking (supplier, customer, products, locations)

### Roadmap
- MCP integration when SF releases (Q1 2026)
- Agent could run flows/emails/actions via MCP
- Write capabilities via MCP

---

## 12. DATA PLATFORM INTEGRATION

### Current Data Stores

| Store | Purpose | Access Method |
|-------|---------|---------------|
| PostgreSQL | Data warehouse, Salesforce replica | Direct SQL |
| DynamoDB | Session, flow, execution data | AWS SDK |
| S3 | Documents, flow artifacts, logs | AWS SDK |

### Database Clients
- `joe/service/clients/ddb.py` - DynamoDB operations
- `joe/service/clients/psql.py` - PostgreSQL operations
- `joe/service/clients/salesforce.py` - SF operations
- `joe/service/clients/secrets.py` - Secrets Manager

### Semantic Layer (Current)
- Catalog agent for schema discovery
- Business annotations per table/column
- Quality scoring
- Relationship mapping (limited)

---

## 13. SHAREPOINT & SALESFORCE ACCESS

### Current State

| System | Access | Capabilities |
|--------|--------|--------------|
| Salesforce | Read-only via SQL | Customer, supplier, account data |
| SharePoint | Not integrated | - |

### SharePoint Gap
- No current integration
- Would require Microsoft Graph API
- Consider for knowledge base expansion

---

## 14. AUTHENTICATION & RBAC

### Current Authentication

| System | Method | Provider |
|--------|--------|----------|
| Joe | Token-based | Custom (DynamoDB) |
| Bricks | JWT/MSAL | Microsoft Entra ID |
| upstack_web | Session-based | Custom |

### Bricks Auth Features
- Microsoft Entra ID integration
- Domain allowlist (upstack.com)
- JWKS caching (6 hours)
- Multi-tenant or single-tenant modes

### RBAC Gap (Critical)
**Current State:** Limited role-based access
- Joe: Basic auth, no granular permissions
- Flows: Any user can schedule any flow
- Agents: No per-agent access control

**Needed:**
- Role definitions (admin, builder, user)
- Agent-level permissions
- Flow ownership and sharing
- Data access policies
- Tenant isolation

---

## 15. OBSERVABILITY & MONITORING

### Langfuse (Joe)
- Trace hierarchy for document processing
- LLM generation tracking
- Span-level operation logging
- Environment tagging
- Cost tracking

### Datadog (upstack_web)
- Application logging
- Real User Monitoring (RUM)
- Session tracking

### CloudWatch (All)
- Lambda function logs
- Application metrics
- Performance monitoring

---

## 16. LLM PROVIDER SUPPORT

### Multi-Provider Architecture

| Provider | Models Available |
|----------|-----------------|
| **AWS Bedrock** | Claude 4/4.5 Sonnet, Claude 3.5 Haiku, Llama 3.3 70B, Amazon Nova (Micro/Lite/Pro), DeepSeek R1 |
| **DeepInfra** | Llama 3.3 70B Instruct Turbo, DeepSeek R1 Distill, Qwen3 235B, Phi-4 Multimodal |
| **Local** | MiniCPM-O-2.6, custom local support |

### Features
- Unified interface across providers
- Automatic tool format conversion (OpenAI ↔ Bedrock)
- Per-feature model configuration

---

## IDENTIFIED GAPS

### Critical Gaps

| Gap | Impact | Timeline |
|-----|--------|----------|
| **RBAC** | No granular permissions, security risk | Q1-Q2 2026 |
| **Semantic Layer** | Limited relationship modeling, business glossary | Q1-Q2 2026 |
| **SharePoint** | No document access from MS ecosystem | TBD |
| **Write to Salesforce** | Read-only limits automation | Q1 2026 (via MCP) |

### Platform Gaps

| Gap | Current State | Needed |
|-----|---------------|--------|
| Agent versioning | None | Version control, rollback |
| Agent marketplace | None | Discovery, sharing, templates |
| Usage analytics | Limited | Token usage, cost allocation |
| Multi-tenant | Partial | Full tenant isolation |
| Testing framework | Ad-hoc | Automated agent testing |
| Prompt management | File-based | Version control, A/B testing |

### Integration Gaps

| Gap | Description |
|-----|-------------|
| Slack | No direct integration |
| Email automation | Limited (api_call only) |
| Calendar/scheduling | No meeting integration |
| ERP systems | No direct connection |

---

## USE CASE MAPPING STRATEGY

### Building Block Composition Model

**Concept:** Use cases are compositions of building blocks arranged with guardrails.

```
USE CASE = Agent(s) + Tools + Prompts + Orchestration + Interface + Data + Guards
```

### Example Compositions

**QBR Report Generator:**
```
Agents: sql, kb/docs
Tools: execute_query, search, create_visualization
Orchestration: flow (parallel data pulls → agent synthesis → pdf generation)
Interface: web (trigger) or scheduled
Data: warehouse + kb
Guards: data access policy, output review
```

**Supplier Intelligence:**
```
Agents: internet, catalog, sql
Tools: search_web, load_webpage, execute_query
Orchestration: flow (search → extract → enrich → store)
Interface: Teams or web
Data: external + warehouse
Guards: rate limiting, content filtering
```

### Mapping Framework

1. **Identify the Use Case** — What outcome does the user want?
2. **Decompose into Capabilities** — What agents, tools, data are needed?
3. **Design Orchestration** — What's the workflow (linear, parallel, conditional)?
4. **Select Interface** — How will users trigger/interact (web, Teams, scheduled)?
5. **Define Guards** — What constraints apply (access, rate limits, approvals)?
6. **Compose** — Arrange building blocks into a working agent

### Guardrails Framework

| Category | Examples |
|----------|----------|
| **Data Access** | Schema restrictions, row-level security |
| **Rate Limiting** | API calls, token usage, execution frequency |
| **Content Filtering** | PII detection, moderation, output review |
| **Approval Workflows** | Human-in-the-loop for critical actions |
| **Audit Logging** | All actions logged with user context |

---

## NEXT STEPS

1. **Validate this manifest** with Joe/Bricks/upstack_web teams
2. **Prioritize gap closure** (RBAC, semantic layer first)
3. **Create use case templates** for common patterns
4. **Build agent catalog** with composition guidelines
5. **Design guardrail framework** for safe self-service

---

*This manifest should be updated as capabilities evolve.*
