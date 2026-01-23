# Inbox

Quick capture for notes, todos, and insights. Process later.

## How to Use

**Add an item:**
```
Create a file: YYMMDD_<topic>.md
```

**Or just tell Claude:**
> "Capture this: [your note]"
> "Add to inbox: [your thought]"
> "Todo: [your task]"

Claude will create the file and it will be processed in the next review.

## Item Format

```markdown
# [Topic]

**Captured:** YYYY-MM-DD HH:MM
**Type:** note | todo | insight | question
**Priority:** P0 | P1 | P2 | none
**Related strand:** [optional - link to work strand]

---

[Content]
```

## Processing

Items in inbox should be:
1. **Processed** — Moved to appropriate location (strand, initiative, project note)
2. **Acted on** — If a todo, complete or schedule
3. **Archived** — If no longer relevant, move to `_inbox/_archive/`

---

*Inbox items are context-isolated until explicitly processed.*
