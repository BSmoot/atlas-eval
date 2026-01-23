# Handoff: Strategic Initiative Population

**Created:** 2026-01-14
**For:** New Claude session
**Task:** Populate 6 strategic initiative charters from source documentation

---

## Context

You are working on an Atlas-aligned executive knowledge management system for the CEO of UPSTACK, a 260-person IT infrastructure channel business.

**Read these files first:**
1. `_context/project/PROJECT_CONTEXT.md` — Full project context
2. `_context/cornerstones/CORNERSTONE_UPSTACK.md` — Business context
3. `_context/state/OPEN_ITEMS.md` — See OI-005

---

## Your Task

The user will place strategic initiative documentation in one of:
- `initiatives/init-01/source/` through `initiatives/init-06/source/` (per-initiative)
- `_inbox/initiative-docs/` (all in one place for you to sort)
- `_context/cornerstones/source/` (if mixed with business context)

**For each of the 6 initiatives, populate:**
- `initiatives/init-XX/charter.md` with:
  - Initiative name and purpose
  - OKRs (from draft OKR documents)
  - Team/owner assignments
  - Scope (in/out)
  - Dependencies

**Template exists at:** `initiatives/_TEMPLATE_CHARTER.md`

---

## Constraints

- **Local-first** — All data stays in this project folder
- **No deletion** — Never delete source documents, only add/update
- **Atlas-aligned** — Follow the initiative → workflow → task hierarchy
- **Update manifest** — After populating, update `_context/state/manifest.json` with initiative names

---

## When Complete

1. Update `_context/state/OPEN_ITEMS.md` — Mark OI-005 complete
2. Update `_context/state/manifest.json` — Add initiative names to the initiatives section
3. List any gaps or questions in `_inbox/` for follow-up

---

## Prompt to Start Session

```
I'm continuing work on the atlas-eval project. Read _context/project/HANDOFF_STRATEGIC_INITIATIVES.md for your task. I've placed documentation in [LOCATION]. Please process it and populate the initiative charters.
```
