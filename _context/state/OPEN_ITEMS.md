# Open Items

**Status:** Active
**Last Updated:** 2026-01-25

---

## Open

### OI-004 - IRIS integration approach
**Status:** Open
**Priority:** P2
**Blocking:** Semantic query capability

IRIS provides semantic queries against internal data sources. Define:
- How this system interacts with IRIS
- Whether to replicate data or query on-demand
- Authentication/access pattern

---

### OI-006 - Define initial personal work strands
**Status:** In Progress
**Priority:** P1
**Blocking:** Personal execution tracking

**First strand created:** Use Case Synthesis (WS-001)
- Building blocks manifest complete
- Gap analysis complete
- Use case mapping framework established

**Deliverables:**
- `_context/project/BUILDING_BLOCKS_MANIFEST.md` — Full platform capability inventory
- `_context/initiatives/personal-execution/strands/use-case-synthesis.md` — Active work strand

**Remaining:**
- Identify additional active work strands
- Create strand files for each

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
