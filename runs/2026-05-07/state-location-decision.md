# State Location Decision Memo

## Purpose

- Decide where the first live Daily Driver state object should live during the current manual, approval-gated phase.
- Keep the decision aligned with DDA source-of-truth rules, multi-surface orientation needs, and the current no-execution posture.

## Decision Question

- For the first live Daily Driver state object, should the working home be:
  - Notion-first
  - Repo-first
  - Hybrid

## Verified Inputs Used

- `/workspace/runs/2026-05-07/orientation-brief.md`
- `/workspace/runs/2026-05-07/workflow-pre-stage.md`
- `/workspace/runs/2026-05-07/daily-driver-state.md`
- Notion working-context docs viewed on 2026-05-06:
  - `Daily Driver Agent - Operating Model + Repo Architecture Scoping Packet v0.1`
  - `Daily Driver Agent - Positioning Reframe Note`
- Linear `SSI-113` state and review comments
- Slack `#diarized-daily` context from 2026-05-06 and 2026-05-07

## Decision Criteria

- Must support fast session-start orientation.
- Must preserve source-of-truth discipline instead of turning chat into durable truth by accident.
- Must work in a manual-first, approval-gated phase.
- Must make it easy to separate live working state from reviewed durable snapshots.
- Must not force repo execution or external writes before approval.

## Option 1: Notion-First

### Description

- Keep the live Daily Driver state object primarily in Notion as the working state surface.
- Use repo-backed artifacts later only for reviewed snapshots or approved outputs.

### Strengths

- Best fit for live planning context and cross-linked notes.
- Easiest place to maintain evolving state without implying implementation.
- Matches the current reality that much of the DDA framing already lives in Notion working-context docs.
- Lower friction for frequent human review and revision.

### Weaknesses

- Notion working context is explicitly below repo-backed artifacts in the truth hierarchy.
- Risks turning draft planning state into de facto truth unless the snapshot boundary stays strict.
- Harder to treat as durable proof if later review asks for artifact-backed evidence.

### Best Use Case

- Strongest if the immediate need is fluid working-state reconstruction and review, not durable audit proof.

## Option 2: Repo-First

### Description

- Keep the live state object primarily as a repo-backed markdown artifact from the start.

### Strengths

- Strongest durability and audit posture.
- Aligns well with the stated truth hierarchy that favors repo-backed artifacts.
- Makes later proof review simpler if the artifact is already versioned and stable.

### Weaknesses

- Too heavy for the current manual-first, review-heavy phase.
- Risks prematurely turning a fluid working object into something that feels canonical.
- Would push the workflow toward repo writes before state semantics and approval rules are settled.
- Conflicts with the current instruction posture that repo changes should wait for explicit approval and later execution routing.

### Best Use Case

- Strongest only after the state shape is approved and the work is ready to move from planning object to durable operating artifact.

## Option 3: Hybrid

### Description

- Keep the live working state in Notion or chat-facing planning context first, but produce an approved repo-backed state snapshot at defined points such as session close or reviewed milestone.

### Strengths

- Best match for the scoping doc's direction that state should eventually live in both a live planning surface and a committed snapshot.
- Preserves agility for working-state updates while still creating durable evidence when approved.
- Separates temporary coordination state from stronger truth artifacts.
- Fits DDA's current manual posture and supports later promotion into a more formal operating model.

### Weaknesses

- Requires a clear rule for when the snapshot is created, or the boundary will blur.
- Adds a small amount of operational complexity because two surfaces must stay intentionally distinct.
- Needs explicit wording so the live planning state does not get mistaken for reviewed durable truth.

### Best Use Case

- Strongest when the system needs both live orientation and auditable proof, but is not yet ready to treat every state update as a repo event.

## Comparison Summary

- Notion-first optimizes flexibility.
- Repo-first optimizes durability.
- Hybrid optimizes boundary discipline between live working state and reviewed durable state.

## Recommendation

- Recommend `Hybrid`, with this operating rule:
  - Live working state starts in Notion-facing planning context.
  - Repo-backed `state-snapshot.md` is created only after review or at a defined session checkpoint.
  - Chat may draft or refresh state, but chat alone is never treated as the durable home.

## Why This Recommendation Fits Current Evidence

- The scoping packet already points toward both a live truth surface and a committed snapshot.
- Today's work is still definition-heavy and approval-dependent, so a repo-first model would over-harden a still-moving object.
- A Notion-only model would underserve the evidence lane and make later proof review weaker.
- Hybrid keeps DDA aligned with its own source-of-truth rules without forcing premature implementation.

## Proposed Operating Rule

- During the current phase:
  - Notion holds the editable live state object.
  - ChatGPT can draft refreshes and proposed changes.
  - Repo snapshots happen only after explicit approval and only as reviewed checkpoint artifacts.

## Approval-Dependent Elements

- Whether `Hybrid` is the approved initial state-location model.
- Whether the live working home should specifically be Notion, rather than another planning surface.
- When the first repo snapshot should be required:
  - session close
  - milestone review
  - only when a state change materially affects routing or proof
- What the snapshot file should be called in practice:
  - `state-snapshot.md`
  - `daily-driver-state.md`
  - another approved name

## Open Risks

- If the snapshot trigger stays vague, the hybrid model will create ambiguity instead of clarity.
- If Notion state is edited without a later approved snapshot, the evidence lane may lag behind live context.
- If repo snapshots are created too often, the workflow may become heavy before the model is stable.

## Next Decision Needed

- Approve, revise, or reject the hybrid recommendation.
- If approved, the next useful artifact is a short state-snapshot policy draft that defines:
  - trigger
  - minimum fields
  - approval boundary
  - destination name
