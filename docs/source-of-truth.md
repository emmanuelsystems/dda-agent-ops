---
title: Source of Truth Model
asset_type: reference
status: draft
version: v0.2
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: docs/source-of-truth.md
created: 2026-04-28
updated: 2026-04-28
---

# Source of Truth Model

## Core Rule

Notion is the planning and operating surface.

GitHub is the durable markdown backend.

Codex is the build and research execution layer.

DDA is the daily alignment layer.

Automations own recurrence.

Durable artifacts own truth.

## Durable Truth Rule

Chat history is not durable truth.

A decision, instruction, prompt, skill, or workflow becomes durable only when captured in one of these places:

- GitHub markdown file
- Notion approved page/database record
- Approved memory entry
- Linked issue/task with final status
- Approved release/changelog entry

Codex output becomes durable only after review and commit.

## Surface Ownership

| Surface | Owns |
|---|---|
| Notion | Planning, triage, dashboards, working notes, active task status, review surfaces, daily review pages, manual approval queues |
| GitHub | Prompt source, DAB source files, agent source, PRDs, app flows, instructions, skills, templates, evals, schemas, changelogs, version history |
| Codex | Repo work, research, refactoring, markdown generation, verification, PR-ready changes |
| DDA | Context pull, classification, daily planning, reporting, carryovers, routing artifacts into the right place |
| Slack | Approved team-safe updates, notifications, handoff visibility |
| Linear | Optional implementation tasks and workflow tickets when explicitly used |
| Memory | Approved durable preferences, patterns, decisions, and constraints |
| Chat history | Temporary working context only |

## Conflict Rules

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

If memory conflicts with committed repo files, the committed repo file wins.

If chat history conflicts with a reviewed artifact, the reviewed artifact wins.


## Promotion Workflow (Draft -> Reviewed -> Durable)

### States

1. Draft: working artifact not yet approved.
2. Reviewed: artifact reviewed by human with required checks complete.
3. Durable: approved artifact stored in durable surface (committed GitHub source or approved Notion record).

### Promotion Rules

- Draft -> Reviewed: human reviewer confirms boundary compliance, source citations, and scope alignment.
- Reviewed -> Durable (GitHub): artifact is committed in the repo.
- Reviewed -> Durable (Notion): artifact is explicitly marked approved in Notion.
- Memory durability requires explicit human approval and approved memory logging.

### Precedence Order

1. Committed GitHub source files.
2. Approved Notion artifact records.
3. Approved memory entries.
4. Chat history (temporary context only).

### Conflict Handling Procedure

1. Identify conflicting artifacts and quote their paths.
2. Apply precedence order.
3. Record the resolution in a reviewed artifact.
4. Escalate unresolved ambiguity as an open question.

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

## Codex Owns

Codex owns build/research execution inside the repo. Codex may draft or refactor artifacts, but it does not make those artifacts durable until a human reviews and commits them.

Codex may:

- Convert approved Notion context into markdown.
- Refactor prompt assets.
- Create docs.
- Review diffs.
- Generate PRDs and app flows.
- Create skill packets.
- Check version consistency.
- Produce changelog entries.
- Generate eval cases.
- Draft repo instructions.
- Create PR-ready changes.

Codex must not:

- Treat raw chat history as durable truth.
- Assume direct app integrations unless confirmed.
- Enable automations.
- Collapse DDA and Codex responsibilities.
- Mark speculative assumptions as facts.
- Treat its own output as final without review.

## DDA Owns

DDA owns daily alignment. It should pull context, classify inputs, help form daily plans, report progress, preserve carryovers, and create Codex handoffs when work requires build, research, repo updates, artifact drafting, prompt refactoring, skill generation, automation planning, or verification.

DDA should not become the build worker. It should route build/research execution to Codex through clear handoff packets.

## Automations Own

Automations own recurrence only after manual workflow behavior is proven and approval boundaries are defined.

Automation-related documents in this repo are planning artifacts only. Their existence does not mean automation is enabled.

## Approval Rules

The agent may draft.

The human approves.

Durable artifacts preserve the truth.

Human approval is required before:

- Posting to Slack
- Sending email
- Saving persistent memory
- Updating Notion pages
- Creating or merging pull requests
- Enabling automation
- Treating Codex output as final
- Changing source-of-truth rules

## Related Docs

- `docs/backend-strategy.md`
- `docs/conversion-pipeline.md`
- `docs/open-questions.md`
