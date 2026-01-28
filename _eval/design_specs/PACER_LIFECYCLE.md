# Design Spec: PACER Item Lifecycle

**Status:** Draft
**Source:** Evaluation session 2026-01-28
**Target:** atlas-workcore PACER service

---

## Problem Observed

Small inbox items (e.g., "call Dan") have different lifecycles than larger tracked items (e.g., "IRIS integration approach"). Treating them identically creates noise:

- Quick tasks often resolved in real life but not marked done in system
- Items pile up, creating stale attention lists
- User loses trust in the attention surface

---

## Design Principle

**Items have different gravity based on type.** Light items decay fast; heavy items persist and prompt.

---

## Item Types & TTL

| Type | Examples | Default TTL | Decay Behavior |
|------|----------|-------------|----------------|
| **quick** | "call Dan", "send email" | 72h | Auto-archive, no prompt |
| **task** | "review board deck" | 7d | Soft prompt at 5d, archive at 7d |
| **decision** | "CRO candidate approach" | 14d | Prompt at 7d, escalate at 14d |
| **blocked** | "waiting on Anders" | 30d | Re-prompt weekly for status |
| **open_item** | OI-004 IRIS integration | No decay | Weekly confidence check |

---

## Lifecycle States

```
captured → active → [prompted] → resolved | archived | escalated
```

- **resolved**: User marked done
- **archived**: Decayed without action (retrievable, searchable, off active list)
- **escalated**: Decision/blocker exceeded TTL without resolution

---

## Touchpoints

### Session Start
- Surface only items needing attention (prompted, escalated, decisions)
- Not the full list
- Format: "X items need attention" with top item highlighted

### Session End (optional, light)
- "Anything to close out?"
- Quick checkboxes, not a full audit
- Skip if nothing captured this session

### Weekly Digest
- Batch review of all active items by strand
- Confidence check: "Still working on X?" with one-tap responses
- Options: done / still open / defer / drop

---

## Type Classification

### Automatic (capture-time heuristics)
- Contains "call", "email", "send", "schedule" → quick
- Contains "decide", "choose", "approach" → decision
- Contains "blocked", "waiting", "pending" → blocked
- Linked to OI-xxx → open_item
- Default → task

### Manual Override
- User can reclassify at capture or review
- "This is actually a decision" / "This is just a quick task"

---

## Inference Signals (Future Enhancement)

| Signal | Action |
|--------|--------|
| Item mentioned in completed work | Suggest closing |
| Related decision logged | Prompt to resolve dependent items |
| No activity on strand for 14d | Flag strand for review |
| User working in related area | Surface related open items |

---

## Implementation Notes

### Affected Components
- `pacer-calculator.ts` - TTL logic, decay calculations
- `pacer-service.ts` - State transitions, archive handling
- `pacer-mapper.ts` - Type classification from raw input
- Session hooks - Start/end touchpoints

### Data Model Changes
```typescript
interface PacerItem {
  id: string;
  type: 'quick' | 'task' | 'decision' | 'blocked' | 'open_item';
  status: 'captured' | 'active' | 'prompted' | 'resolved' | 'archived' | 'escalated';
  ttl_hours: number;
  created_at: Date;
  last_prompted_at?: Date;
  archived_at?: Date;
  archived_reason?: 'resolved' | 'decayed' | 'dropped';
}
```

---

## Open Questions

1. Should archived items resurface if user searches related terms?
2. What's the right escalation path for decisions that exceed TTL?
3. Should strand-level rollups show archived item counts?

---

## Validation Plan

Test in atlas-eval by:
1. Capturing mix of quick/task/decision items
2. Letting some decay naturally
3. Rating: Did decay match expectations? Did prompts feel right?
4. Adjust TTLs based on calibration

---

*Captured from evaluation observation: inbox items showing as stale when already resolved in real project.*
