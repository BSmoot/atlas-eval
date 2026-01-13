# Atlas Evaluation Project

A real Atlas project for evaluating the Atlas system over multiple weeks.

## Purpose

Test Atlas's core promise: **INTENT == EXECUTION**

This evaluation uses the actual Atlas system, not a scaffolded approximation. The goal is to see how the system performs when a non-technical user works on their own project.

## What This Is

- A real Atlas project (not a mock)
- Tracked by native Atlas scoring (Elicitor, Verifier, Aligner)
- Supplemented by human calibration ratings
- Every CLI interaction mapped to UI pages for the design team

## Quick Start

### First-Time Setup

```bash
# 1. Clone the repo
git clone [repo-url] atlas-eval
cd atlas-eval

# 2. Initialize the atlas-workcore submodule
git submodule update --init --recursive

# 3. Configure services (optional - for M2M testing)
# Edit config/services.json with your API keys
```

### Starting a Session

```bash
# Open terminal in project folder
cd atlas-eval

# Start Claude Code
claude

# Then just describe what you want to work on
```

### Updating atlas-workcore (Weekly)

During weekly checkpoints, pull the latest atlas-workcore:

```bash
cd atlas-workcore
git fetch origin
git checkout origin/master
cd ..
git add atlas-workcore
git commit -m "Update atlas-workcore submodule"
```

## Structure

```
atlas-eval/
├── _context/           # Your project context
│   ├── cornerstones/   # Project principles
│   ├── decisions/      # Decision log
│   ├── state/          # Open items
│   └── project/        # Specs, notes
│
├── _eval/              # Evaluation data
│   ├── native_scores/  # System-captured scores
│   ├── human_calibration/  # Your ratings
│   ├── ui_mappings/    # CLI to UI mappings
│   └── weekly_analysis/
│
├── atlas-workcore/     # Platform reference (submodule)
├── config/             # Service configuration
└── docs/               # Documentation
```

## End-of-Session Eval Form

At the end of each session, record your evaluation:

### 1. Copy the UI mapping template

```bash
cp _eval/ui_mappings/TEMPLATE.yaml _eval/ui_mappings/session_$(date +%Y%m%d).yaml
```

### 2. Fill in the form

```yaml
session:
  date: "YYYY-MM-DD"
  duration_minutes: [how long was the session?]

# For each thing you did, map it to a UI page
interactions:
  - cli_action: "What you did"
    ui_page: "Page name (see reference below)"
    page_id: "PC.1, CC.6, WK.1, etc."
    notes: "Any observations"

# What workflows had no obvious UI?
ui_gaps_noticed:
  - "Description of gap"

# Your ratings (1-5 scale)
human_calibration:
  intent_capture: [1-5]  # "Did this capture what I meant?"
  context_useful: [1-5]  # "Was the context useful?"
  overall: [1-5]         # "How was the session overall?"

notes: |
  Any other observations, friction, surprises.
```

### 3. UI Page Reference

| Page ID | Name | Used For |
|---------|------|----------|
| PC.1 | Concept Capture | Intent elicitation, AI questions |
| PC.3 | Project Setup | Charter building |
| P.1 | Project Dashboard | Project overview |
| P.6 | Project Context | Context management (blocked by H-005) |
| CC.6 | Steward Chat | Context surfacing, guidance |
| D.1 | Deliverables | Work structure overview |
| WK.1 | Task Board | Work progress tracking |
| WK.7 | Work Review | Acceptance, review |
| S.1 | Pacer View | Velocity tracking (blocked by H-002) |
| CO.8 | Flow Health | Coordination health |
| OT.1 | Outcome Review | Certificate vs result (GAP - needs creation) |

## What We're Measuring

| Area | Native Score | Your Input |
|------|--------------|------------|
| Intent Capture | Verifier scores | "Did this capture what I meant?" (1-5) |
| Context Quality | Retriever scores | "Was the context useful?" (1-5) |
| Alignment | Aligner scores | "Does this match my intent?" (1-5) |
| Outcome | Certificate comparison | "Did I get what I wanted?" (1-5) |

## Weekly Checkpoint

Each week, we analyze:
1. **Correlation**: Do native scores match your ratings?
2. **Detection**: What did the system flag vs what you noticed?
3. **UI gaps**: Which workflows lack UI surfaces?
4. **Submodule update**: Pull latest atlas-workcore

## When Things Go Wrong

See `docs/WHEN_STUCK.md`

**Remember:** Problems are valuable data. Finding where the system doesn't work is exactly what we're looking for.

## Detailed Documentation

- `docs/GETTING_STARTED.md` - Full setup guide
- `docs/WHEN_STUCK.md` - Troubleshooting
- `_eval/ui_mappings/TEMPLATE.yaml` - Session form template
