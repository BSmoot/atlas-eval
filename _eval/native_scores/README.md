# Native Scores

This folder captures scores from Atlas's built-in evaluation components.

## What Gets Captured

### Elicitor Scores
- `classify()` outputs (PRE_CONCEPT vs CONCEPT)
- Gap analysis results
- Questions generated
- Lock readiness assessments

### Verifier Scores
- goal_accuracy
- goal_coverage
- anti_goal_recall
- over_interpretation rate
- pass/reground decisions

### Aligner Scores
- alignment_result.overall
- constraint_compliance
- drift_alerts triggered
- pivot_classifications

### Context Engine Metrics
- retrieval_relevance
- context_types_used
- staleness_events

## File Format

Scores are captured in JSON format:

```json
{
  "session_date": "YYYY-MM-DD",
  "component": "elicitor|verifier|aligner",
  "scores": { ... }
}
```
