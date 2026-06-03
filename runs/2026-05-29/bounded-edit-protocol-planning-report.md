---
title: Bounded Edit Protocol Planning Report
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
related_method_lane: ATDL
related_issue: SSI-118
created: 2026-05-29
approval_status: not_approved
runtime_claim: none
canon_claim: none
external_write_claim: none
memory_claim: none
automation_claim: none
implementation_claim: none
---

# Bounded Edit Protocol Planning Report

## Review Boundary

This is a report-first planning artifact.

It does not approve:

- runtime skill edits
- `AGENTS.md` changes
- PRD, app-flow, template, or eval changes
- Notion updates
- Slack or Linear posts
- persistent memory saves
- automation creation or enablement
- commits, pushes, pull requests, or merges
- canon promotion
- treating DDA Pilot 001 evidence as system doctrine
- implementing `continuity-snapshot`

Codex remains report-first for this work unless a later human approval grants a specific docs-only or repo-edit implementation scope.

## Task Summary

The current task is to clarify how a SkillOpt-style bounded edit process should be represented in the SSI AI Operating Base / DDA planning system before any implementation.

The desired move is from:

```text
agent notices a skill or doc seems wrong
-> agent rewrites the file
```

to:

```text
evidence batch
-> scored failure pattern
-> bounded edit candidate packet
-> held-out validation / review
-> accepted candidate or rejected edit memory
```

The planning question is where this loop belongs, how it applies to a `continuity-snapshot` skill, and what artifact should be drafted next without crossing approval boundaries.

## Source Basis

| Source | Surface | How it was used |
|---|---|---|
| User-provided DDA to Codex handoff packet | Chat | Primary task scope and desired output. |
| `AGENTS.md` | Repo | Repo operating rule, approval boundaries, and DDA/Codex role split. |
| `runs/2026-05-25/dda-v2-intent-router-fit-test-and-operating-model.md` | Repo | Current DDA intent-router operating model and packet sequence. |
| `runs/2026-05-25/dda-codex-intent-router-skill-plan.md` | Repo | One-skill-with-modes decision and router scope. |
| `runs/2026-05-26/dda-codex-intent-router-skill-dry-run-results.md` | Repo | Review-only proof that the router draft can preserve preflight, run packet, and reconciliation boundaries. |
| `runs/2026-05-26/dda-codex-template-router-contract-audit.md` | Repo | Current template gap analysis against the router contract. |
| `runs/2026-05-27/ssi-113-blocker-reconciliation.md` | Repo | Current split between `SSI-113` blocker history and `SSI-118` intent-router review lane. |
| `skills/dda-codex-intent-router/SKILL.md` | Repo | Current local router procedure and packet definitions. |
| David SkillOpt / bounded-context-state update | Slack / user context | Current strategic input: markdown skills and memory artifacts should evolve through bounded, verifier-gated state transitions. |
| DDA Pilot 001 Operating Contract + Router Matrix v0.2 | Notion / user context | Current planning contract: DDA is an evidence lane before it is a doctrine source. |

## Current Alignment

The bounded edit process fits the current DDA direction, but it should not be treated as a normal file-edit workflow.

It is better classified as a governed learning loop for agent-facing context state:

```text
observed failures
-> candidate improvement
-> validation
-> review gate
-> accepted candidate, rejected edit memory, or no-op
```

This supports the current DDA sequence:

```text
preflight before routing
-> routing before execution
-> reconciliation before memory
-> approval before external writes or canon claims
```

The important shift is that the unit of learning is not "the edited skill file." The unit of learning is the validated edit decision.

## Where This Belongs

| Layer | Role in bounded edits |
|---|---|
| DDA Pilot 001 | Can pilot the bounded edit loop as evidence and decision support. It should identify failure patterns, route candidate edit packets, and reconcile validation results. |
| ATDL | Should evaluate whether the bounded edit loop improves capability artifacts and preserves governance boundaries. |
| SSI AI Operating Base | Should hold the reusable protocol if it proves useful across DDA and at least one non-DDA case. |
| Operating Knowledge | Should hold slow-state principles only after review: e.g. how context state evolves, what gets protected, and what counts as validation. |
| Codex | Should draft reports, packets, docs-only proposals, or bounded repo edits only after explicit authorization. |
| Runtime skills / automations | Out of scope until manual evidence proves stable trigger, input, output, verifier, and gate behavior. |

Recommended classification:

```text
Authority class: decision-support / candidate operating protocol
Current home: DDA Pilot 001 evidence lane
Promotion path: Operating Base candidate only after repeated reviewed use
Implementation posture: report-first
```

## Main Recommendation

Represent the SkillOpt-style process as a new candidate packet type:

```text
Packet 4: Bounded Edit Candidate Packet
```

Do not add it to the approved DDA packet system yet.

Treat Packet 4 as a candidate extension to the existing packet sequence:

```text
Packet 0: Research Preflight Packet
Packet 1: Intent-Bounded Run Packet
Packet 2: Completion Reconciliation Packet
Packet 3: Memory / Authority Decision Packet
Packet 4: Bounded Edit Candidate Packet
```

Packet 4 should be used only when there is evidence that an agent-facing file, skill, template, memory rule, or operating doc needs improvement.

It should not be used as permission to edit the file.

## Packet 4: Bounded Edit Candidate Packet

### Purpose

Preserve a proposed context-state improvement as a reviewable candidate before any skill, doc, memory, or operating-knowledge file is changed.

### Required Fields

```markdown
# Bounded Edit Candidate Packet

## Target Artifact

## Current Authority Class

## Evidence Batch

## Failure Pattern

## Failure Score Or Severity

## Proposed Bounded Edit

## Edit Budget

## Protected Regions

## Source Anchors

## Verifier

## Held-Out Validation Cases

## Acceptance Rule

## Rejection Rule

## Rejected Edit Memory

## Human Gate

## Stop Conditions

## Candidate Vs Approved Status

## Recommended Next Loop
```

### Required Labels

Every Packet 4 must label the proposed change as one of:

- candidate edit
- accepted candidate
- rejected edit
- needs more evidence
- not worth changing
- out of scope
- requires authority decision

No Packet 4 should label an edit as approved doctrine, runtime-ready, or canonical unless that approval is explicitly granted by the human authority owner.

## Bounded Edit Protocol v0.1

### Step 1: Evidence Batch

Collect the smallest useful batch of evidence.

Examples:

- failed outputs
- user corrections
- repeated ambiguity
- stale source routing
- missed approval boundary
- low-quality handoff
- repeated overclaim
- missing verifier
- context recovery failure

Evidence must be source-anchored. Chat memory alone is not enough for durable conclusions.

### Step 2: Failure Pattern

Name the recurring failure in one sentence.

Good pattern:

```text
The skill retrieves current status but fails to separate merged baseline from active review work.
```

Weak pattern:

```text
The skill needs to be better.
```

### Step 3: Candidate Edit

Propose the smallest edit that could fix the failure.

The edit should be bounded by:

- target section
- exact behavioral intent
- maximum scope
- protected regions
- no-touch boundaries
- expected output change

### Step 4: Held-Out Validation

Test the candidate against cases not used to invent the edit.

For repo-local skills, held-out validation should include at least:

1. one prior failure or confusing case
2. one normal expected case
3. one boundary or adversarial case

### Step 5: Accept, Reject, Or Hold

Use strict decision rules:

- accept only if the edit improves the target behavior without damaging protected behavior
- reject ties
- reject if the edit widens scope
- reject if the edit weakens approval boundaries
- hold if evidence is insufficient
- log rejected edit memory as candidate-only evidence

### Step 6: Promotion Gate

Accepted candidates are not automatically canon.

Promotion requires the correct authority gate:

- DDA evidence lane review for DDA-local behavior
- ATDL review for capability artifact governance
- Operating Base review for shared protocol behavior
- Operating Knowledge review for slow-state doctrine
- repo approval for durable source changes

## Application To `continuity-snapshot`

### Current Concept

`continuity-snapshot` appears to be a candidate skill or workflow for recovering current truth and continuity across dense workstreams.

The likely job is not broad summary. It should help a fresh run recover:

- current durable baseline
- active lane
- latest reviewed decision
- open blockers
- proof status
- what changed since the last stable point
- what not to confuse
- next smallest action

### Fit With Existing DDA Work

`continuity-snapshot` should sit near the DDA intent-router, but it should not replace it.

Recommended relationship:

```text
continuity-snapshot = state recovery / current-truth reconstruction
dda-codex-intent-router = route the recovered state into the smallest safe next loop
bounded edit protocol = improve either skill only after failure evidence and validation
```

### First Packet 4 Example

```markdown
# Bounded Edit Candidate Packet

## Target Artifact

`continuity-snapshot` skill concept.

## Current Authority Class

Candidate skill / planning context. Not implemented. Not approved.

## Evidence Batch

Current DDA lane has repeated need to distinguish:

- `SSI-118` focused review surface
- `SSI-113` broader evidence lane
- DDA-local evidence vs Operating Base doctrine
- repo proof vs Slack/Notion intake
- review-only skill draft vs runtime-ready capability

## Failure Pattern

Continuity recovery can collapse adjacent surfaces into one storyline unless it explicitly separates baseline, active lane, proof status, and authority class.

## Proposed Bounded Edit

When drafting `continuity-snapshot`, include a required `Do Not Confuse` section and an `Authority Class` row for each major source or claim.

## Edit Budget

Planning only. No skill file creation yet.

## Protected Regions

- approval boundaries
- source-of-truth hierarchy
- candidate-vs-approved labels
- no external-write claims
- no automation claims
- no canon claims

## Source Anchors

- `AGENTS.md`
- `runs/2026-05-25/dda-v2-intent-router-fit-test-and-operating-model.md`
- `runs/2026-05-27/ssi-113-blocker-reconciliation.md`
- `skills/dda-codex-intent-router/SKILL.md`

## Verifier

A fresh reader can identify current baseline, active issue, active artifact, unresolved blockers, authority class, and next action without treating Slack or memory as durable truth.

## Held-Out Validation Cases

1. DDA `SSI-113` vs `SSI-118` lane split.
2. May 13 loop 003 proof blockers vs May 26 intent-router review progress.
3. A future non-DDA repo where merged baseline and active review branch differ.

## Acceptance Rule

Accept only if the draft skill improves current-truth recovery while preserving source hierarchy and approval gates.

## Rejection Rule

Reject if it becomes a generic summary skill, hides blockers, or treats candidate planning as canon.

## Human Gate

Human approval required before creating or editing any skill file.

## Stop Conditions

Stop if the target path, source priority, or verifier is not agreed.
```

## Artifact Options

| Option | Description | Pros | Risks | Recommendation |
|---|---|---|---|---|
| Add Packet 4 directly to `skills/dda-codex-intent-router/SKILL.md` | Make bounded edits part of the current router skill. | Keeps the loop in one place. | Premature; changes active skill behavior before validation. | Do not do yet. |
| Create a run artifact defining Packet 4 and protocol v0.1 | Preserve the planning contract as review-only evidence. | Low risk, reviewable, matches repo pattern. | Still needs later translation into templates or skills. | Recommended next artifact. |
| Create a template file now | Add `templates/bounded-edit-candidate-packet.md`. | Makes reuse easier. | Template promotion may imply more approval than exists. | Hold until report is reviewed. |
| Create `continuity-snapshot` skill now | Implement candidate skill. | Fast experimentation. | Too early; target path and verifier not settled. | Do not do yet. |
| Update Operating Knowledge / Notion now | Move principle into slow-state doctrine. | Captures strategic direction. | Premature canonization. | Do not do yet. |

## Recommended Next Artifact

Draft this next, if approved:

```text
runs/2026-05-29/bounded-edit-candidate-packet-v0.1.md
```

Purpose:

- define Packet 4 as a review-only packet
- include the `continuity-snapshot` example
- specify verifier and held-out validation rules
- preserve out-of-scope boundaries

Do not create a reusable template or skill until that packet is reviewed.

## New Context Needed Before Docs-Only Implementation

Before any docs-only implementation, gather:

1. Exact target for `continuity-snapshot`.
   - Is it a repo-local skill, global Codex skill, DDA artifact template, or Operating Base pattern?
2. Exact source links.
   - AI Operating Base / Operating Knowledge planning doc.
   - May 28 meeting notes.
   - SkillOpt paper or local notes.
   - Any continuity snapshot source note.
3. Authority owner.
   - Who can approve Packet 4 as DDA-local evidence?
   - Who can approve it as Operating Base candidate protocol?
4. Validation cases.
   - At least 2-3 held-out continuity failures or drift cases.
5. Target repository path.
   - Keep `F:\Codex Projects\dda-agent-ops` as the current planning repo unless another repo is explicitly approved.
6. Scope decision.
   - Report-only, run artifact, template, skill, or source-doc update.
7. Explicit implementation authorization.
   - Without this, Codex should not edit skills, templates, `AGENTS.md`, Notion, Linear, Slack, memory, or automations.

## Out Of Scope Until Explicit Approval

- creating `continuity-snapshot`
- editing `skills/dda-codex-intent-router/SKILL.md`
- editing templates
- editing `AGENTS.md`
- updating PRD, app-flow, instructions, evals, or source-of-truth docs
- writing to Notion, Linear, Slack, Gmail, GitHub, or memory
- creating automations, hooks, plugins, or runtime behavior
- declaring Packet 4 canonical
- treating SkillOpt as approved SSI doctrine
- accepting any bounded edit without held-out validation

## Decision Needed

Choose one next step:

1. Accept this report as the current planning read and draft `bounded-edit-candidate-packet-v0.1.md` as the next review-only run artifact.
2. Revise this report with more source links and the exact `continuity-snapshot` target before drafting Packet 4.
3. Hold Packet 4 and first review `a04d6e1` / `SSI-118` against the SkillOpt lens.

Recommended decision:

```text
Option 1, if the goal is to preserve momentum as report-first repo evidence.
Option 2, if the May 28 Operating Base / Operating Knowledge source should be primary before any next artifact.
```

## Codex To DDA Completion Packet

### Summary

Created a review-only planning report for representing SkillOpt-style bounded edits as a candidate Packet 4 process inside the DDA / SSI AI Operating Base planning lane.

### Files Created Or Updated

| File | Path | Notes |
|---|---|---|
| Bounded Edit Protocol Planning Report | `runs/2026-05-29/bounded-edit-protocol-planning-report.md` | New draft review-only run artifact. |

### Decisions Made

- Packet 4 should be treated as a candidate extension, not an approved part of the DDA packet system yet.
- `continuity-snapshot` should be used as an example case, not implemented yet.
- The bounded edit process belongs first as DDA-local evidence and Operating Base candidate protocol, not slow-state doctrine.

### Open Questions

- What is the exact target home for `continuity-snapshot`?
- Which May 28 Operating Base / Operating Knowledge source should be primary?
- Who approves Packet 4 as DDA-local evidence vs broader Operating Base candidate protocol?
- What held-out validation cases should be used first?

### Recommended Next Steps

1. Review this report against David's latest SkillOpt / Operating Base framing.
2. Fill the missing exact source links and target path for `continuity-snapshot`.
3. If accepted, draft `runs/2026-05-29/bounded-edit-candidate-packet-v0.1.md` as the next review-only artifact.

### DDA Integration Notes

DDA should treat this as candidate planning evidence only. It may inform a future Packet 4, template, or skill update, but it does not authorize edits, memory saves, automations, external writes, runtime behavior, or canon promotion.
