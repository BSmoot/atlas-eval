# Project Context

**Status:** Active
**Last Updated:** 2026-01-14

---

## What This Project Is

An **executive knowledge management and work orchestration system** for the CEO of UPSTACK, a 260-person IT infrastructure channel business.

**UPSTACK Context:**
- Business model: Brokering transactions between enterprises and infrastructure service providers
- Core services: Data center colocation, network connectivity, CCaaS, UCaaS, CX/AI tooling, Security, Managed Services, IoT
- Current focus: Proving organic cross-sell and new logo sales through demand generation investments, while transforming into a scalable, data-driven execution platform
- Growth strategy: Acquisition + organic hiring, now focused on operational maturity

---

## Goals

### Primary Goal
Reduce context-switching overhead and information overload by providing a unified system that:
1. Tracks personal work strands tied to intended outcomes
2. Tracks 6 strategic initiatives for 2026 with OKRs and team alignment
3. Tracks UPSTACK performance metrics with analysis and guidance
4. Provides inbox/outbox for capturing notes, todos, insights
5. Derives outputs for distribution (emails, docs, occasional slides)
6. Keeps all context and assets organized, versioned, and accessible

### Secondary Goals
- Chief of staff agent to help manage, ideate, strategize, prioritize
- Specialist agents for expertise and execution (research, analysis, writing)
- Spin-off execution "fleets" for specific business needs (QBR creation, customer insights, ML assessments)
- Board positioning and change leadership communication support

---

## Constraints

### Technical
- **Local-first**: All data stored locally on Windows
- **Local git**: Version control via local git repository
- **Backup**: Cloud-sync'd folder to SharePoint (GitHub backup pending security review)
- **Single user**: Built for one executive today; potential product translation later

### Operational
- No replacement of existing tools (SharePoint, IRIS, Obsidian, etc.)
- No automated external communication (all outputs require human review before distribution)
- No deletion or destruction of information
- No external data leakage

### Existing Inputs
- `.txt` notes in `yymmdd_<topic>` format (existing notes folder)
- `.md` notes in Obsidian
- SharePoint company information
- IRIS system for semantic queries against internal data
- Draft OKRs for 2026 strategic initiatives

---

## Anti-Goals (What This Is NOT)

- **Not a CRM replacement** - Salesforce and existing customer systems stay as-is
- **Not an automation engine** - Human review required for all external outputs
- **Not a team collaboration tool** (yet) - Single user focus for now
- **Not reinventing the wheel** - Should leverage existing Atlas agents, modules, and marketplace capabilities where available

---

## Success Criteria

**90-day success indicator:**
> "I'm guiding each initiative team and my own work BASED ON the output of this system, and fully trusting the alignment of intent to execution."

**Specific measures:**
- [ ] All personal work strands tracked with clear outcomes and status
- [ ] 6 strategic initiatives visible with OKR progress
- [ ] Can capture note/insight/todo in <30 seconds and trust it won't be lost
- [ ] Weekly output derived from system guides actual decisions
- [ ] Zero information loss or leakage incidents

---

## Atlas Evaluation Context

This is a real project being used to evaluate the Atlas system.

**Evaluation lens:**
- How well does Atlas enable rapid project standup?
- How easily can existing agents/tools/services be discovered and integrated?
- Does the system maintain alignment between stated intent and actual execution?
- What friction exists in the CLI-to-work pipeline?

**CLI to UI Mapping:**
| This Session | UI Page | Page ID |
|--------------|---------|---------|
| Concept capture / intent elicitation | Concept Capture | PC.1 |

---

## Open Questions

1. How to access atlas-workcore and existing agent marketplace?
2. Security review outcome for GitHub backup
3. Integration approach with existing IRIS system
4. Import strategy for existing notes (txt + md)
