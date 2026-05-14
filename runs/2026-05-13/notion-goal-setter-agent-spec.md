---
title: Notion Goal-Setter Agent Spec
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
created: 2026-05-13
updated: 2026-05-13
approval_status: not_approved
---

# Notion Goal-Setter Agent Spec

## Review Boundary

This is a draft/review-only design artifact. It does not create a Notion AI agent, update Notion, approve automation, promote a new source-of-truth rule, or authorize Codex execution.

Human approval is required before this spec is copied into a Notion agent configuration, used to update Notion pages or databases, committed, pushed, or treated as approved operating procedure.

## Purpose

Define how a Notion AI goal-setter agent could convert DDA-derived todos into consistent Codex `/goal` prompts while staying inside the broader workflow:

```text
DDA structures todos
-> goal-setting layer turns selected todos into Codex /goal prompts
-> Codex executes the approved goal
-> evaluator reviews outputs and improves future goal quality
```

The Notion goal setter is a candidate planning-context surface. It should help turn Notion project/task/research context into a reviewable goal packet and draft Codex `/goal` prompt. It should not execute Codex work.

## Why Notion Is A Candidate Surface

Notion is already the planning and operating surface for DDA-related project context, task state, review logs, knowledge pages, and working notes.

Notion is useful for this role because it can sit near:

- active project pages and task databases
- DDA planning notes and review logs
- source pages such as DDA Pilot Build Brief, DDA Agent Architecture Decisions, Codex Operating Model, and Agentic Team Deployment Context
- knowledge pages and field-guide notes about `/goal`, routing, and orchestration
- future task/status dashboards if approved

Verified current state:

- The repo source-of-truth model says Notion owns planning, active task status, dashboards, review surfaces, and working notes.
- GitHub/repo files own prompt source, agent source, skill specs, templates, evals, schemas, changelogs, and version history.
- The fetched Notion planning pages are draft or working-context pages, not automatically canonical.

Design recommendation:

- Use Notion as the strongest candidate for context-aware goal drafting from planning/task surfaces.
- Do not use Notion as the first canonical implementation surface for the goal-setting rules, because goal-prompt contracts and skill specs should remain repo-backed until reviewed.

## Required Inputs

The Notion goal setter should require a DDA-structured todo packet, not raw chat.

Minimum DDA todo handoff fields:

- `todo_id`: stable identifier if available.
- `todo_title`: one action-oriented todo.
- `todo_source`: source surface and reference, such as Notion task, Linear issue, repo path, Slack message, or DDA artifact.
- `source_quotes_or_claims`: short evidence snippets or claim summaries.
- `desired_outcome`: what should exist or be true when Codex is done.
- `why_now`: priority, deadline, blocker, or active-lane reason.
- `target_repo_or_surface`: repo, docs path, issue, Notion project, or unknown.
- `known_inputs`: files, pages, issue links, prior artifacts, or research to read first.
- `acceptance_criteria`: observable done conditions.
- `constraints`: no-touch files, external-write limits, readiness boundaries, approval gates.
- `review_status`: raw, candidate, accepted working context, ready for Codex, or blocked.
- `missing_info`: explicit gaps DDA could not resolve.

Optional inputs:

- Current DDA goal packet.
- Current Daily Driver state object.
- Current orientation brief.
- Codex completion packet from a prior run.
- Evaluator feedback from a prior goal attempt.
- Relevant Notion project/task properties.

If the DDA todo is not specific enough to route, the Notion goal setter should return a blocked goal packet instead of inventing missing facts.

## Required Outputs

The Notion goal setter should produce a reviewable goal packet, not direct execution.

Required output sections:

- `Current verified state`: what is confirmed from Notion/repo/other sources.
- `Planning context`: task/project context and why this todo matters now.
- `Selected todo`: the single todo being converted.
- `Candidate goals considered`: 2-3 possible goal framings when ambiguity exists.
- `Selected Codex outcome`: one bounded outcome for Codex.
- `Codex /goal draft`: a copy-ready `/goal` prompt.
- `Read-first context`: exact files, pages, issues, and artifacts Codex should read first.
- `In scope`: allowed work.
- `Out of scope`: excluded work.
- `Approval boundaries`: external writes, commits, pushes, Notion writes, Slack posts, memory saves, automation, source-of-truth changes.
- `Acceptance criteria`: observable checks for completion.
- `Return requirement`: what Codex must return to DDA.
- `Open questions and risks`: missing facts, stale surfaces, permission gaps, routing uncertainty.

The `/goal` draft should be concise enough to paste into Codex, but it must preserve the highest-risk boundaries.

Suggested `/goal` shape:

```md
/goal [Outcome]. Read first: [paths/pages/issues]. Produce: [artifact or patch]. Keep in scope: [scope]. Keep out of scope: [exclusions]. Boundaries: [approval gates]. Return: [completion packet requirement].
```

## How It Should Access Project / Planning / Research Context

The Notion goal setter should use a source-priority posture, not a broad workspace search posture.

Read order:

1. The DDA-provided todo packet.
2. The linked Notion task or project page when present.
3. Linked review logs, architecture decisions, field-guide notes, or research outputs.
4. Repo-backed source references named by DDA.
5. Current task status only from the active planning surface.

Source posture:

- For planning and active task status, Notion can be treated as the planning source when the page/task is current and reviewed enough for planning use.
- For prompt, agent, workflow, template, schema, and skill rules, the repo remains the source to read or cite.
- If Notion and repo conflict, the agent must state the conflict and apply the repo source-of-truth rules.
- If a Notion page is a draft or accepted working context, the output must preserve that status.

The agent should not rely on hidden chat history or unlogged conversation memory.

## How It Should Convert DDA Todos Into Codex `/goal` Prompts

Use this conversion sequence:

1. Confirm the todo is execution-class work.
2. Identify the desired Codex-owned outcome: repo edit, research brief, artifact draft, prompt refactor, skill spec, verification, or implementation plan.
3. Strip planning narrative that belongs in DDA or Notion.
4. Preserve only the context Codex needs to start safely.
5. Convert source references into a read-first list.
6. Convert constraints into explicit Codex boundaries.
7. Convert acceptance criteria into done-when checks.
8. Add a return requirement for a Codex-to-DDA completion packet.
9. Mark unresolved facts as open questions instead of burying them inside the prompt.

Strong `/goal` prompts should be:

- one outcome
- repo-aware
- source-grounded
- bounded
- review-status aware
- explicit about no external writes
- explicit about return format

Weak `/goal` prompts should be rejected when they:

- ask Codex to "work on" a broad topic
- combine multiple unrelated outcomes
- omit source references
- omit approval gates
- ask Codex to make planning/status decisions that DDA or Notion owns
- imply automation or external writes are approved

## Constraints And Approval Boundaries

The Notion goal setter must not:

- update Notion unless explicitly approved
- post to Slack
- send email
- save memory
- create commits, branches, pull requests, pushes, or merges
- enable automation
- start Codex execution
- treat a Notion draft page as canonical repo source
- collapse DDA, goal-setter, Codex, and evaluator into one role
- promote `/goal` text as durable truth unless it is saved in an approved artifact

Human approval is required before:

- turning this spec into a Notion AI agent
- granting write permissions
- letting the agent update task records or pages
- using Notion-generated goals as approved Codex execution instructions
- promoting a successful pilot into source-of-truth docs

## Open Questions And Risks

- Notion AI custom-agent availability, permissions, and credit posture were not verified in this run.
- Exact Notion database/page destinations for DDA goal-setter outputs remain unspecified.
- It is not yet confirmed whether the agent should operate in draft-only mode or assisted-setup mode.
- Notion search can surface connected sources, but connected-source authority must be handled carefully.
- Notion task state may be current while repo source files may be more authoritative for agent behavior.
- A Notion goal setter could silently overfit to planning context and under-read repo source unless the read-first rules are enforced.
- If Notion has write access, misfiling or premature status promotion becomes a material risk.

## Pilot Recommendation For This Surface

Do not build the Notion AI goal setter first.

Test Notion second or third, after the reusable skill contract defines the goal shape. The first Notion pilot should be draft-only: feed it one reviewed DDA todo packet and ask for a goal packet plus `/goal` draft, with no page or task writes.
