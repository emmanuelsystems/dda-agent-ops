# State Snapshot Policy Draft

## Purpose

- Define when a Daily Driver state snapshot should be created, what it must contain, and what approval boundary applies.
- Make the hybrid state-location model operational without turning every live state update into a repo event.

## Working Policy

- Live working state may evolve in the planning surface.
- A repo-backed state snapshot is a reviewed checkpoint artifact, not a continuously edited live object.
- Chat may help draft or refresh the state, but chat alone is never the durable home.

## Snapshot Trigger

- Default trigger: create a state snapshot at session close if the session produced a meaningful state update.
- Also create a state snapshot earlier when one of these happens:
  - the recommended dispatch lane changes
  - the active goal changes materially
  - a new approval boundary or blocker appears that affects routing
  - a reviewed artifact changes what DDA should treat as current truth
- Do not create a snapshot for minor wording edits, temporary thinking, or unchanged orientation.

## Minimum Required Fields

- `active_goal`
- `verified_state`
- `active_surfaces`
- `current_loops`
- `blocked_decisions`
- `dispatch_lane`
- `next_actions`
- `trace_sources`
- `snapshot_reason`
- `approval_state`

## Field Guidance

- `active_goal`: one primary goal, plus competing thread only if it materially affects routing.
- `verified_state`: proven evidence first, then assumptions or missing proof kept visibly separate.
- `active_surfaces`: only the surfaces currently relevant to the live loop.
- `current_loops`: what is active, what is unfinished, and what is blocked.
- `blocked_decisions`: unresolved choices that prevent safe promotion or execution.
- `dispatch_lane`: continue here, wait for approval, route to Codex later, or wait for missing evidence.
- `next_actions`: one immediate next action and, if needed, one follow-on action.
- `trace_sources`: enough evidence references that a reviewer can reconstruct why the snapshot says what it says.
- `snapshot_reason`: why this checkpoint exists now.
- `approval_state`: draft, needs review, approved, blocked, or superseded.

## Approval Boundary

- A state snapshot may be drafted without external action.
- Creating or updating a repo-backed snapshot requires explicit approval before it is treated as durable truth.
- Until approved, the snapshot is a review artifact only.
- A snapshot does not by itself authorize:
  - repo implementation
  - Slack posting
  - Notion updates
  - memory saves
  - automation changes
  - readiness or canon claims

## Destination And Naming

- Recommended file name: `state-snapshot.md`
- Recommended path when approved: `runs/YYYY-MM-DD/state-snapshot.md`
- Working draft versions may remain in the current drafting surface until approval is given for promotion.

## When Not To Snapshot

- When the current state is still mostly speculative.
- When no routing-relevant information has changed.
- When the session only produced questions and no clearer current truth.
- When a stronger reviewed source is still expected shortly and would likely supersede the draft.

## Risks To Watch

- Snapshotting too often can make the process heavy and blur which checkpoint matters.
- Snapshotting too rarely can let the live planning state drift away from the evidence lane.
- If approval state is omitted, reviewers may mistake a draft snapshot for durable truth.

## Recommended Current Use

- For the current phase, use `daily-driver-state.md` as the drafting object and promote only approved checkpoint versions into `state-snapshot.md`.

## Approval-Dependent Elements

- Whether session close should remain the default trigger.
- Whether milestone review should also always force a snapshot.
- Whether `state-snapshot.md` is the approved final file name.
- Whether a repo-backed snapshot should require explicit approval every time, or only the first time during this phase.
