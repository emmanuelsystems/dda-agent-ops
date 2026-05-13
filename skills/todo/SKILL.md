---
name: todo
description: Convert raw notes, meeting notes, Slack updates, or brainstorms into a clean, prioritized Markdown todo artifact. Use when the user invokes /todo or asks Codex to extract actionable tasks, prioritize notes, assign owners, identify due dates, or write/update artifacts/todo.md from unstructured input.
---

# Todo

## Purpose

Convert `INPUT_TEXT` into one durable Markdown todo artifact at `artifacts/todo.md`.

Keep the workflow narrow: extract actionable tasks, normalize them into next actions, prioritize them, tag owners and due dates, and capture missing details as questions.

## Inputs

Require `INPUT_TEXT`: raw notes, messages, meeting notes, a Slack update, or a brainstorm to convert into tasks.

Accept optional inputs:

- `CONTEXT`: project name and what matters most right now.
- `DEFAULT_OWNER`: owner to use when the owner is unclear. Use `Unassigned` when omitted.
- `TIMEZONE`: use only when interpreting relative dates. Default to the local environment timezone.
- `MAX_TASKS`: cap the task list. Default to 15.

If `INPUT_TEXT` is missing, ask for it instead of creating the artifact.

## Write Boundary

Create or update exactly one file: `artifacts/todo.md`, relative to the current workspace.

Do not delete files. Do not modify anything outside `artifacts/todo.md`.

## Extraction Rules

- Do not fabricate owners, due dates, or commitments.
- Use `Owner: Unassigned` when no explicit owner exists and no `DEFAULT_OWNER` was provided.
- Use `Due: TBD` when no explicit or unambiguous due date exists.
- Add missing owners, deadlines, confirmations, or ambiguous commitments to `Questions / Missing Info`.
- Make each task atomic: one clear next action with one observable outcome.
- Avoid vague verbs such as "work on", "handle", or "look into" unless the task includes the specific action and expected outcome.
- Deduplicate overlapping items and keep the clearest phrasing.
- Keep `Source` as a short verbatim quote from `INPUT_TEXT` so reviewers can trace why the task exists.
- If `Project` cannot be confidently filled from `CONTEXT`, use `TBD`.
- If there are more candidates than `MAX_TASKS`, include the highest-priority items and move lower-confidence or later items to `Backlog / Parking lot` when appropriate.

## Priority Rules

Use only these priorities:

- `P0`: blocks progress, urgent, or time-sensitive.
- `P1`: important but not blocking.
- `P2`: nice-to-have, later, exploratory, or parking lot.

Select the top three non-backlog tasks for `Now (Top 3)`, ordered by urgency and impact. If fewer than three actionable tasks exist, list only the available tasks.

## Procedure

1. Parse `INPUT_TEXT` and extract candidate tasks, decisions, requests, blockers, and follow-ups.
2. Normalize candidates into next-action phrasing.
3. Assign priority, owner, due date, next action, definition of done, and source quote.
4. Deduplicate and cap the list according to `MAX_TASKS`.
5. Choose the top three tasks for `Now (Top 3)`.
6. Write `artifacts/todo.md` using the required template exactly.
7. Verify the artifact satisfies the done-when checklist before responding.

## Required Template

Use this structure exactly, adding tasks as needed:

```markdown
# Todo (generated)

## Context
- Project: TBD
- Notes source: Provided in INPUT_TEXT
- Generated at: YYYY-MM-DD HH:MM (TIMEZONE)

## Now (Top 3)
1. [P0] Task - Owner: ... - Due: ...
2. [P1] Task - Owner: ... - Due: ...
3. [P1] Task - Owner: ... - Due: ...

## Task List
- [ ] [P0] **Task name**
  - Owner: Unassigned
  - Due: TBD
  - Next action: ...
  - Definition of done: ...
  - Source: "verbatim snippet from INPUT_TEXT"
- [ ] [P1] **Task name**
  - Owner: ...
  - Due: ...
  - Next action: ...
  - Definition of done: ...
  - Source: "..."

## Backlog / Parking lot
- [ ] [P2] ...

## Questions / Missing Info
- Who owns: ...
- What is the deadline for: ...
- Confirm whether: ...
```

## Done-When

The run is complete only when `artifacts/todo.md` exists and includes:

- `Now (Top 3)`.
- `Task List` with checkbox tasks.
- `Backlog / Parking lot`.
- `Questions / Missing Info`.
- Every task has priority, owner, due, next action, definition of done, and source.

In the final response, state that `artifacts/todo.md` was created or updated and mention important unresolved questions.
