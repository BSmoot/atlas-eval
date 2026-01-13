# Human Calibration

This folder captures human ratings to calibrate against native scores.

## Purpose

Native scores tell us what the system measured. Human ratings tell us if those measurements match user perception.

## Per-Session Ratings

After each session, record 3 ratings (1-5 scale):

1. **Intent Capture**: "Did this capture what you meant?"
2. **Context Useful**: "Was the context useful?"
3. **Overall**: "How was the session overall?"

## Correlation Analysis

Weekly, we compare:

| Native Score | Human Rating | What It Means |
|--------------|--------------|---------------|
| High | High | System working as designed |
| High | Low | Native scoring doesn't match perception |
| Low | High | Native too strict, or human generous |
| Low | Low | System correctly identifying issues |

## File Format

Ratings are captured in JSON format:

```json
{
  "session_date": "YYYY-MM-DD",
  "ratings": {
    "intent_capture": 4,
    "context_useful": 5,
    "overall": 4
  },
  "notes": "Any observations"
}
```
