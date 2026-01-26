# Direct Report Findings: Nick (Nick B / Nick Besch)

**Role:** VP/Director Engineering — Application, Infrastructure, Security
**Period:** July 2025 - January 2026
**Notes reviewed:** 29 files
**Last meeting:** January 22, 2026

---

## Role & Responsibilities

Nick owns/manages:
- **Engineering team** — Application development, IRIS agents, portal
- **Infrastructure** — AWS, PostgreSQL, OLAP, compute/storage
- **Security** — RBAC, SSO/MFA, OWASP, secure coding, BCP/DR
- **AI platform engineering** — Agent architecture, Bedrock integration, LLM optimization
- **DevOps & QA** — CI/CD, testing, prototype environments
- **Contractor teams** — defmethod (Portugal), previously Kickdrum/Brainblend
- **Data engineering** (shared) — Pipelines, transformations, data mart

---

## Key Themes (Jul 2025 - Jan 2026)

### 1. IRIS Agent Architecture
Central technical ownership of IRIS platform:
- Tool-oriented approach: "Model has access to tools and decides how to solve the problem"
- Not rigid orchestration — "exposing tools in the right way is critical"
- One repo for IRIS, agents in directories
- Bedrock with failover to DeepInfra
- "What we have now is not complicated. Orchestration and choreography not needed."
- Collecting prompt, instruction, and context as the key design pattern
- Flexible architecture: agent sees tools as tools, assistant sees agents as tools

### 2. Semantic Layer Development
Major initiative across Oct-Jan:
- Evaluating cube.dev, Terragonia approach
- Globally define metrics/columns/reports
- Flows into Tableau and other systems
- "Removing key person risk" in how reporting is derived
- Business definitions, personas, domain knowledge → store → context for queries
- "Last piece of AI system" — enables agent-driven analytics

### 3. Infrastructure & Scaling
- **OLAP pain point:** Growing as more people/systems query
  - PostgreSQL hitting limits — "can only scale so far"
  - Snowflake PoC proposed (vs. Redshift, Databricks)
  - Need to separate compute and storage
  - Threshold for migration to be defined
- **gp3 migration** — storage optimization
- **IO contention** — optimized what's possible, continuing
- **Lambda limitations** — can't run locally; prototype environment needed

### 4. Security & Governance
- Coding standards and secure coding training (OWASP courses)
- System Design Security Review (OWASP ASVS 5.0)
- Linting system (deterministic) + AI reviewer
- RBAC implementation — getting off Okta (costly), moving to Entra
- Person-session auth for AI tools
- External auth being "chipped away at"
- BCP tabletop exercises

### 5. Development Environment & Process
Designed clear dev workflow (Jan 2026):
- Prototype environment: branch with prototyping prefix → push to GitHub → deploys to prototype env in AWS
- Production path: prototype → dev → QA → production
- Dev = peer reviewed, tested, built via automation
- Sandbox vs. prototype distinction: security oversight, no production impact
- .env management via 1Password
- Local dev: Copilot with VS Code; Mike and Ali using Claude API keys

### 6. Email Ingestion Pipeline
- Green-lit (Nov 2025)
- Mike investigating integration piece with Darrell
- Recommendation by end of sprint
- Permissions and connectivity setup needed
- Would feed into knowledge layer / semantic layer

---

## Decisions Made

1. **Agent architecture:** Tool-oriented, not orchestration-based — model decides
2. **Auth direction:** Entra over Okta (cost-driven, "just a question of when")
3. **Email ingestion:** Approved and in progress
4. **Brainblend:** Cut ties; defmethod (Portugal) is preferred partner
5. **Kickdrum:** "Maybe — still around but bad fit with proposal"
6. **Prototype environment:** Branch-based deployment to AWS for testing
7. **SFDC MCP:** In beta, Postgres as source of truth is longer-term option

---

## Action Items (Open)

- Snowflake PoC: scope and timeline for OLAP evaluation
- Semantic layer eval finalization (cube.dev)
- Email ingestion pipeline: tool procurement, pipeline setup
- Secure coding training rollout (OWASP courses for team)
- RBAC completion — external auth migration
- Define OLAP threshold for when PostgreSQL no longer sufficient
- Patrick stepping up on application stack (team development)
- Thomas on data platform support
- Bedrock throttling resolution
- Token efficiency / LLM cost optimization

---

## Performance & Development

### Strengths (from Aug 2025 Reflection by BS)
- "Consistently reliable deliverer with strong methodical planning and management capabilities"
- "Systematic approach to work demonstrates the technical depth we value"
- Strong understanding of the full technology stack
- Ability to architect flexible, pragmatic solutions

### Development Areas (from Aug 2025 Reflection)
- **Transition from operational to strategic:** "I tend to like to have some involvement [in ops]... I do not have a good balance here — largely because of necessity"
- **Wants to scale out:** testing, database administration, DevOps — via staff augmentation
- **Creative contribution:** "As much opportunity in driving ideas and creativity from the tech side as there is the product side"
- **Cross-org understanding:** "Lingering divide in understanding between [tech and agency] has been a source of frustration"

### Guidance Given (Aug 2025)
- "Transition from heavy operational support to participating in strategic thinking"
- "Driving more creative, forward-thinking technology solutions that anticipate business needs"
- Help convey the "why" of tech investment to other groups
- "Operating review with key stakeholders — what we're delivering, why, where we're at"
- Technology roadmap review — make time to architect

### Team
- Patrick stepping up on application stack
- Thomas supporting data work
- Mike and Ali on AI/innovation
- defmethod (Portugal - Sergio/Carlos) as senior dev contractors

---

## Relationships & Dynamics

- **With Anders:** Primary relationship — 15+ joint meetings; architecture, security, roadmap
- **With Darrell:** IT/Security partnership; email ingestion coordination
- **With Mike/Ali:** AI engineering team collaboration
- **With Product:** Tension — "not enough trust, transparency" (org-wide issue)
- **With business teams:** Gap identified — wants to help bridge tech/agency divide

---

## Open Threads

1. OLAP scaling: Snowflake PoC timing and approach
2. Semantic layer: tool selection and stakeholder workflow design
3. Email ingestion: pipeline buildout
4. RBAC: Okta → Entra migration timeline
5. Innovation team contribution: enabling tech team to drive ideas into product
6. Staff augmentation: scaling testing/DevOps/DB admin
7. LLM cost management: token efficiency, model selection (haiku 4.5 test?)
8. MLP features: 3 categories identified, postgres and dynamodb as backends
9. SharePoint integration: "already underway"
