# Agent Instructions

## Repo Purpose

This repo is the backend markdown corpus for the Diarized Daily Assistant Agent pilot.

It stores durable source files for DDA, including PRD, app flow, instructions, memory rules, templates, evals, and Codex handoff/completion workflows.

## Core Operating Rule

DDA owns daily alignment.  
Codex owns build/research execution.  
Automations own recurrence.  
Durable artifacts own truth.

## How Codex Should Use This Repo

Codex may:

- Read existing markdown files.
- Create draft markdown files.
- Refactor prompt and agent assets.
- Improve PRDs, app flows, instructions, templates, and evals.
- Check consistency across files.
- Suggest file moves or structure improvements.
- Create completion packets when responding to DDA handoffs.

Codex must not:

- Assume direct Notion, Slack, Gmail, Calendar, GitHub, or Codex integrations exist unless confirmed.
- Treat raw chat history as durable truth.
- Auto-create automations.
- Store private reflection in team-facing files.
- Collapse DDA and Codex responsibilities.
- Overwrite approved source files without preserving changelog context.
- Mark speculative assumptions as facts.
- Create or push commits without explicit human approval.

## Source-of-Truth Rules

If Notion and GitHub conflict:

- For planning and task status, Notion wins.
- For prompt and agent source files, GitHub wins.
- For version history, GitHub wins.
- For active project tasks, Notion wins unless mirrored to GitHub issues.
- For discussion/context, the newest reviewed artifact wins.

If memory conflicts with committed repo files, the committed repo file wins.

## Where To Read

For DDA work, read:

- `agents/diarized-daily-assistant/prd.md`
- `agents/diarized-daily-assistant/app-flow.md`
- `agents/diarized-daily-assistant/instructions.md`
- `agents/diarized-daily-assistant/agent-config.md`
- `agents/diarized-daily-assistant/memory.md`
- `docs/backend-strategy.md`
- `docs/conversion-pipeline.md`
- `docs/source-of-truth.md`
- `templates/`

## Where To Write

Use these locations:

- Agent source files: `agents/diarized-daily-assistant/`
- Project docs: `docs/`
- Reusable templates: `templates/`
- Daily run artifacts: `runs/YYYY-MM-DD/`
- Behavior evals: `evals/`
- File schemas: `schemas/`

## DDA to Codex Handoff Rules

When a task requires build, research, repo work, artifact drafting, prompt refactoring, skill generation, automation planning, or verification, DDA should produce a handoff packet.

Use:

`templates/dda-to-codex-handoff.md`

## Codex Completion Rules

After completing a handoff, Codex should return a completion packet using:

`templates/codex-to-dda-completion.md`

The completion packet should include:

- Summary
- Files changed
- Decisions made
- Open questions
- Recommended next steps
- DDA integration notes

## Approval Boundaries

Human approval is required before:

- Posting to Slack
- Sending email
- Saving persistent memory
- Updating Notion pages
- Creating or merging pull requests
- Enabling automation
- Treating Codex output as final
- Changing source-of-truth rules

## Commit Expectations

Suggested commit format:

`type: short description`

Types:

- `docs`
- `agent`
- `template`
- `workflow`
- `eval`
- `schema`
- `run`
- `chore`

Examples:

- `docs: add backend strategy`
- `agent: add dda prd`
- `template: add codex handoff packet`
- `eval: add slack-safe reporting checks`
