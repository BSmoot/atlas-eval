# Handoff: Existing Notes Import

**Created:** 2026-01-14
**For:** New Claude session
**Task:** Import and organize existing notes into Atlas structure

---

## Context

You are working on an Atlas-aligned executive knowledge management system for the CEO of UPSTACK, a 260-person IT infrastructure channel business.

**Read these files first:**
1. `_context/project/PROJECT_CONTEXT.md` — Full project context
2. `_context/state/OPEN_ITEMS.md` — See OI-003

---

## Your Task

The user will provide paths to:
1. **Work notes folder** — Contains `.txt` files in `yymmdd_<topic/attendee>` format
2. **Obsidian vault** — Contains `.md` notes (may overlap or be different)

**Your job:**

### Phase 1: Analysis
- Inventory all notes (count, date range, topics)
- Identify duplicates or overlapping content
- Categorize by type: meeting notes, insights, todos, decisions, etc.
- Propose organization strategy

### Phase 2: Import (after user approval)
- Copy notes into appropriate locations:
  - Meeting notes → `_context/project/notes/meetings/`
  - Insights/ideas → `_inbox/` for processing
  - Decision-relevant → `_context/decisions/` or reference in DECISION_LOG
  - Initiative-specific → `initiatives/init-XX/source/`
  - Personal strand-related → `initiatives/personal-execution/strands/` or reference
- Preserve original filenames and dates
- Create an index if helpful

### Phase 3: Synthesis (optional, if requested)
- Extract key themes
- Identify open threads/unfinished items
- Surface insights across notes

---

## Constraints

- **No deletion** — Copy, don't move. Original notes stay untouched.
- **No external access** — Only read from paths user provides
- **Preserve dates** — Keep yymmdd naming convention or add metadata
- **Local-first** — All imported content stays in this project folder

---

## Output Locations

```
_context/project/notes/          # Organized imported notes
├── meetings/
├── insights/
└── reference/

_inbox/                          # Items needing processing
```

---

## When Complete

1. Update `_context/state/OPEN_ITEMS.md` — Mark OI-003 complete
2. Create `_context/project/NOTES_INDEX.md` if helpful
3. List any notes that need clarification or follow-up in `_inbox/`

---

## Prompt to Start Session

```
I'm continuing work on the atlas-eval project. Read _context/project/HANDOFF_NOTES_IMPORT.md for your task. My notes are at:
- Work notes: [PATH TO TXT NOTES]
- Obsidian vault: [PATH TO OBSIDIAN]

Please analyze and propose an import strategy.
```
