# Workflow Pre-Stage Draft

## Purpose Of This Draft

- Define what "pre-stage" means in the Daily Driver loop so the operator can approve one clear workflow behavior before any skill build, repo work, or automation planning continues.
- Keep this as working context for review, not canon and not execution guidance yet.

## Verified Inputs Used

- `runs/2026-05-07/orientation-brief.md`
- Notion working-context docs viewed on 2026-05-06:
  - `Daily Driver Agent - Operating Model + Repo Architecture Scoping Packet v0.1`
  - `Daily Driver Agent - Positioning Reframe Note`
- Linear `SSI-113` issue state and 2026-05-05 to 2026-05-06 comments
- Slack `#diarized-daily` updates from 2026-05-06 and 2026-05-07

## Draft Content

### Working Definition

- Pre-stage means: after DDA restores verified state and identifies the most useful next move, it drafts exactly one review-ready artifact for that move before any external action happens.
- The artifact is a proposal, not a completed action.
- The purpose is to reduce startup friction without bypassing approval boundaries.

### Where Pre-Staging Sits In The Loop

1. Retrieve verified state.
2. Orient the operator.
3. Identify the first recommended action.
4. Pre-stage the single artifact that action needs.
5. Wait for approval, revision, rejection, or rerouting.
6. Dispatch only after approval.

### What Counts As A Pre-Staged Artifact

- `codex-handoff.md` when the next lane belongs to Codex.
- `slack-update.md` when the next lane is a team-safe update draft.
- `linear-note.md` when the next lane is a Linear review or issue update draft.
- `notion-draft.md` when the next lane is a planning or documentation draft.
- `open-questions.md` when missing proof blocks a safe first move.
- `daily-game-plan.md` when orientation is complete and the next need is execution planning.

### Required Inputs

- One active goal.
- Verified state from durable or approved surfaces.
- At least one clearly identified active lane.
- One recommended first action grounded in evidence.
- Visible proof gaps or approval boundaries when they affect the artifact.

### Surface Read Order For Pre-Staging

- First: repo-backed artifacts or approved durable files, when available.
- Second: approved Notion planning or context docs.
- Third: Linear issue state and review comments.
- Fourth: Slack coordination context.
- Fifth: current chat context only as temporary working context.

### Output Contract

- Exactly one primary draft artifact per session-start pass.
- Short statement of purpose.
- Verified inputs used.
- Draft text ready for review.
- Proof gaps or assumptions called out separately.
- Approval-dependent actions listed explicitly.
- Clear next handoff or decision.

### Draft-Only Rules

- Pre-staging may prepare language, structure, destinations, and routing recommendations.
- Pre-staging may not post, save externally, commit, merge, schedule, or claim completion.
- Pre-staging may point to an intended destination, but must not imply the destination was updated.
- If multiple possible artifacts exist, DDA should pick one primary artifact and move the rest into open questions or later options.

### Pass Criteria

- The artifact reduces friction for the next step.
- The artifact matches one identified lane.
- The recommendation is traceable to verified inputs.
- The draft does not blur proposal and execution.
- Approval-sensitive elements are explicit.

### Fail Conditions

- The artifact tries to do execution-heavy work instead of preparing it.
- The draft bundles multiple unrelated next moves into one packet.
- The draft makes canon, readiness, or completion claims not supported by durable evidence.
- The draft depends on missing proof but does not name the gap.

### Recommended Current Use

- For today's loop, the highest-value pre-stage object is this workflow definition itself.
- After review, the next likely pre-staged object is a state-location decision draft or a Codex/Notion-facing packet derived from that decision.

## Approval-Dependent Elements

- Whether this working definition is accepted as the default meaning of pre-stage for DDA.
- Whether DDA should always pre-stage exactly one artifact or may present a ranked list in some cases.
- Whether the state-location decision is part of the same packet or a separate next artifact.
- Whether this should later become a formal skill spec, a Notion planning doc, a repo template, or some combination.

## Next Decision Or Handoff Needed

- Immediate decision: approve, revise, or narrow this pre-stage definition.
- If approved, the next artifact to draft should be the state-location decision packet, unless you want to route directly into a Codex or Notion-facing handoff.
