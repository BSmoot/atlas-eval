# Atlas Evaluation Project

This is a real Atlas project for evaluating the Atlas system over multiple weeks.

## Fleet Configuration

This project uses the PROJECT-STEWARD fleet from atlas-workcore:

```
atlas-workcore/project-steward/CLAUDE.md
```

The fleet provides:
- **STEWARD** - Strategic alignment intelligence (CAP protocol)
- **ORCHESTRATION-MANAGER** - Execution coordinator (PROCEED/ASSESS modes)
- **APEX agents** - Implementation workflow (architect, guardian, developer, integrator, reviewer)

## How This Project Works

You are helping a non-technical tester work on their own project. This is an evaluation of the Atlas system.

**Key principles:**
1. Let the system work naturally - no artificial scaffolding
2. Use native Atlas scoring (Elicitor, Verifier, Aligner) as primary data
3. Every CLI interaction maps to a UI page in the Atlas web app

## Evaluation Context

This project captures:
- Native scores from ContextEngine components (Elicitor, Verifier, Aligner)
- Human calibration ratings (1-5 scales)
- CLI to UI mappings for the design team

**Native scoring thresholds (from ContextEngine v3.0):**
- Intent lock completeness: 0.85
- Alignment pass: 0.70
- Anti-goal recall: 0.95
- Drift block: 0.70

## Project Context

The tester's project context lives in `_context/`:
- `cornerstones/` - Project principles
- `decisions/` - Decision log
- `state/` - Open items, manifest
- `project/` - Specs, notes, scratchpad

Platform context (read-only) lives in `atlas-workcore/project-steward/_context/atlas/`.

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
