# Work Strand: Agentic Organization

**ID:** WS-006
**Status:** Active
**Created:** 2026-01-26
**Owner:** Ben Smoot

---

## Purpose

Build an agentic organization that mirrors our human organization - to test context management, advise and support teams, augment current capabilities, and surface options and leverage we never previously saw.

---

## Core Concept

Agents operate from the same context as their human counterparts. They consume our MVV, goals, ownership structures, job descriptions, and handoff protocols. When context is missing or unclear, they say so - providing a continuous stress test of our documentation and a feedback loop for improvement.

---

## Design Principles

| Principle | Description |
|-----------|-------------|
| Mirror structure | Agent teams map to human teams |
| Shared context | Same inputs as human teammates |
| Gap detection | Agents surface what's missing |
| Autonomous feedback | Agents describe what they wish was different |
| Cross-department teaming | Agents collaborate across boundaries |
| Dynamic spawning | Agents create specialized sub-agents as needed |

---

## Agent Team Structure

### Departmental Agents

Agents that mirror each human team, operating from that team's perspective.

| Human Team | Agent Counterpart | Primary Function |
|------------|-------------------|------------------|
| Sales | Sales Agent Team | Pipeline support, customer intelligence |
| Operations | Ops Agent Team | Process optimization, execution support |
| Finance | Finance Agent Team | Analysis, forecasting, reporting |
| Technology | Tech Agent Team | Architecture guidance, implementation support |
| Product | Product Agent Team | Research, spec support, feedback synthesis |
| Leadership | Strategy Agent Team | Alignment checking, decision support |

Each departmental agent relies on:
- Mission, Vision, Values (MVV)
- Team goals and OKRs
- Ownership and accountability maps
- Job descriptions for team members
- Handoff protocols with other teams

---

### Dynamic Agents (Spawned On-Demand)

Departmental agents can spawn specialized agents for themselves or human teammates.

| Agent Type | Purpose | Spawned By |
|------------|---------|------------|
| Research Agent | Deep-dive investigation | Any team |
| Guide Agent | Walk through process/decision | Any team |
| Execution Agent | Perform specific task | Any team |
| Analysis Agent | Crunch data, find patterns | Any team |
| Draft Agent | Create first versions | Any team |

---

### Context Operations Team

A dedicated agent team that supports the agentic org and by proxy supports the entire business.

| Function | Description |
|----------|-------------|
| Context maintenance | Keep canonical docs current |
| Gap tracking | Log what agents report as missing |
| Distribution | Ensure context reaches all agents |
| Quality assurance | Verify context is accurate |
| Feedback synthesis | Aggregate agent feedback into improvements |

---

## Context Consumption Model

```
Canonical Context (WS-005)
         ↓
    Agent Teams
         ↓
    Gap Detection → Context Ops → Improvements
         ↓
    Human Teams (benefit from cleaner context)
```

---

## Agent Feedback Loop

Agents autonomously report:

| Feedback Type | Example |
|---------------|---------|
| Missing information | "No handoff protocol exists between Sales and Ops for X" |
| Unclear ownership | "It's not clear who owns decision Y" |
| Conflicting guidance | "Goal A and Goal B appear to conflict" |
| Suggested adjustments | "If I had Z, I could do X more effectively" |
| Optimization opportunities | "Teams A and B are duplicating effort on X" |

---

## Cross-Department Value

Agents work across boundaries to find leverage.

| Opportunity Type | Description |
|------------------|-------------|
| Process optimization | Streamline cross-team workflows |
| Information sharing | Surface relevant data between teams |
| Alignment checking | Verify teams are rowing same direction |
| Duplicate detection | Find redundant efforts |
| Gap bridging | Cover handoff gaps between teams |

---

## Implementation Phases

| Phase | Focus | Outcome |
|-------|-------|---------|
| 1 | Context Ops team | Foundation for supporting agents |
| 2 | First departmental agent | Prove the model works |
| 3 | Expand to 2-3 teams | Test cross-team collaboration |
| 4 | Full mirror org | Complete agentic organization |
| 5 | Dynamic agent spawning | Self-service agent creation |

---

## Dependencies

| Dependency | Type | Notes |
|------------|------|-------|
| WS-005 Context Management | Critical | Agents need context to operate |
| WS-001 AI Exploration | Internal | Building blocks, human-AI model |
| Building blocks platform | Technical | Agent infrastructure |
| MVV, JDs, goals documentation | Content | Agent operating context |

---

## Success Criteria

- [ ] Context Ops agent team operational
- [ ] At least one departmental agent team running
- [ ] Agents successfully consuming shared context
- [ ] Gap detection producing actionable feedback
- [ ] Cross-department collaboration demonstrated
- [ ] Dynamic agent spawning working
- [ ] Human teams report value from agent support

---

## Next Actions

- [ ] Design Context Ops agent team spec
- [ ] Identify first departmental team to mirror
- [ ] Inventory existing MVV, goals, JDs for that team
- [ ] Define gap detection output format
- [ ] Create feedback-to-improvement workflow

---

## Notes

This strand is both a test of WS-005 (context management) and a value delivery mechanism. If context is good enough for agents to operate effectively, it's good enough for humans. Gaps agents find are gaps humans are likely working around.

The agentic org doesn't replace the human org - it amplifies it.

---

*Last Updated: 2026-01-26*
