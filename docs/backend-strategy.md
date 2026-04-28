---
title: Backend Strategy
asset_type: reference
status: draft
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: docs/backend-strategy.md
created: 2026-04-28
updated: 2026-04-28
---

# Backend Strategy

## Purpose

This document defines the backend storage strategy for moving DDA prompt, DAB, agent, workflow, and operating artifacts out of a Notion-only structure and into a durable GitHub-backed markdown corpus.

The immediate goal is to support the DDA Agent Ops pilot.

The longer-term goal is to create a repeatable backend pattern for converting Systems Shaper's DABs, prompt blocks, agent specs, skills, and workflow instructions into versioned markdown assets that Codex and future workspace agents can read, modify, test, and improve.

## Core Strategy

Notion is the operating surface. GitHub is the durable source backend. Codex is the build/research worker. DDA is the daily alignment layer that routes artifacts into the right place.

## Core Operating Rule

DDA owns daily alignment.

Codex owns build/research execution.

Automations own recurrence.

Durable artifacts own truth.

## Working Model

| Layer | Primary Tool | Role |
|---|---|---|
| Human planning layer | Notion | Planning, review, triage, dashboards, working notes |
| Durable source layer | GitHub | Markdown files, version history, agent specs, templates, skills |
| Execution layer | Codex | Repo work, research, refactoring, artifact generation, verification |
| Communication layer | Slack | Team-safe updates, notifications, handoff visibility |
| Daily alignment layer | DDA | Context pull, classification, daily planning, reporting, carryovers |
| Automation layer | Future automations / MCP / OpenClaw | Recurrence, triggers, scheduled checks, cross-surface routing |

## Why GitHub

The current Prompts DB and Notion workspace are useful for working inventory, but they are not enough for the next phase of agent operations.

Notion is strong for:

- Thinking
- Planning
- Relational context
- Human-facing review
- Working dashboards
- Drafting and triage

GitHub is stronger for:

- Version history
- Diffs
- Branches and pull requests
- Repo-level instructions
- Markdown source files
- Codex-readable file structure
- Skill/spec modularization
- Tests and evals
- Issue tracking
- Release tagging
- Long-term backend storage

The team direction is converging on a markdown file economy, where markdown files become the working instruction layer for agents, workflows, skills, and context vault outputs. The DDA backend should be the first practical pilot of that direction.

## Repo Scope

Immediate pilot repo:

`dda-agent-ops`

Future expansion candidate:

`systems-shaper-agents`

Recommendation:

Use `dda-agent-ops` now. Design it as if it may later become a subfolder inside `systems-shaper-agents`.

## Source-of-Truth Model

The detailed source-of-truth model lives in `docs/source-of-truth.md`.

If Notion and GitHub conflict:

| Conflict Type | Source of Truth |
|---|---|
| Planning/status | Notion wins |
| Prompt/agent source files | GitHub wins |
| Active project tasks | Notion wins unless mirrored to GitHub Issues |
| Version history | GitHub wins |
| Daily logs | Notion for human review; GitHub for durable markdown archive if committed |
| Agent instructions | GitHub wins after approved commit |
| Skill specs | GitHub wins |
| Discussion/context | Newest reviewed artifact wins |
| Memory candidates | Approved memory log wins, not raw chat |

Chat history is not durable truth.

## Notion Owns

- Project planning
- Triage
- Status tracking
- Human-facing dashboards
- Working notes
- Rough context
- Relational databases
- Project tasks
- Review surfaces
- Meeting notes
- Draft thinking
- Prompt compiler context
- Daily review pages
- Manual approval queues

## GitHub Owns

- Prompt markdown source
- DAB source files
- Agent configuration docs
- PRDs
- App flows
- Skill specs
- Schemas
- Examples
- Tests/evals
- Changelogs
- Version history
- Repo instructions
- Codex workflows
- Markdown templates
- Handoff packet templates
- Completion packet templates
- Agent improvement logs after review

## Codex Role

Codex should use the GitHub repo as its working environment.

Codex should perform:

- Converting approved Notion context into markdown
- Refactoring prompt assets
- Creating docs
- Reviewing diffs
- Generating PRDs and app flows
- Creating skill packets
- Checking version consistency
- Producing changelog entries
- Generating eval cases
- Drafting repo instructions
- Creating pull requests or PR-ready changes

Codex output becomes durable only after review and commit.

## Repo Structure

The current scaffold intentionally keeps the first pilot structure minimal and indexable:

```txt
dda-agent-ops/
├── README.md
├── AGENTS.md
├── CHANGELOG.md
├── docs/
├── agents/
│   └── diarized-daily-assistant/
├── templates/
├── runs/
├── skills/
├── snippets/
├── workflows/
├── evals/
├── references/
└── schemas/
```

The approved future expansion model may add documents such as `docs/project-charter.md`, `docs/asset-classification.md`, `templates/daily-log.md`, and `evals/README.md` once there is a clear need. Those files are not required for the first content-fill pass.

## Folder Logic

`docs/` stores project-level documents: strategy, source-of-truth, pipeline, pilot plan, and open questions.

`agents/diarized-daily-assistant/` stores stable source files for the DDA agent: PRD, app flow, instructions, config, memory model, examples, and evals.

`templates/` stores reusable markdown templates: daily loop, handoff/completion, and reports.

`runs/YYYY-MM-DD/` stores date-specific pilot outputs: logs, handoffs, and completions.

`skills/`, `workflows/`, `evals/`, `references/`, and `schemas/` provide scalable slots for modularization once the pilot stabilizes.

## File Naming Rules

Use lowercase kebab-case.

Good:

- `daily-game-plan.md`
- `codex-to-dda-completion.md`
- `automation-plan.md`
- `source-of-truth.md`

Avoid:

- `Daily Game Plan.md`
- `DDA_completionPacket_FINAL_v2.md`
- `new doc copy.md`

Date-based files should use ISO date format:

`YYYY-MM-DD`

Example:

`runs/2026-04-28/`

## Markdown Frontmatter Standard

Every durable markdown file should eventually include frontmatter.

```yaml
---
title:
asset_type:
status:
version:
owner:
related_project:
related_agent:
source_notion_url:
source_database:
github_path:
tags:
created:
updated:
---
```

Recommended `asset_type` values:

- `prd`
- `app_flow`
- `agent_config`
- `instruction`
- `template`
- `skill_spec`
- `workflow`
- `daily_log`
- `handoff_packet`
- `completion_packet`
- `memory_model`
- `automation_plan`
- `evaluation`
- `reference`
- `changelog`

Recommended `status` values:

- `draft`
- `review`
- `approved`
- `active`
- `deprecated`
- `archived`

## Example Agent PRD Frontmatter

```yaml
---
title: Diarized Daily Assistant PRD
asset_type: prd
status: draft
version: v0.2
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
source_notion_url:
source_database: Prompts DB
github_path: agents/diarized-daily-assistant/prd.md
tags:
  - dda
  - prd
  - workspace-agent
  - pilot
created: 2026-04-28
updated: 2026-04-28
---
```

## Example Daily Run Frontmatter

```yaml
---
title: DDA Daily Game Plan
asset_type: daily_log
status: draft
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
source_notion_url:
source_database:
github_path: runs/2026-04-28/daily-game-plan.md
tags:
  - dda
  - daily-run
  - game-plan
created: 2026-04-28
updated: 2026-04-28
---
```

## Asset Classification Model

| Class | Description | Example |
|---|---|---|
| Source | Original prompt/DAB source material | `source.md` |
| Spec | Product or system definition | `prd.md`, `app-flow.md` |
| Config | Agent setup/instructions | `agent-config.md`, `instructions.md` |
| Template | Reusable output structure | `daily-game-plan.md` |
| Run Artifact | Date-specific output | `runs/2026-04-28/evening-report.md` |
| Workflow | Multi-step process | `codex-handoff-workflow.md` |
| Skill | Modular reusable capability | `daily-context-pull.md` |
| Eval | Test or quality check | `handoff-quality-eval.md` |
| Reference | Stable supporting context | `source-of-truth.md` |
| Changelog | Version history | `CHANGELOG.md` |

## Related Docs

- `docs/conversion-pipeline.md`
- `docs/source-of-truth.md`
- `docs/open-questions.md`
