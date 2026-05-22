# Agent Instructions

## Repo Purpose

This repo is the backend markdown corpus for the Diarized Daily Assistant Agent pilot.

It stores durable source files for DDA, including PRD, app flow, instructions, memory rules, templates, evals, and Codex handoff/completion workflows.

## Core Operating Rule

DDA owns daily alignment.  
Codex owns build/research execution.  
Automations own recurrence.  
Durable artifacts own truth.

## David Codex Workloop

For DDA and Codex work, design the workflow as:

`intent -> context -> mode -> slot -> cadence -> artifact -> verifier -> memory -> gate -> learning update`

Use this sequence as an operating checklist, not as permission to bypass approval boundaries. In particular, `memory`, external writes, automations, pull requests, and final-status claims still require the human approval gates below.

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

## Coding Behavior Contract

Use this Karpathy-derived 12-rule contract for Codex work in this repo:

1. Think before coding: state assumptions, surface tradeoffs, ask when unclear, and push back when a simpler or safer path exists.
2. Simplicity first: write the minimum code or markdown needed to solve the request; avoid speculative features and single-use abstractions.
3. Surgical changes: touch only the files and lines required; do not refactor, reformat, or clean unrelated code.
4. Goal-driven execution: define what success means, then verify against that success condition before reporting done.
5. Use the model for judgment, not deterministic work: routing, retries, status checks, transforms, and mechanical validation belong in tools or code where possible.
6. Respect budget and context limits: if a task is growing past the available context, summarize current state and surface the need for a fresh pass.
7. Surface conflicts, do not average them: when repo files, memory, Slack, Notion, Linear, or prior artifacts disagree, name the conflict and follow the source-of-truth rules.
8. Read before writing: inspect the relevant file, neighboring files, templates, and existing patterns before adding or changing content.
9. Tests and checks must verify intent: passing commands are not enough if they do not prove the behavior or artifact quality the task requires.
10. Checkpoint significant steps: for multi-step work, keep the user oriented on what changed, what is verified, and what remains.
11. Convention beats novelty: match this repo's current structure, language, templates, naming, and conservative proof posture unless asked to change them.
12. Fail visibly: never report success if files, records, tests, sources, checks, sends, commits, pushes, or approvals were skipped, partial, blocked, or unverified.

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
