# Daily Driver State Object Schema

## Purpose

Define the minimum reviewable state object for a manual-supervised Daily Driver run.

The state object exists to make the active goal, cross-surface work state, next action, and trace requirements explicit before DDA pre-stages an artifact or routes work to Codex.

## Status

- **Status:** draft
- **Version:** v0.1
- **Owner:** Emmanuel Olana
- **Related agent:** diarized-daily-assistant
- **Created:** 2026-05-07
- **Updated:** 2026-05-07

## Required Top-Level Fields

- `state_date`
- `active_goal`
- `goal_source`
- `active_surfaces`
- `conversation_loops`
- `latest_outputs`
- `project_context_refs`
- `task_structure`
- `pre_staged_artifacts`
- `dispatch_lane`
- `trace_log`
- `blocked_decisions`
- `approval_required`
- `readiness_status`

## Field Definitions

### `state_date`

Date the state object represents.

Expected format:

`YYYY-MM-DD`

### `active_goal`

The current goal the operator is trying to advance.

This should be written as one clear outcome, not a general theme.

### `goal_source`

Where the active goal came from.

Allowed values:

- `operator`
- `david`
- `linear`
- `slack`
- `notion`
- `repo`
- `codex`
- `mixed`

Include a source note when the value is `mixed`.

### `active_surfaces`

List of surfaces involved in the current work loop.

Each surface entry should include:

- `surface`
- `role`
- `current_status`
- `last_checked`
- `evidence_ref`

Allowed surface values:

- `chatgpt`
- `notion_ai`
- `codex`
- `linear`
- `slack`
- `github_repo`
- `gmail`
- `google_drive`
- `memory`
- `other`

### `conversation_loops`

List of active AI or work conversations that need continuity.

Each loop should include:

- `loop_name`
- `surface`
- `purpose`
- `where_it_left_off`
- `next_expected_move`
- `evidence_ref`

### `latest_outputs`

Latest reviewed or review-relevant outputs from the active surfaces.

Each output should include:

- `title`
- `surface`
- `artifact_or_message_ref`
- `status`
- `summary`
- `supports_goal`

Allowed status values:

- `draft`
- `reviewed`
- `posted`
- `committed`
- `superseded`
- `blocked`

### `project_context_refs`

References to project context needed to understand the current goal.

Each reference should include:

- `title`
- `surface`
- `ref`
- `why_it_matters`
- `truth_role`

Allowed truth role values:

- `planning`
- `source`
- `discussion`
- `task_status`
- `runtime_evidence`
- `trace`
- `temporary_context`

### `task_structure`

Current task framing.

Required subfields:

- `linear_issue`
- `owner`
- `status`
- `priority`
- `acceptance_target`
- `next_task`

Use `None` when a field is not currently available.

### `pre_staged_artifacts`

Artifacts DDA should prepare or has prepared for review.

Each item should include:

- `artifact_name`
- `artifact_type`
- `target_surface`
- `review_status`
- `approval_required_before_use`

Allowed artifact type values:

- `orientation_brief`
- `state_refresh`
- `codex_handoff`
- `slack_update`
- `linear_comment`
- `notion_summary`
- `prd_rewrite`
- `workflow_spec`
- `trace_log`
- `run_summary`
- `other`

### `dispatch_lane`

Where the next action should be routed.

Allowed values:

- `dda_only`
- `codex`
- `linear`
- `notion`
- `slack`
- `github_repo`
- `operator_decision`
- `blocked`

### `trace_log`

Evidence trail used to support the state object.

Each trace entry should include:

- `source_surface`
- `source_ref`
- `timestamp`
- `claim_supported`
- `confidence`
- `gap_or_risk`

Allowed confidence values:

- `confirmed`
- `likely`
- `assumption`
- `unknown`

### `blocked_decisions`

Decisions that prevent the next action from becoming durable or executable.

Each blocked decision should include:

- `decision`
- `owner`
- `needed_by`
- `blocking_reason`
- `recommended_resolution`

### `approval_required`

Approval gates that apply before external action.

Use this field to explicitly mark actions that cannot happen silently.

Common approval gates:

- Slack posting
- Notion update
- Memory save
- Email send
- Commit or push
- Automation enablement
- Source-of-truth change
- Runtime readiness claim

### `readiness_status`

Current readiness classification for this state.

Allowed values:

- `red`
- `yellow`
- `green`

For DDA / Daily Driver v0.1, use `yellow` unless a reviewed artifact proves otherwise.

## Markdown Instance Template

```md
# Daily Driver State

## State Date

YYYY-MM-DD

## Active Goal

[One clear goal.]

## Goal Source

[operator | david | linear | slack | notion | repo | codex | mixed]

## Active Surfaces

| Surface | Role | Current Status | Last Checked | Evidence Ref |
|---|---|---|---|---|
| [surface] | [role] | [status] | [timestamp/date] | [link/path/ref] |

## Conversation Loops

| Loop | Surface | Purpose | Where It Left Off | Next Expected Move | Evidence Ref |
|---|---|---|---|---|---|
| [loop] | [surface] | [purpose] | [left off] | [next move] | [ref] |

## Latest Outputs

| Title | Surface | Ref | Status | Summary | Supports Goal |
|---|---|---|---|---|---|
| [title] | [surface] | [ref] | [status] | [summary] | [yes/no] |

## Project Context Refs

| Title | Surface | Ref | Why It Matters | Truth Role |
|---|---|---|---|---|
| [title] | [surface] | [ref] | [why] | [truth role] |

## Task Structure

- **Linear issue:** [issue or None]
- **Owner:** [owner]
- **Status:** [status]
- **Priority:** [priority]
- **Acceptance target:** [target]
- **Next task:** [next task]

## Pre-Staged Artifacts

| Artifact | Type | Target Surface | Review Status | Approval Required Before Use |
|---|---|---|---|---|
| [artifact] | [type] | [surface] | [status] | [approval] |

## Dispatch Lane

[dda_only | codex | linear | notion | slack | github_repo | operator_decision | blocked]

## Trace Log

| Source Surface | Source Ref | Timestamp | Claim Supported | Confidence | Gap Or Risk |
|---|---|---|---|---|---|
| [surface] | [ref] | [timestamp] | [claim] | [confidence] | [gap/risk] |

## Blocked Decisions

| Decision | Owner | Needed By | Blocking Reason | Recommended Resolution |
|---|---|---|---|---|
| [decision] | [owner] | [date] | [reason] | [resolution] |

## Approval Required

- [Approval gate]

## Readiness Status

[red | yellow | green]
```

## Validation Checklist

- Active goal is specific enough to route work.
- Every active surface has an evidence reference or is marked unavailable.
- Conversation loops say where work left off.
- Pre-staged artifacts remain draft/review-only unless approved.
- Dispatch lane does not collapse DDA and Codex responsibilities.
- Trace log separates confirmed evidence from assumptions.
- Approval gates are explicit.
- Readiness status is not upgraded without reviewed proof.
