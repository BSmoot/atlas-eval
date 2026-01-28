# Open Items

**Status:** Active
**Last Updated:** 2026-01-28

---

## Open

### OI-004 - IRIS integration approach
**Status:** Deferred
**Priority:** P3
**Blocking:** Semantic query capability
**Deferred:** 2026-01-28 (not a priority right now)

IRIS provides semantic queries against internal data sources. Define:
- How this system interacts with IRIS
- Whether to replicate data or query on-demand
- Authentication/access pattern

---

### OI-006 - Define initial personal work strands
**Status:** In Progress
**Priority:** P1
**Blocking:** Personal execution tracking

**Active Strands:**

| ID | Strand | Status |
|----|--------|--------|
| WS-001 | AI Exploration | Active |
| WS-002 | Vision Alignment & Transformation Readiness | Active |
| WS-003 | Program Stewardship | Active |
| WS-004 | Strategic Positioning | Active |
| WS-005 | Context Management | Active |
| WS-006 | Agentic Organization | Active |
| WS-007 | Revenue Engine | Active |
| WS-008 | Strategic Insights | Active |
| WS-009 | Investor Alignment | Active |

**WS-001 - AI Exploration**
- Expanded scope: prove what's possible, give business access, accelerate change, create leverage, define human-AI collaboration
- Workstreams: Use Case Synthesis, Capability Access, Proof Points, Human-AI Collaboration Model
- Building blocks manifest and gap analysis complete

**WS-002 - Vision Alignment & Transformation Readiness**
- Strand file created
- 9 workstreams defined
- Ready for execution

**WS-003 - Program Stewardship**
- Strand file created
- Covers: monitoring, guidance, questioning, resourcing, unblocking, coordinating
- Spans all 6 strategic programs

**WS-004 - Strategic Positioning**
- Strand file created
- Audiences: investors, internal, customers
- Themes: investment impact, leverage, augment/automate/rewrite, offerings as products

**WS-005 - Context Management**
- Strand file created
- Shared context layer for humans and AI
- Workstreams: canonical context, specific context, intent→outcome, metrics alignment, tracking, collaboration, traceability, feedback, human-AI review

**WS-006 - Agentic Organization**
- Strand file created
- Mirror org structure with agent teams
- Context Ops team supports all agents (and by proxy, the business)
- Tests WS-005 context, surfaces gaps, spawns dynamic agents

**WS-007 - Revenue Engine**
- Strand file created
- Repeatability, predictability, programmatic revenue growth
- CRO hire, marketing/sales enablement maturity, systems, goal alignment
- Insights → action → insights continuous improvement loop

**WS-008 - Strategic Insights**
- Strand file created
- Four pillars: demand/selling, optimized investment, retention, metrics that matter
- Key partner: Dan Corning
- Gated by data accuracy; feeds WS-007 Revenue Engine

**WS-009 - Investor Alignment**
- Strand file created
- Alignment stack: daily ops → weekly → monthly → board → investor story
- Board decks as investor pitch practice
- Defensible numbers, digestible narrative

**Deliverables:**
- `_context/project/BUILDING_BLOCKS_MANIFEST.md` — Full platform capability inventory
- `_context/initiatives/personal-execution/strands/use-case-synthesis.md` — WS-001
- `_context/initiatives/personal-execution/strands/vision-alignment.md` — WS-002
- `_context/initiatives/personal-execution/strands/program-stewardship.md` — WS-003
- `_context/initiatives/personal-execution/strands/strategic-positioning.md` — WS-004
- `_context/initiatives/personal-execution/strands/context-management.md` — WS-005
- `_context/initiatives/personal-execution/strands/agentic-org.md` — WS-006
- `_context/initiatives/personal-execution/strands/revenue-engine.md` — WS-007
- `_context/initiatives/personal-execution/strands/strategic-insights.md` — WS-008
- `_context/initiatives/personal-execution/strands/investor-alignment.md` — WS-009

**Remaining:**
- Execute work strands
- Identify additional work strands if needed

---

## Complete

### OI-003 - Existing notes import strategy
**Status:** Complete
**Priority:** P1
**Resolved:** 2026-01-23

**Resolution:** Notes indexed and key insights extracted. Strategy: reference in place (not copy), with structured extractions for high-value content.

**Deliverables:**
- `_context/project/NOTES_INDEX.md` — Searchable index of 367 notes (Jul 2025 - Jan 2026 + AI Explorations)
- `_context/project/notes/extracted/STRATEGIC_THEMES.md` — Decisions, action items, themes from leadership/strategy notes
- `_context/project/notes/extracted/AI_STRATEGY_INSIGHTS.md` — AI architecture, IRIS platform, AI-enabled sales vision
- `_context/project/notes/extracted/AI_EXPLORATIONS_SUMMARY.md` — Summary of 16 employee AI interviews + findings

**Approach:** Index-in-place + targeted extraction. 1:1 notes remain reference-only (findable via index). Original notes untouched in OneDrive.

---

### OI-005 - Populate 6 strategic initiative charters
**Status:** Complete
**Priority:** P1
**Resolved:** 2026-01-23

**Resolution:** All 6 initiative charters populated from 2026 strategic plan documents. Cornerstones 00-04 imported. Manifest updated with initiative names and owners.

**Content imported:**
- Programs 01-05: Full charters with purpose, scope, OKRs, projects, teams, dependencies, quarterly arcs
- Program 06: Reserved slot structure for Gateway initiatives
- Cornerstones 00-04: Why We're Here, Strategic Context, Program Architecture, Operating Principles, Key Entities

---

### OI-001 - Atlas-workcore access
**Status:** Complete
**Priority:** P1
**Resolved:** 2026-01-21

**Resolution:** Submodule URL corrected from relative `../atlas-workcore` to `https://github.com/BSmoot/atlas-core.git`. Submodule now properly initialized at `atlas-workcore/` pointing to latest main branch (commit `2a0cf2f`).

**Key insight:** The repo was renamed from atlas-workcore to atlas-core. Submodule path kept as `atlas-workcore/` to maintain CLAUDE.md reference compatibility. Direct clone at `atlas-core/` can be removed if desired (no longer needed).

**Verified:** `atlas-workcore/project-steward/CLAUDE.md` and `atlas-workcore/project-steward/_context/atlas/` now accessible.
