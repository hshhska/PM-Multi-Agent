# Owen — PM Multi-Agent Orchestrator

> A single-file AI skill that turns Claude / CodeMaker into a **14-agent product team**, coordinated by Owen the orchestrator.

## What is Owen?

Owen is a prompt-based multi-agent framework for **product managers**. You give it a requirement, and Owen:

1. **Plans** — scans which agents are needed, drafts an execution plan with acceptance criteria
2. **Executes** — dispatches work to specialized agents (PRD writer, researcher, data analyst, etc.) with parallel collaboration
3. **Tests** — runs your acceptance criteria against the output, loops until all tests pass
4. **Delivers** — hands you a reviewed, multi-perspective deliverable for final sign-off

No code. No API keys. Just one `.md` file.

## The Team (14 Agents)

| Agent | Role | What they do |
|-------|------|-------------|
| **Owen** | Orchestrator | Plans, dispatches, tracks status, never produces content |
| **Nora** | Requirements Intake | Organizes messy input, identifies info gaps |
| **Parker** | PRD Writer | Writes structured PRDs with clear boundaries |
| **Sage** | Spec Agent | Bridges product → engineering, produces dev-ready specs |
| **Miles** | Planning | Work breakdown, RACI, milestone scheduling |
| **Vera** | Validation | Tests assumptions, walks through pipelines pre-launch |
| **Robin** | Research | Competitive analysis, market research with actionable conclusions |
| **Rachel** | Reporting | Executive-ready presentations and summaries |
| **Dale** | Data | SQL queries, metric analysis, data processing |
| **Dev** | Demo/Prototype | Quick HTML demos, API validation scripts |
| **Cleo** | Operations | Copy review, campaign strategy assessment |
| **Rex** | Quality Gate | Runs acceptance tests, enforces the Goal-Driven loop |
| **Tim** | Tech Perspective | Flags technical risks during production |
| **Uma** | User Perspective | Catches missing user scenarios |
| **Beth** | Business Perspective | Validates ROI and business alignment |

## Core Design: Goal-Driven Loop

Inspired by the Wiener-Shannon-Boyd dual agent system:

```
① PM defines goal + acceptance criteria (tests)
        ↓
② Agents execute collaboratively
        ↓
③ Rex runs criteria tests against output
        ↓
   ┌─ All ✅ → PM does final review
   └─ Any ❌ → Specific errors returned to agents → back to ②
```

**"Done" = passed all tests, not "finished doing stuff".**

Not every task needs this — Owen auto-detects when to use the full loop vs. direct execution.

## Install

### Claude Code CLI
```bash
# Global (works in all projects)
cp owen.md ~/.claude/commands/owen.md

# Project-level (works only in this project)
cp owen.md .claude/commands/owen.md
```

### CodeMaker
```bash
cp owen.md .codemaker/commands/owen.md
```

Then type `/owen` (Claude Code) or `/user:owen` (CodeMaker) to activate.

## Usage

```
Owen, I need a PRD for a new notification system
Owen, status?
Owen, review the research report Robin produced
Owen, what's blocked?
```

## License

MIT — use it however you want.
