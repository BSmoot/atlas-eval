# Work Strand: Use Case Synthesis

**ID:** WS-001
**Status:** Active
**Created:** 2026-01-25
**Owner:** Ben Smoot

---

## Purpose

Synthesize findings across AI use cases in the context of UPSTACK's existing and near-future agentic, data, and web-application capabilities to create a composable "building blocks" platform for embedded AI agents.

---

## Scope

### In Scope
- Catalog all existing building blocks (joe, bricks, upstack_web)
- Identify capability gaps (RBAC, semantic layer, integrations)
- Create use case → building blocks mapping framework
- Design guardrails for safe self-service agent creation
- Map employee-surfaced use cases to platform capabilities

### Out of Scope (for now)
- Implementation of gap closures
- Building new agents
- Production deployment changes

---

## Key Deliverables

| Deliverable | Status | Location |
|-------------|--------|----------|
| Building Blocks Manifest | Complete | `_context/project/BUILDING_BLOCKS_MANIFEST.md` |
| Gap Analysis | Complete (in manifest) | Section: "IDENTIFIED GAPS" |
| Use Case Mapping Framework | Complete (in manifest) | Section: "USE CASE MAPPING STRATEGY" |
| Use Case → Blocks Matrix | Pending | TBD |
| Guardrails Framework | Started (in manifest) | Needs expansion |

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

## Building Blocks Summary

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

## Use Cases Awaiting Mapping

From AI Explorations interviews:

| Use Case | Priority | Likely Blocks |
|----------|----------|---------------|
| QBR Report Generation | High | sql, kb/docs, flows, pdf |
| Supplier Registration Lookup | High | kb/docs, flows, internet |
| Mobility Data Cleanup | Medium | sql, python, flows |
| Contact Extraction from Email | Medium | (gap: email access) |
| Vendor Comparison Tool | High | internet, sql, flows |
| Customer Benchmarking | Medium | sql, kb/docs, flows |

---

## Next Actions

- [ ] Create detailed use case → building blocks matrix
- [ ] Expand guardrails framework into separate document
- [ ] Map Program 2/4/6 initiatives to building blocks
- [ ] Identify minimum viable RBAC for safe experimentation
- [ ] Document composition patterns for common use cases

---

## Notes

- "Code is free. Our context, documentation, approach, knowledge, and data sources are the difference" — AI Innovation Team charter
- Platform vision: building blocks that can be arranged/rearranged with guardrails for user-created agent workers
- Key principle: agents building agents (meta-capability)

---

*Last Updated: 2026-01-25*
