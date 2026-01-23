# Open Items

**Status:** Active
**Last Updated:** 2026-01-23

---

## Open

### OI-002 - Security review for GitHub backup
**Status:** Open
**Priority:** P2
**Blocking:** Long-term backup strategy

Current plan: Local git + cloud-sync'd folder to SharePoint.
Pending: Security team review of GitHub backup option.

---

### OI-003 - Existing notes import strategy
**Status:** Open
**Priority:** P1
**Blocking:** Initial system population

Need to define:
- Import process for existing `.txt` notes (yymmdd_<topic> format)
- Import process for existing Obsidian `.md` notes
- Deduplication/organization approach
- Whether to copy or reference SharePoint content

---

### OI-004 - IRIS integration approach
**Status:** Open
**Priority:** P2
**Blocking:** Semantic query capability

IRIS provides semantic queries against internal data sources. Define:
- How this system interacts with IRIS
- Whether to replicate data or query on-demand
- Authentication/access pattern

---

---

### OI-006 - Define initial personal work strands
**Status:** Open
**Priority:** P1
**Blocking:** Personal execution tracking

Need to:
- Identify current active work strands
- Create strand files in `initiatives/personal-execution/strands/`
- Capture current status and next actions for each

---

## Complete

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
