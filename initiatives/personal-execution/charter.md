# Personal Execution Initiative

**Status:** Active
**Owner:** CEO
**Created:** 2026-01-14

---

## Purpose

Track personal work strands tied to intended outcomes. Reduce context-switching overhead by maintaining clear visibility into active work, status, and next actions.

## Scope

- Personal work items (not delegated to team)
- Cross-initiative work that doesn't belong to a single strategic initiative
- Ad-hoc execution and decision-making
- Knowledge transfer and information management

## Success Criteria

- [ ] All active work strands visible with clear outcomes
- [ ] Status updated in real-time as work progresses
- [ ] Can identify next action for any strand in <30 seconds
- [ ] Context-switching friction measurably reduced

---

## Structure

### Strands

Each work strand is a workflow-equivalent:

```
strands/
├── strand_<id>.md          # Strand definition + status
└── tasks/
    └── task_<id>.json      # Discrete tasks within strand
```

### Strand Template

```markdown
# [Strand Title]

**ID:** strand_XXX
**Status:** active | paused | complete | blocked
**Outcome:** [What success looks like]
**Related initiative:** [If any]
**Priority:** P0 | P1 | P2

## Context
[Why this strand exists, what triggered it]

## Current State
[Where we are now]

## Next Actions
- [ ] Action 1
- [ ] Action 2

## Log
| Date | Update |
|------|--------|
| YYYY-MM-DD | [What happened] |
```

---

## Active Strands

*To be populated as strands are created.*

| ID | Title | Status | Priority |
|----|-------|--------|----------|
| — | — | — | — |
