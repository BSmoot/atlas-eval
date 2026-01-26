# Extracted AI & Technology Insights

**Source:** Notes from Jul 2025 - Jan 2026 (AI SteerCo, AI Innovation, Tech Underlayment, AI Enabled Sales, AI Bricks)
**Extracted:** 2026-01-23

---

## AI Organizational Structure

### AI Steering Committee
- **Membership:** 81 participants in broader program; SteerCo is executive governance
- **Mission:** Empower employees, operationalize efficiency and innovation, culture of enablement/experimentation
- **Cadence:** ~Monthly (notes from Sep 22, Oct 27, Nov 24)

### AI Center of Excellence (CoE)
- **Role:** Underpinnings, alignment with broader goals, funding/tools/resources, decision making
- **Key functions:**
  - Shaping GPT workspace administration
  - Guidance and governance
  - Incubation and exploration
  - Documentation and facilitation to results
  - History storage, anonymization, data descriptions

### AI Innovation Team (Jan 2026 - "AI Bricks")
- **Members:** Ben (business), Ali (engineering), Jade (product)
- **Charter principle:** "We're here to prove what's possible in 2026, not theorize about it"
- **Operating model:** Build at pace rest of business can't yet sustain
- **Key quotes:**
  - "EVERY tokenizable step will be reviewed for AI/tech augmentation or overhaul"
  - "Not looking at existing process asking where AI can help. Looking at AI and asking where we cannot or should not apply this"
  - "Code is free. Our context, documentation, approach, knowledge, and data sources are the difference"
  - "10x = 30 person team equivalent. 5x = 15 person team"

---

## IRIS Platform (Internal AI System)

### Architecture (from 250923_AI Tech Underlayment)
- **IRIS** = LLM-based system with context and access to agents
- **Interface:** Teams app/bot, can also use portal or applets
- **Foundation:** AWS Bedrock for models
- **Key components:**
  - Agents/Tools: internet, catalog, knowledge base, SQL, documents
  - API + MCP integration
  - Catalog/semantic layer connected to data warehouse
  - Langfuse for monitoring (latency, token usage, cost, scoring)

### Agent Architecture Principles
- No fixed pipelines — model chooses which agent to use
- Agents are modules: Tools + Models + Instructions (Prompts)
- More jobs you give to model = less accurate; reason over one specific task
- End user doesn't write prompts — team tests, experiments, controls
- Agents can expose REST APIs or capabilities to IRIS
- Self-learning: agents fix errors and persist corrections

### Data Layer
- Semantic layer between raw data and agents (not just SQL)
- Business descriptions of tables/columns as catalog
- Performance, fiscal year, etc. defined as concepts
- 7k of 60k docs currently fed to AI (growth opportunity)

### IRIS Capabilities (current)
- Read-only access to Salesforce data
- HR chatbot (errors fixed, tuning for deterministic answers)
- Instant inventory (quote parsing based)
- Knowledge base Q&A (SOPs, Stackwise)
- SQL generation against data warehouse

---

## AI-Enabled Sales Vision (from 251023 - detailed blueprint)

### Two Strategic Pillars

**Pillar 1: Customer Intelligence Platform**
- Pattern recognition and predictive analytics on procurement histories
- Cross-sell/upsell and new logo acquisition
- 80M transactions as knowledge base

**Pillar 2: Sales Enablement Intelligence**
- Accelerate deal velocity and conversion rates
- Reduce manual research burden on 220+ person org
- Position UPSTACK as industry-leading advisor

### Seven Capability Areas

1. **Intelligent Intake** — AI extracts needs from natural language, matches to 80M transaction DB
2. **Continuous Supplier Intelligence Engine** — Web monitoring, structured extraction, comparative analysis, advisor alerts
3. **Context-Aware Solution Design** — Filter 100+ suppliers to 5-8 viable, rank, flag risks, generate comparison
4. **Automated Supplier Engagement** — RFP generation, response processing, negotiation support
5. **Implementation Risk Prediction** — Timeline patterns, failure indicators, risk assessment from historical data
6. **Autonomous Execution Services** — Tier 1 full automation (80% of tickets), Tier 2 AI-assisted, Tier 3 proactive detection
7. **Renewal Intelligence & Expansion** — 6-month, 3-month, at-renewal AI analysis and proposal generation

### Key Metrics Targets
- 50-70% time savings on RFP/proposal generation
- 40-65% ticket deflection on L1/L2 routing
- 5-6X time leverage on solution design (8-12 hrs → 1-2 hrs)
- 12-18% churn reduction from renewal prediction
- 1 service delivery person: 50-100 customers → 500-1,000 customers

### Competitive Moat
- "Suppliers only know their own products. Enterprise buyers only research 3-5 suppliers. You know everything about everyone, updated daily."

---

## AI Innovation Team Principles (Jan 2026)

### Operating Philosophy
1. Every tokenizable step reviewed for AI augmentation or overhaul
2. Output integrates into existing systems — proving what's possible by testing infrastructure edges
3. Document with eye to explaining to non-technical users
4. Provide "building block" solutions that work across multiple scenarios/teams
5. Building a platform, not individual point solutions

### Evaluation Framework
- Intent/Context/Spec/Execution loops
- Quantitative score + intent misalignment check
- Subjective but structured evaluation
- Traceability of decisions and outcomes
- Confidence scores on agent outputs
- Agents building agents (meta-capability)

### Process
- Shift-left security reviews (early)
- Common infrastructure patterns for front/back-end
- Best practices REQUIRED — not optional
- Get it into GitHub → run against controls
- Be thoughtful about libraries (well maintained, supported, widely used)

### Innovation → Delivery Pipeline
- Idea → Concept → Prioritization → Delivery
- Collection of capabilities → break into components → architecture → working code
- Innovation program becomes a delivery team (Ali's team)
- Tickets, quality control, testing required

---

## AI Proof of Concepts (from 251022)

### Salesforce MCP Integration
- SFDC working on MCP as an offering (beta)
- Agents able to run flows/emails/actions via MCP possible Q1 2026
- Hosted MCP server: Claude Desktop pointing to SFDC server
- IRIS can already do read-only study via SQL
- Agent could choose SQL vs MCP based on task

### Key Architecture Decision
- Direct PostgreSQL: low latency, no limits, no additional cost
- MCP: more capabilities but adds complexity
- **Resolution:** Agent exposes functionality, agent chooses where to go

### Business Assistant Requirements
1. Semantic knowledge
2. Feedback on outcome

### Insight Curation Model
- Business owner makes decisions on relevance
- Curation of INSIGHTS instead of raw data
- Contradictory info handling: teach agents how to resolve differences
- Preference to source types, newer sources, etc.
- Humans facilitate through curation and qualifying

---

## Tech Platform Decisions

### Tools/Platforms in Play
| Tool | Purpose | Status |
|------|---------|--------|
| IRIS | Internal AI assistant | Production |
| Dataiku | Data science/LLM Mesh | Training/eval |
| Langfuse | LLM observability | Production |
| Lumopath | Analytics? | Evaluation |
| Gong | Conversation intelligence | Evaluation |
| HubSpot | Marketing automation | Evaluation |
| Marketo | Marketing automation | Evaluation |
| AWS Bedrock | Model hosting | Production |
| MCP/Claude | Agent framework | Active exploration |

### Security & Governance
- Prompt security review conducted (250820)
- BCP tabletop exercises (Jul, Oct)
- Data protection vs. encouraging use tension acknowledged
- Shift-left security for AI development
- PII data points tracked
- Engineering AI team and CoE team sharing capabilities

---

## Key Open Questions (from notes)

1. Who manages the agent? AI management in hands of business unit vs. tech team
2. How to handle model shifts (testing approach when models change)
3. Data protection vs. encouraging use — where's the line?
4. Off-the-shelf agent composition tool vs. custom build?
5. Full platform capability vs. critical adoption of what exists?
6. How much data governance maturity required at this stage?
7. Engineering AI team vs. CoE team boundaries
