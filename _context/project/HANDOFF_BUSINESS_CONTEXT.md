# Handoff: Industry & Business Context

**Created:** 2026-01-14
**For:** New Claude session
**Task:** Synthesize industry and business context into cornerstones

---

## Context

You are working on an Atlas-aligned executive knowledge management system for the CEO of UPSTACK, a 260-person IT infrastructure channel business.

**Read these files first:**
1. `_context/project/PROJECT_CONTEXT.md` — Full project context
2. `_context/cornerstones/CORNERSTONE_UPSTACK.md` — Current business context (draft)

---

## Your Task

The user will place industry and business documentation in:
- `_context/cornerstones/source/industry/` — Market reports, channel dynamics, competitor info
- `_context/cornerstones/source/business/` — UPSTACK financials, org structure, business model

**Your job:**

### Phase 1: Analysis
- Review all source documents
- Identify key themes, facts, and insights
- Note gaps or questions

### Phase 2: Synthesize Cornerstones

Create or update these cornerstone documents:

| File | Content |
|------|---------|
| `CORNERSTONE_UPSTACK.md` | Update with richer company context |
| `CORNERSTONE_INDUSTRY.md` | IT infrastructure channel landscape, trends, dynamics |
| `CORNERSTONE_BUSINESS_MODEL.md` | How UPSTACK makes money, unit economics, growth levers |
| `CORNERSTONE_COMPETITIVE.md` | Competitive landscape, differentiation, threats |

**Cornerstone format:**
- Clear sections with headers
- Facts over opinions
- Source references where applicable
- Actionable insights highlighted

### Phase 3: Update Manifest

Add new cornerstones to `_context/state/manifest.json` in the items array.

---

## Constraints

- **No deletion** — Source documents stay in `/source/`
- **Synthesis, not copy** — Cornerstones should be structured knowledge, not raw dumps
- **Atlas-aligned** — Cornerstones are canonical assets referenced across all initiatives
- **Local-first** — All content stays in this project folder

---

## When Complete

1. Update `_context/state/manifest.json` — Add new cornerstone items
2. List any gaps or questions in `_inbox/` for follow-up
3. Note which source docs were most/least useful

---

## Prompt to Start Session

```
I'm continuing work on the atlas-eval project. Read _context/project/HANDOFF_BUSINESS_CONTEXT.md for your task. I've placed documentation in _context/cornerstones/source/. Please analyze and synthesize into cornerstones.
```
