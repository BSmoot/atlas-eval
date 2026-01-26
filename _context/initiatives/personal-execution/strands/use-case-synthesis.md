# Work Strand: AI Exploration

**ID:** WS-001
**Status:** Active
**Created:** 2026-01-25
**Owner:** Ben Smoot

---

## Purpose

Fast-track AI exploration to prove what's possible, give the business access to AI capabilities, accelerate pace of change, create new leverage, and determine what it means to work collaboratively in the new age of AI.

---

## Objectives

| Objective | Description |
|-----------|-------------|
| Prove what's possible | Demonstrate AI capabilities through working examples |
| Give business access | Put AI tools in the hands of people who need them |
| Accelerate pace of change | Move faster than traditional project cycles allow |
| Create new leverage | Find where AI multiplies human effort |
| Define collaborative work | Establish how humans and AI work together |

---

## Workstreams

### 1. Use Case Synthesis

Synthesize findings across AI use cases to create a composable building blocks platform.

**Scope:**
- Catalog existing building blocks (joe, bricks, upstack_web)
- Identify capability gaps (RBAC, semantic layer, integrations)
- Create use case → building blocks mapping framework
- Design guardrails for safe self-service agent creation
- Map employee-surfaced use cases to platform capabilities

**Deliverables:**

| Deliverable | Status | Location |
|-------------|--------|----------|
| Building Blocks Manifest | Complete | `_context/project/BUILDING_BLOCKS_MANIFEST.md` |
| Gap Analysis | Complete | In manifest: "IDENTIFIED GAPS" |
| Use Case Mapping Framework | Complete | In manifest: "USE CASE MAPPING STRATEGY" |
| Use Case → Blocks Matrix | Pending | TBD |
| Guardrails Framework | Started | Needs expansion |

---

### 2. Capability Access

Get AI capabilities into the hands of the business.

| Element | Status | Notes |
|---------|--------|-------|
| Teams bot deployment | Exists | Natural language access to agents |
| Web interfaces | Exists | KB, Chat, Typewriter |
| Training/enablement | Pending | How to use what we have |
| Access expansion | Pending | Who else needs access |

---

### 3. Proof Points

Demonstrate what's possible through working examples.

| Proof Point | Status | Impact |
|-------------|--------|--------|
| QBR Report Generation | Pending | High - visible, repeatable |
| Supplier Registration Lookup | Pending | High - common need |
| Vendor Comparison Tool | Pending | High - decision support |
| Customer Benchmarking | Pending | Medium - strategic value |

---

### 4. Human-AI Collaboration Model

Define how humans and AI work together.

| Element | Status | Notes |
|---------|--------|-------|
| Role boundaries | Pending | What AI does vs human |
| Handoff patterns | Pending | When/how to hand off |
| Quality assurance | Pending | How humans verify AI work |
| Feedback loops | Pending | How AI learns from humans |
| Trust calibration | Pending | When to trust, when to verify |

---

## Platform Capabilities (Current State)

### Available Now
- **16 Agents** (sql, catalog, kb/docs, internet, python, flows, etc.)
- **Flow Orchestration** (parallel, conditional, scheduled)
- **MCP Protocol** (tool integration, session management)
- **Teams Bot** (natural language agent access)
- **Web Interfaces** (KB, Chat, Typewriter, Portal)
- **Multi-LLM Support** (Bedrock, DeepInfra, local)
- **Observability** (Langfuse, Datadog, CloudWatch)

### Critical Gaps
1. **RBAC** — No granular permissions system
2. **Semantic Layer** — Limited relationship modeling
3. **SharePoint** — No MS document ecosystem access
4. **Salesforce Write** — Read-only limits automation (MCP Q1)

---

## Source Materials

### Codebases Reviewed
- `joe` — Agentic service platform (agents, flows, MCP, Teams)
- `bricks` — Agent Builder infrastructure (auth, hosting, deployment)
- `upstack_web` — Client Portal (user-facing, admin, inventory)

### Context Documents
- `AI_STRATEGY_INSIGHTS.md` — IRIS architecture, AI-enabled sales vision
- `AI_EXPLORATIONS_SUMMARY.md` — 16 employee interviews, use cases surfaced

---

## Use Cases Awaiting Action

From AI Explorations interviews:

| Use Case | Priority | Likely Blocks | Status |
|----------|----------|---------------|--------|
| QBR Report Generation | High | sql, kb/docs, flows, pdf | Pending |
| Supplier Registration Lookup | High | kb/docs, flows, internet | Pending |
| Mobility Data Cleanup | Medium | sql, python, flows | Pending |
| Contact Extraction from Email | Medium | (gap: email access) | Blocked |
| Vendor Comparison Tool | High | internet, sql, flows | Pending |
| Customer Benchmarking | Medium | sql, kb/docs, flows | Pending |

---

## Next Actions

- [ ] Create detailed use case → building blocks matrix
- [ ] Expand guardrails framework into separate document
- [ ] Map Program 2/4/6 initiatives to building blocks
- [ ] Identify minimum viable RBAC for safe experimentation
- [ ] Document composition patterns for common use cases
- [ ] Select first proof point to execute
- [ ] Draft human-AI collaboration principles
- [ ] Identify next wave of business users for access

---

## Notes

- "Code is free. Our context, documentation, approach, knowledge, and data sources are the difference" — AI Innovation Team charter
- Platform vision: building blocks that can be arranged/rearranged with guardrails for user-created agent workers
- Key principle: agents building agents (meta-capability)

---

*Last Updated: 2026-01-26*
