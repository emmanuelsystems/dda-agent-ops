---
title: DDA Codex Intent Router Skill Plan
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
related_method_lane: ATDL
github_path: runs/2026-05-25/dda-codex-intent-router-skill-plan.md
created: 2026-05-25
updated: 2026-05-25
approval_status: not_approved
runtime_claim: none
canon_claim: none
external_write_claim: none
---

# DDA Codex Intent Router Skill Plan

## Review Boundary

This is a draft/review-only run artifact. It captures the decision review and implementation plan for a future `dda-codex-intent-router` skill.

This artifact does not approve:

- creating the skill
- updating `AGENTS.md`
- updating PRD, app-flow, instructions, templates, or evals
- updating Notion, Slack, Linear, Gmail, GitHub, or persistent memory
- creating or enabling automations
- commits, pushes, pull requests, or merges
- runtime readiness or canonical promotion

## Decision

Build `dda-codex-intent-router` as one umbrella skill with explicit modes first.

Do not create multiple smaller skills yet.

The skill should preserve the full operating sequence:

```text
research preflight
-> routing
-> bounded run packet
-> completion reconciliation
-> memory banking decision
```

Separate mode-specific skills should be extracted only after repeated manual runs prove stable triggers, stable inputs, stable outputs, and stable validation rules.

## Why One Umbrella Skill First

The riskiest failure is not that each sub-skill is imperfect. The riskiest failure is that DDA loses the sequence:

- preflight before routing
- routing before execution
- reconciliation before memory
- approval gates before external writes, automation, canon, or runtime claims

One umbrella skill keeps the governing router logic visible while the workflow is still stabilizing. A thin router plus many small skills may become cleaner later, but it is premature before the manual pilots prove which modes deserve extraction.

## Implementation Target

When approved later, create the skill as a repo-local draft skill under:

```text
skills/dda-codex-intent-router/
```

Expected files:

```text
skills/dda-codex-intent-router/SKILL.md
skills/dda-codex-intent-router/agents/openai.yaml
```

Also update:

```text
skills/README.md
```

The README update should only list the new draft skill and state that it is review-only.

## Skill Scope

The skill should trigger when Codex needs to turn messy DDA / Systems Shaper intent into a safe execution route, especially when the work involves:

- Notion context
- Codex handoffs
- workflow design
- skill candidates
- automation candidates
- memory candidates
- completion review
- source-heavy planning
- DDA / ATDL proof boundaries

The skill should not trigger for simple one-off answers that do not need source stabilization, routing, execution planning, or memory decisions.

## Recommended Skill Metadata

```yaml
---
name: dda-codex-intent-router
description: Stabilize messy DDA or Systems Shaper intent, classify work shape, route to the smallest safe execution surface, create bounded run packets, reconcile completion outputs, and identify memory or skill candidates without making external writes, automation, runtime-readiness, or canon claims.
---
```

## Skill Modes

| Situation | Mode |
|---|---|
| Messy sources, unclear claims, doctrine/research implications. | Research Preflight Mode |
| User wants to decide where work should go. | Intent Router Mode |
| Work is ready for Codex or another execution surface. | Run Packet Mode |
| Codex or another agent returned output. | Completion Reconciliation Mode |
| Learning may need to survive. | Memory Banking Mode |

## Required Workloop Fields

The skill must preserve these fields whenever routing work:

```text
intent
context
mode
slot
cadence
artifact
verifier
memory
gate
learning update
```

## Packet Interfaces

### Packet 0: Research Preflight Packet

Use when inputs are source-heavy, ambiguous, strategic, doctrine-related, or likely to be distorted if routed too early.

```text
User intent
Sources available
Source access status
Major claims
Assumptions / unknowns
Conflicts or tension
Governing frame
Likely misread
Readiness to route
Recommended next move
```

### Packet 1: Intent-Bounded Run Packet

Use when the work is ready for Codex, `/goal`, browser/computer use, manual pilot, or another execution surface.

```text
Human intent
Work shape
Recommended surface
Routing rationale
Scope boundary
Inputs
Required artifact
Verifier
Human gate
Stop conditions
Return format
```

### Packet 2: Completion Reconciliation Packet

Use when Codex or another execution surface returns output.

```text
Original intent
Run outcome
Artifact produced
Evidence and verification
Files / systems touched
Decisions made
Open risks
Human review needed
Memory candidates
Recommended next loop
```

### Packet 3: Memory Banking Decision

Use when a loop produced reusable learning.

```text
What happened
What learning may survive
Best home
Candidate vs approved
Approval owner
Promotion gate
Next review point
```

## Router Rules

| Input Condition | DDA Action | Route | Required Artifact | Gate |
|---|---|---|---|---|
| Messy source stack. | Run preflight. | DDA. | Research Preflight Packet. | Do not execute yet. |
| Clear bounded repo task. | Build run packet. | Codex. | Intent-Bounded Run Packet. | Approval before writes if not already granted. |
| Returned Codex output. | Reconcile. | DDA. | Completion Reconciliation Packet. | Do not treat as accepted automatically. |
| Reusable pattern found. | Evaluate packaging. | DDA. | Skill/automation candidate review. | Approval before creating. |
| Repeated manual workflow. | Prove manually. | DDA/manual. | Pilot evidence log. | No automation until stable. |
| External-facing draft needed. | Pre-stage. | DDA. | Slack/Linear/Notion/email draft. | Human send/post/create gate. |
| No verifier exists. | Pause. | Human-only. | Decision note. | Define verifier first. |

## Write Boundaries

The future skill must explicitly block:

- external writes to Slack, Notion, Linear, Gmail, GitHub, or memory
- automation creation or enablement
- commits, pushes, pull requests, or merges
- runtime-readiness claims
- canonical PRD, `AGENTS.md`, or source-of-truth changes
- treating Codex output as accepted without reconciliation

The skill may recommend these actions only as gated next steps.

## Relationship To Existing Skill

Existing skill:

```text
skills/dda-evidence-decision-review/
```

Keep it separate.

Reason:

- `dda-evidence-decision-review` is evidence-review specific.
- `dda-codex-intent-router` is routing/workflow specific.

The intent-router skill may route a transcript or proof-boundary task into the evidence-decision-review skill, but it should not absorb that skill's full packet shape.

## Future Split Criteria

Only split a mode into its own skill when all are true:

1. It has been used successfully in at least 3 real tasks.
2. Its trigger is stable.
3. Its inputs are stable.
4. Its output packet is stable.
5. Its verifier is stable.
6. Splitting it would reduce context load or improve execution reliability.

Likely future split order:

```text
dda-research-preflight
dda-run-packet-builder
dda-completion-reconciler
```

Do not split `dda-memory-banking-decision` early because it carries the highest approval risk.

## Test Plan

Validate with three manual scenarios before treating the skill as usable:

1. Messy Notion context.
   - Confirms Research Preflight runs before routing.
2. Bounded repo-doc task.
   - Confirms Run Packet Mode produces scope, artifact, verifier, gate, and stop conditions.
3. Returned Codex output.
   - Confirms Completion Reconciliation Mode separates evidence, risks, memory candidates, and next loop.

Acceptance criteria:

- Correct mode chosen for each scenario.
- No premature execution route when source context is unstable.
- Every output includes verifier and human gate.
- Memory is labeled candidate only.
- External writes and automation remain blocked unless explicitly approved.
- The result is useful enough for DDA or another Codex thread to act on without inventing missing decisions.

## Assumptions

- The first implementation target is a repo-local draft skill under `F:\Codex Projects\dda-agent-ops\skills`, not a global Codex user skill.
- The first version is documentation/instruction only; no helper scripts are needed.
- Existing `dda-evidence-decision-review` remains separate.
- Mode-based umbrella skill is the default until 3-5 real uses show which modes deserve extraction.

## Recommended Next Step

If this plan is accepted, the next bounded implementation packet should be:

```text
Create draft repo-local skill: skills/dda-codex-intent-router/
```

That implementation should be limited to:

- `skills/dda-codex-intent-router/SKILL.md`
- `skills/dda-codex-intent-router/agents/openai.yaml`
- `skills/README.md`

No other repo source files should be changed in the same pass.
