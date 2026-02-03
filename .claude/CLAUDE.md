# Atlas Evaluation Project

This is the evaluation wrapper for observing Atlas system behavior over multiple weeks.

## Structure

```
atlas-eval/
├── upstack/                    # THE USER PROJECT - start sessions here
│   ├── .claude/CLAUDE.md       # Project Steward configuration
│   ├── _context/               # Junction to ../_context
│   └── atlas-workcore/         # Junction to ../atlas-workcore
├── _context/                   # Actual context storage
├── atlas-workcore/             # Fleet definitions (submodule)
└── _evaluation/                # Evaluation data capture
```

## How to Use

**For stewardship work:** Start Claude sessions in `upstack/`
```
cd upstack
claude
```

**For evaluation administration:** Start sessions in `atlas-eval/` (here)

## Evaluation Data Capture

This project captures:
- Native scores from ContextEngine components (Elicitor, Verifier, Aligner)
- Human calibration ratings (1-5 scales)
- CLI to UI mappings for the design team
- Session observations and friction notes

**Native scoring thresholds (from ContextEngine v3.0):**
- Intent lock completeness: 0.85
- Alignment pass: 0.70
- Anti-goal recall: 0.95
- Drift block: 0.70

## At End of Each Session

Remind the tester to:
1. Provide 3 human calibration ratings (1-5)
2. Note any friction or surprises
3. Record UI mapping: "This would happen in [page X]"

## CLI to UI Mapping Reference

| CLI Action | UI Page | Page ID |
|------------|---------|---------|
| Describe project goal | Concept Capture | PC.1 |
| AI elicitation questions | Concept Capture | PC.1 |
| Context retrieval | Steward Chat | CC.6 |
| Charter alignment | Project Setup | PC.3 |
| Work progress | Task Board | WK.1 |
| Work review | Work Review | WK.7 |

**Known gaps:**
- Outcome vs Intent review (OT.1 needed)
- Drift score display (add to CO.8 or P.1)
