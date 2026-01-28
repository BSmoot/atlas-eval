# Design Specs

Design decisions and specifications for Atlas that emerge from evaluation observations.

## Purpose

This folder captures product/system design that should be implemented in atlas-workcore. These are distinct from:

- `_context/` - Real-world project content (stays clean)
- `_eval/native_scores/` - Measurement data
- `_eval/human_calibration/` - User perception data

## Workflow

1. **Observation**: Something doesn't work well during evaluation
2. **Capture**: Document the problem and proposed design here
3. **Implement**: Build in atlas-workcore
4. **Validate**: Test back in this eval project
5. **Close**: Mark spec as implemented with version reference

## File Format

```markdown
# Design Spec: [Name]

**Status:** Draft | In Progress | Implemented | Validated
**Source:** Evaluation session YYYY-MM-DD
**Target:** [atlas-workcore component]
**Implemented:** [version/commit when done]

---

## Problem Observed
## Design Principle
## Specification
## Implementation Notes
## Validation Plan
```

## Current Specs

| Spec | Status | Target |
|------|--------|--------|
| PACER_LIFECYCLE.md | Draft | pacer-service |
