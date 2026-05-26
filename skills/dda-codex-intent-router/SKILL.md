---
name: dda-codex-intent-router
description: Stabilize messy DDA or Systems Shaper intent, classify work shape, route to the smallest safe execution surface, create bounded run packets, reconcile completion outputs, and identify memory or skill candidates without making external writes, automation, runtime-readiness, or canon claims.
---

# DDA Codex Intent Router

## Review Boundary

This is a repo-local draft skill for review. It is not a canon source, runtime configuration, automation, PRD update, or approval to write to external systems.

Use it as a manual operating procedure for routing DDA, ATDL, or Systems Shaper work into the smallest safe next artifact or execution surface.

## Purpose

Preserve the DDA/Codex workloop when intent is messy, source-heavy, or likely to blur planning, execution, proof, and memory decisions.

The governing sequence is:

```text
intent -> context -> mode -> slot -> cadence -> artifact -> verifier -> memory -> gate -> learning update
```

Use this sequence as a checklist. Do not use it to bypass human approval gates.

## Trigger

Use this skill when the user asks Codex or DDA to turn mixed intent into a safe route, especially when the work involves:

- Notion, Linear, Slack, Gmail, GitHub, repo, or memory context.
- Codex handoffs or completion review.
- Workflow design or source-heavy planning.
- Skill, automation, memory, or canon candidates.
- DDA / ATDL proof boundaries.
- Ambiguous requests where execution before routing could distort the intent.

Do not use this skill for simple one-off answers that do not need source stabilization, routing, execution planning, verification, or memory decisions.

## Inputs

Require:

- `USER_INTENT`: what the human is trying to accomplish.
- `AVAILABLE_CONTEXT`: supplied sources, repo paths, tickets, notes, prior artifacts, or connected-surface references.

Accept optional inputs:

- `REQUESTED_MODE`: one of the modes below when the user already knows the shape.
- `TARGET_DATE`: date for run artifacts or freshness checks.
- `OUTPUT_PATH`: requested artifact path.
- `APPROVALS`: explicit permissions already granted by the human.
- `STOP_BOUNDARIES`: actions the human explicitly blocked. These override artifact creation and execution even when the requested surface is inside the repo.

If the intent, sources, verifier, or approval boundary is too unclear to route safely, ask for the missing item or produce a Research Preflight Packet instead of executing.

## Modes

| Situation | Mode |
|---|---|
| Messy sources, unclear claims, doctrine/research implications. | Research Preflight Mode |
| User wants to decide where work should go. | Intent Router Mode |
| Work is ready for Codex or another execution surface. | Run Packet Mode |
| Codex or another agent returned output. | Completion Reconciliation Mode |
| Learning may need to survive. | Memory Banking Mode |

Keep the modes together until repeated manual use proves stable triggers, inputs, outputs, and validators.

## Source Order

When sources disagree, apply the repo's current source-of-truth rules:

1. Committed repo files for prompt, agent source, durable artifact, and version-history truth.
2. Notion for planning and active task status when current and explicitly provided or fetched.
3. Linear for active issue state, lane status, and gating comments when current and explicitly provided or fetched.
4. Slack, Gmail, or meeting notes for discussion and intake context, not durable truth.
5. Memory as discovery context only; verify important claims against current sources when feasible.

If a claim cannot be verified, label it as unknown, candidate, partial, or unproven.

## Procedure

1. Restate the review boundary, approvals, blocked actions, and source basis.
2. Identify the user's intent and the work shape.
3. Choose the mode. If the mode is unclear, default to Research Preflight Mode.
4. Fill the workloop fields: intent, context, mode, slot, cadence, artifact, verifier, memory, gate, and learning update.
5. Route to the smallest safe next surface: DDA, Codex, `/goal`, manual pilot, review packet, draft external message, skill candidate, automation candidate, memory candidate, or human-only decision.
6. Produce the required packet for the chosen mode.
7. Verify that the packet includes a verifier, human gate, stop conditions, and candidate-vs-approved labels where relevant.
8. Return the packet or create the requested draft artifact only inside the approved repo scope.

For manual validation or dry runs, produce the required packet in the response without creating files unless the human explicitly approves file creation.

## Packet 0: Research Preflight Packet

Use this when inputs are source-heavy, ambiguous, strategic, doctrine-related, or likely to be distorted if routed too early.

```markdown
# Research Preflight Packet

## User Intent

## Sources Available

## Source Access Status

## Major Claims

## Assumptions / Unknowns

## Conflicts Or Tension

## Governing Frame

## Likely Misread

## Readiness To Route

## Verifier

## Human Gate

## Stop Conditions

## Recommended Next Move
```

## Packet 1: Intent-Bounded Run Packet

Use this when the work is ready for Codex, `/goal`, browser or computer use, manual pilot, or another execution surface.

```markdown
# Intent-Bounded Run Packet

## Human Intent

## Work Shape

## Recommended Surface

## Routing Rationale

## Scope Boundary

## Inputs

## Required Artifact

## Verifier

## Human Gate

## Stop Conditions

## Return Format
```

## Packet 2: Completion Reconciliation Packet

Use this when Codex or another execution surface returns output.

```markdown
# Completion Reconciliation Packet

## Original Intent

## Run Outcome

## Artifact Produced

## Evidence And Verification

## Files / Systems Touched

## Decisions Made

## Open Risks

## Human Review Needed

## Verifier

## Human Gate

## Stop Conditions

## Memory Candidates

## Recommended Next Loop
```

## Packet 3: Memory Banking Decision

Use this when a loop produced reusable learning.

```markdown
# Memory Banking Decision

## What Happened

## What Learning May Survive

## Best Home

## Candidate Vs Approved

## Approval Owner

## Promotion Gate

## Next Review Point
```

## Router Rules

| Input Condition | DDA Action | Route | Required Artifact | Gate |
|---|---|---|---|---|
| Messy source stack. | Run preflight. | DDA. | Research Preflight Packet. | Do not execute yet. |
| Clear bounded repo task. | Build run packet. | Codex. | Intent-Bounded Run Packet. | Approval before writes if not already granted, including repo-local markdown writes. |
| Returned Codex output. | Reconcile. | DDA. | Completion Reconciliation Packet. | Do not treat as accepted automatically. |
| Reusable pattern found. | Evaluate packaging. | DDA. | Skill or automation candidate review. | Approval before creating. |
| Repeated manual workflow. | Prove manually. | DDA/manual. | Pilot evidence log. | No automation until stable. |
| External-facing draft needed. | Pre-stage. | DDA. | Slack, Linear, Notion, or email draft. | Human send, post, or create gate. |
| No verifier exists. | Pause. | Human-only. | Decision note. | Define verifier first. |

## Write Boundaries

Do not perform or claim any of these actions unless the human explicitly approves that specific action:

- External writes to Slack, Notion, Linear, Gmail, GitHub, or memory.
- Automation creation, enabling, or scheduling.
- Commits, pushes, pull requests, or merges.
- Runtime-readiness claims.
- Canonical PRD, `AGENTS.md`, template, source-of-truth, or agent-source changes.
- Treating Codex output as accepted without reconciliation.

The skill may recommend these only as gated next steps.

## Relationship To Existing Skills

Keep this separate from `skills/dda-evidence-decision-review/`.

`dda-evidence-decision-review` reviews evidence into decision packets. `dda-codex-intent-router` routes intent and workflow shape before or after execution. It may route transcript or proof-boundary work into the evidence decision review skill, but it should not absorb that skill's packet shape.

## Future Split Criteria

Extract a mode into its own skill only when all are true:

1. It has been used successfully in at least three real tasks.
2. Its trigger is stable.
3. Its inputs are stable.
4. Its output packet is stable.
5. Its verifier is stable.
6. Splitting it would reduce context load or improve execution reliability.

Likely future split order:

- `dda-research-preflight`
- `dda-run-packet-builder`
- `dda-completion-reconciler`

Do not split `dda-memory-banking-decision` early because it carries the highest approval risk.

## Done-When

The router run is complete only when:

- The selected mode is named.
- The workloop fields are filled or the missing fields are named.
- The recommended route is the smallest safe next surface.
- The output includes artifact, verifier, human gate, and stop conditions.
- Memory, skill, automation, canon, and runtime items are labeled candidate-only unless explicitly approved.
- External writes remain blocked unless the human has approved the exact write.
- The final response names files created or changed and states verification performed or skipped.
