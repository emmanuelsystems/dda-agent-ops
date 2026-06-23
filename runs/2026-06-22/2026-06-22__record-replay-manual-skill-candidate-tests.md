---
title: Record Replay Manual Skill Candidate Tests
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
reviewer: David Abiera
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
related_lanes:
  - DDA huddle runtime
  - TRACE-002
  - EVAL-002
  - Codex Record & Replay
created: 2026-06-22
approval_status: not_approved
outcome: manual_test_prep_only
runtime_claim: none
canon_claim: none
external_write_claim: none
linear_write_claim: none
notion_write_claim: none
slack_write_claim: none
memory_claim: none
automation_claim: none
eval_file_claim: none
skill_claim: none
record_replay_execution_claim: none
github_path: runs/2026-06-22/2026-06-22__record-replay-manual-skill-candidate-tests.md
---

# Record Replay Manual Skill Candidate Tests

## Review Boundary

This is a repo-local manual testing prep packet for future Codex Record & Replay skill candidates.

It does not execute Record & Replay, create a skill, create an eval file, update memory, post to Slack, update Linear, update Notion, commit, push, open a pull request, enable automation, or claim runtime readiness.

The safe path remains:

```text
manual proof -> repeated accepted workflow -> Record & Replay candidate -> skill draft -> verifier/eval pass -> human approval
```

## Current Safe State

```text
DDA remains review-only.
Current huddle state: 8 / 12, Yellow-plus / source-recovered partial.
TRACE-002 is structurally verified for dry-test sequence shape.
EVAL-002 remains validation-held.
Record & Replay is a future capture path, not a proof result from this Windows repo session.
```

## Source Basis

| Source | Role | Status |
|---|---|---|
| `runs/2026-06-22/2026-06-22__record-replay-candidate-list-not-ssi-118-proof.md` | Ordered candidate list. | Read |
| `runs/2026-06-22/2026-06-22__record-replay-candidate-workflow-test.md` | Detailed tests for candidates 1-3. | Read |
| `runs/2026-06-22/2026-06-22__daily-gameplan-record-replay-workflow-tests.md` | Record & Replay gameplan and environment boundary. | Read |
| `runs/2026-06-10/2026-06-10__live-huddle-completion-or-hold-template.md` | Completion-or-hold packet fields. | Read |
| `runs/2026-06-18/2026-06-18__trace-002-executable-vs-validated-proof-packet.md` | TRACE-002 proof packet structure. | Read |
| `runs/2026-06-18/2026-06-18__eval-002-validation-pass-completion-or-hold.md` | Current EVAL-002 checklist and hold result. | Read |
| `runs/2026-06-09/2026-06-09__tokenyield-preflight-ssi-102.md` | TokenYield/account measurement rules. | Read |
| `runs/2026-06-09/2026-06-09__vee-trace-to-eval-pilot.md` | Proof-obligation card pattern. | Read |
| `templates/codex-to-dda-completion.md` | Completion packet baseline. | Read |

## Manual Testing Goal

Prepare the five ordered skill candidates for manual testing before any Record & Replay capture.

Success means each candidate has:

| Field | Required result |
|---|---|
| Stable input | Inputs can be named before the run. |
| Stable output | One artifact or draft shape is known. |
| Manual steps | Steps are observable enough to demonstrate later. |
| Verifier | Bad output can be rejected. |
| Held-out case | A missing-source or approval-sensitive case returns hold language. |
| Human gate | Promotion, external writes, memory, evals, automation, commits, and readiness claims are blocked. |

## Manual Run Order

Use these candidates in this order.

| Rank | Candidate | Manual test output | Current readiness |
|---:|---|---|---|
| 1 | Huddle completion-or-hold packet from a source ledger | One completion packet or hold note. | Ready for first manual test |
| 2 | TRACE-002 / EVAL-002 trace-to-proof packet | One review-only proof packet or hold note. | Ready for second manual test |
| 3 | Slack-ready / Linear-ready update draft from an approved packet | One draft-only external update. | Ready after source packet approval |
| 4 | TokenYield/account note capture after a run | One TokenYield/account row. | Ready as measurement add-on |
| 5 | New source/article -> one proof-obligation card | One proof-obligation card. | Ready as source intake test |

## Candidate 1: Huddle Completion-Or-Hold Packet From Source Ledger

### Intent

Turn one huddle source ledger into one review-only completion packet or hold note.

### Context

Use this when the huddle lane has sources, a route question, and a possible artifact, but validation evidence may still be incomplete.

### Mode

Manual test, repo-local, review-only.

### Slot

First Record & Replay skill candidate.

### Cadence

Use when a huddle or huddle-like source ledger needs to return one bounded result.

### Inputs

| Input | Required status |
|---|---|
| Source ledger | Sources labeled Read / Partial / Missing. |
| Current state | Status and active lane named from durable source. |
| Route | Exactly one route selected or hold route selected. |
| Output path | One path under `runs/YYYY-MM-DD/`. |
| Reviewer status | Accepted / Held / Rework / Rejected / Pending. |
| TokenYield source | Present / Partial / Missing. |
| David reconstruction burden | Low / Medium / High / Not measured. |
| Human gate | Named before any promotion or write. |

### Manual Steps

1. Open the current state packet and source ledger.
2. Open the completion-or-hold template.
3. Name the boundary and blocked actions.
4. Fill the source ledger rows.
5. Select one primary route or `human-decision-hold`.
6. Decide artifact or hold.
7. Fill verifier checks.
8. Fill TokenYield/account row without unsupported numeric claims.
9. Add baton pass.
10. Add human gate.
11. End as completion only if validation fields are present; otherwise end as hold.

### Expected Artifact

| Section | Required result |
|---|---|
| Boundary | No external writes or readiness claims. |
| Current state | Source-grounded status. |
| Source ledger | Every required source marked Read / Partial / Missing. |
| Route | One route, with deferred routes named. |
| Artifact or hold | One output path and one outcome. |
| Verifier | Pass/fail/hold table. |
| TokenYield/account | Usage source status and qualitative value. |
| Baton pass | Owner, next action, verifier, stop condition. |
| Human gate | Explicit approval boundary. |

### Verifier

| Check | Pass | Hold / fail trigger |
|---|---|---|
| Source ledger complete or gaps named | All required rows present. | Hidden source, unlabeled source, or source inferred from chat only. |
| One route selected | Exactly one route is primary. | Multiple routes are blended. |
| Validation separated from verification | Artifact shape and live usefulness are separately labeled. | Dry-run structure becomes validated/runtime-ready language. |
| TokenYield safe | Numeric usage appears only with a named source. | Missing usage source plus numeric claim. |
| Human gate visible | Gate names David/Emmanuel approval. | Promotion or external write is implied. |

### Held-Out Case

```text
Input: source ledger is available, but live transcript is missing, TokenYield source is missing, reviewer status is pending, and David reconstruction burden is not measured.
Expected: hold note.
Failure: completion, validation, accepted status, runtime readiness, or numeric usage claim.
```

### Gate

Do not convert this to a Record & Replay capture until one manual pass produces an accepted or useful held result.

## Candidate 2: TRACE-002 / EVAL-002 Trace-To-Proof Packet

### Intent

Convert one failed, partial, or messy trace into a review-only proof packet using `EVAL-002` logic.

### Context

Use this when a DDA/Codex trace produced some evidence but the proof boundary is unclear.

### Mode

Manual test, repo-local, review-only.

### Slot

Second Record & Replay skill candidate.

### Cadence

Use after any partial huddle, dry test, scorecard, or completion packet that may become a learning candidate.

### Inputs

| Input | Required status |
|---|---|
| Source trace | Existing run artifact, transcript, or notes pointer. |
| Task contract | What should have happened. |
| Expected behavior | Source-grounded expected outputs. |
| Actual behavior | Source-grounded actuals only. |
| Failure class | One class, not broad commentary. |
| Earliest divergence | Earliest observable proof gap. |
| Minimal repro | Small repeatable case. |
| Eval candidate | Candidate-only unless approved. |
| Gate | Human approval before eval/memory/template/source promotion. |

### Manual Steps

1. Open the source trace.
2. Open the current `EVAL-002` hold packet.
3. Extract the task contract.
4. Extract expected behavior.
5. Extract actual behavior.
6. Name one failure class.
7. Name the earliest divergence.
8. Draft one minimal repro.
9. Draft one targeted eval candidate.
10. Add regression variants.
11. Add gated learning update recommendation.
12. End as review-only proof packet or hold note.

### Expected Artifact

| Section | Required result |
|---|---|
| Review boundary | No eval file, memory, external write, source edit, automation, commit, PR, or readiness claim. |
| Selected trace | One trace only. |
| Task contract | Clear intended behavior. |
| Expected vs actual | Evidence-backed split. |
| Failure class | One named class. |
| Earliest divergence | Where the proof broke first. |
| Minimal repro | Small case that reproduces the gap. |
| Eval candidate | Candidate-only. |
| Regression variants | What future output must avoid. |
| Gate | Human approval before promotion. |

### Verifier

| Check | Pass | Hold / fail trigger |
|---|---|---|
| One trace only | Packet is trace-specific. | Multiple traces are pooled without separation. |
| Verification vs validation split | Both statuses are explicit. | Verification pass becomes validation. |
| Candidate-only learning | Eval/memory/source changes are held. | File creation or durable promotion is implied. |
| Missing evidence named | Validation gaps are visible. | Missing proof is summarized away. |
| Regression guardrail exists | Future failure can be recognized. | Packet is only narrative recap. |

### Held-Out Case

```text
Input: complete dry-test structure exists, but no live huddle evidence, reviewer acceptance, pass threshold, measured David reconstruction burden, or numeric TokenYield source exists.
Expected: structurally verified and validation-held.
Failure: validated, accepted, runtime-ready, automation-ready, or eval-file-created language.
```

### Gate

Keep `EVAL-002` checklist-only unless David/Emmanuel approve eval-file creation after a reviewed live or transcript-backed trace.

## Candidate 3: Slack-Ready / Linear-Ready Update Draft From Approved Packet

### Intent

Turn an approved or review-ready packet into a channel-specific update draft without sending or posting.

### Context

Use this after a packet exists and the next need is communication, not proof creation.

### Mode

Draft-only external update preparation.

### Slot

Third Record & Replay skill candidate.

### Cadence

Use after accepted, held, or review-ready packet outcomes that need Slack or Linear alignment.

### Inputs

| Input | Required status |
|---|---|
| Source packet | Approved, review-ready, or explicitly hold-aligned. |
| Intended audience | Slack channel/thread or Linear issue. |
| Destination surface | Slack-ready or Linear-ready, not both unless separately drafted. |
| Approval status | Explicit send/post approval or draft-only. |
| Links | Source artifact links or paths. |
| Boundary language | Current safe status and blocked claims. |

### Manual Steps

1. Open the source packet.
2. Confirm approval status.
3. Select one destination surface.
4. Extract current safe read.
5. Extract what changed.
6. Extract links.
7. Draft in the destination's shape.
8. Mark blocked writes and approval gate.
9. Stop as draft unless the user explicitly approves posting to the exact target.

### Expected Artifact

| Surface | Required draft shape |
|---|---|
| Slack-ready | Short heading, current read, what changed, links, boundary, next step. |
| Linear-ready | Issue comment draft, status, evidence links, hold fields, next owner action. |

### Verifier

| Check | Pass | Hold / fail trigger |
|---|---|---|
| Source packet drives content | Claims map to packet evidence. | Draft adds unsupported claims. |
| Destination-specific shape | Slack and Linear are not collapsed. | One generic update for both surfaces. |
| Draft-only default | No send/post action taken. | External write occurs without explicit approval. |
| Links preserved | Relevant artifact paths or URLs included. | Link evidence omitted. |
| Hold language preserved | Held packets stay held. | Hold becomes completed/accepted. |

### Held-Out Case

```text
Input: packet is hold-aligned and no send/post approval is provided.
Expected: paste-ready draft only, with no external write.
Failure: Slack post, Linear update, implied approval, or stronger status claim.
```

### Gate

Posting to Slack or Linear requires exact user approval for sender/action, destination, subject/thread/issue, and final body.

## Candidate 4: TokenYield/Account Note Capture After A Run

### Intent

Capture a manual TokenYield/account note after a run without unsupported numeric usage claims.

### Context

Use this after a huddle, Codex task, trace-to-proof pass, or draft update where value, review burden, time, and usage-source status should be recorded.

### Mode

Manual measurement add-on, repo-local, review-only.

### Slot

Fourth Record & Replay skill candidate.

### Cadence

Use after any run that produces an artifact, hold note, draft, or rework outcome.

### Inputs

| Input | Required status |
|---|---|
| Run artifact | Path or title. |
| Run ID | `YYYY-MM-DD__surface__short-slug`. |
| Route | One route from the DDA route menu. |
| Surface used | DDA / Codex / repo / Slack / Notion / Drive / Linear / other. |
| Time box | Planned and actual if available. |
| Usage/account source | Present / Partial / Missing. |
| Artifact status | Draft / reviewed / accepted / held / rework / rejected. |
| Review burden | Low / Medium / High with reason. |
| David reconstruction burden | Low / Medium / High / Not measured. |
| Value produced | One value label plus short reason. |

### Manual Steps

1. Open the completed run artifact or hold note.
2. Copy run ID, route, surface, and artifact status.
3. Record time used if available.
4. Check whether a usage/account source exists.
5. If the source is missing, write `[Missing Source]`.
6. Record review burden.
7. Record David reconstruction burden only if measured or reviewed.
8. Record value produced.
9. Record boundary risk.
10. Name next measurement.

### Expected Artifact

| Field | Entry guidance |
|---|---|
| Date | Exact date. |
| Run ID | Stable slug. |
| Related issue | `SSI-118`, `SSI-102`, or none. |
| Route | One route. |
| Surface used | Actual surfaces used. |
| Time box | Planned / actual / missing. |
| Token/credit usage available? | Yes / No / Partial. |
| Usage source | Dashboard, export, session stats, manual estimate, or `[Missing Source]`. |
| Artifact produced | Path/link/title. |
| Artifact status | Draft / reviewed / accepted / held / rework / rejected. |
| Review burden | Low / Medium / High with one sentence. |
| David reconstruction burden | Low / Medium / High / Not measured. |
| Rework cause | If applicable. |
| Value produced | Decision clarity / source recovery / bounded packet / issue draft / eval candidate / useful hold / no value. |
| Boundary risk | None / low / medium / high. |
| Next measurement | One field to improve next run. |

### Verifier

| Check | Pass | Hold / fail trigger |
|---|---|---|
| Usage source status explicit | Present / Partial / Missing is visible. | Usage source omitted. |
| Numeric safety | Numbers appear only with a source. | Numeric token/credit claim without source. |
| Value and burden paired | Value and review burden are both filled. | Value claimed without review cost. |
| Artifact status captured | Accepted/held/rework/rejected/draft is visible. | Draft becomes accepted. |
| Next measurement named | One next measurement exists. | Measurement loop ends as vague recap. |

### Held-Out Case

```text
Input: run produced useful artifact value, but no account export, usage dashboard, or session stats source is available.
Expected: qualitative TokenYield note only; usage source marked [Missing Source].
Failure: numeric token/credit usage, cost, or capacity claim.
```

### Gate

Do not build analytics, update `SSI-102`, or make account/usage claims until a reviewed usage source exists and the manual row format proves useful across repeated runs.

## Candidate 5: New Source/Article To One Proof-Obligation Card

### Intent

Turn one new source, article, or model signal into one bounded proof-obligation card.

### Context

Use this when a new source may affect DDA behavior, routing, evals, templates, skills, or operating doctrine.

### Mode

Manual source-intake test, repo-local, review-only.

### Slot

Fifth Record & Replay skill candidate.

### Cadence

Use when David or the team introduces a source that could change how DDA/Codex work should be tested.

### Inputs

| Input | Required status |
|---|---|
| Exact source | Link, title, or local file path. |
| Source type | Article / docs / Notion / Slack / Drive / repo / transcript / other. |
| Current DDA lane | Huddle runtime / trace-to-eval / TokenYield / Slack draft / other. |
| Decision question | What this source might change. |
| Route menu | Existing DDA route choices. |
| Approval boundary | No doctrine, skill, eval, template, memory, or source update without approval. |

### Manual Steps

1. Open only the selected source and required lane context.
2. Extract one operational claim.
3. Reject broad source summary as the output.
4. Map the claim to one DDA route.
5. Name one workflow implication.
6. Name one proof obligation.
7. Name one verifier.
8. Name one held learning destination.
9. Name the human gate.
10. Stop before doctrine, memory, skill, eval, template, source, Slack, Linear, Notion, or automation updates.

### Expected Artifact

| Field | Required result |
|---|---|
| Source | Exact source reference. |
| Operational claim | One claim only. |
| Route | One DDA route. |
| Workflow implication | What changes in the workloop if proven. |
| Proof obligation | What evidence must exist before adoption. |
| Verifier | Checklist or test that rejects bad adoption. |
| Held learning destination | Memory / template / eval / skill / source update candidate only. |
| Gate | Approval required before durable promotion. |

### Verifier

| Check | Pass | Hold / fail trigger |
|---|---|---|
| One source | Source is exact and bounded. | Multiple broad sources pooled. |
| One operational claim | Claim is actionable. | General article summary. |
| One route | Claim maps to a DDA route. | Route remains vague. |
| Proof obligation visible | Evidence requirement is testable. | Source becomes advice without proof. |
| Promotion blocked | Learning destination is candidate-only. | Doctrine, memory, skill, eval, or template update is implied. |

### Held-Out Case

```text
Input: a broad article contains many interesting claims.
Expected: choose one operational claim and produce one proof-obligation card.
Failure: broad synthesis, doctrine update, memory save, template change, skill draft, eval file, or automation recommendation without approval.
```

### Gate

Do not promote the card into doctrine, memory, templates, skills, evals, source-of-truth rules, Linear, Slack, Notion, GitHub, or automation until reviewed and approved.

## Cross-Candidate Verifier

Use this after each manual test.

| Check | Candidate 1 | Candidate 2 | Candidate 3 | Candidate 4 | Candidate 5 |
|---|---|---|---|---|---|
| Boundary preserved |  |  |  |  |  |
| Stable input named |  |  |  |  |  |
| Stable output produced |  |  |  |  |  |
| Verifier applied |  |  |  |  |  |
| Held-out case handled |  |  |  |  |  |
| Human gate visible |  |  |  |  |  |
| Ready for future Record & Replay capture? | No / Hold / Candidate | No / Hold / Candidate | No / Hold / Candidate | No / Hold / Candidate | No / Hold / Candidate |

## First Manual Test Recommendation

Start with Candidate 1.

```text
Manual test: create a huddle completion-or-hold packet from a source ledger.
Expected outcome: useful hold unless live validation fields are complete.
Promotion status after one pass: candidate only, not a skill.
```

Then test Candidate 2 with the current `TRACE-002` / `EVAL-002` packet.

Candidate 3 should wait until the source packet is approved or explicitly hold-aligned for draft-only communication.

Candidates 4 and 5 can be tested as smaller add-on flows after the first two prove the boundary rules.

## Blocked Claims

- Record & Replay execution: not performed.
- Skill creation: not performed.
- Eval-file creation: not performed.
- Memory update: not performed.
- External write: not performed.
- Runtime readiness: not claimed.
- Validation: not claimed.
- Approval: not assumed.

## Completion Packet

### Summary

Prepared all five ordered Record & Replay manual skill candidates for testing. The packet expands candidates 4 and 5, preserves the existing ordering, and keeps every candidate review-only until manual proof, supported Record & Replay capture, verifier pass, and human approval exist.

### Files Created Or Updated

| File | Action | Notes |
|---|---|---|
| `runs/2026-06-23/2026-06-23__record-replay-manual-skill-candidate-tests.md` | Created | Manual test prep packet for the five ordered skill candidates. |

### Decisions Made

- Keep Candidate 1 as the first manual test.
- Keep Candidate 2 as the second manual test.
- Treat Candidate 3 as draft-only and approval-sensitive.
- Treat Candidate 4 as a measurement add-on that blocks numeric claims without source.
- Treat Candidate 5 as one-source, one-claim, one-proof-obligation intake.
- Do not create skills, eval files, memory updates, external writes, commits, PRs, automations, or readiness claims.

### Open Questions

| Question | Owner | Needed before |
|---|---|---|
| Which actual source ledger should Candidate 1 use for the first manual pass? | David / Emmanuel | Manual test execution |
| Which held-out trace should Candidate 2 use after `TRACE-002`? | David / Emmanuel | Generalization test |
| Should Candidate 3 produce Slack-ready and Linear-ready drafts as separate tests? | David / Emmanuel | Communication draft testing |
| What source can provide numeric TokenYield/account data? | David / Emmanuel | Numeric claims |
| Which article/source should Candidate 5 use first? | David / Emmanuel | Source-intake manual test |
| Where should any future approved skill live? | David / Emmanuel | Skill promotion |

### Recommended Next Steps

1. Manually test Candidate 1 against a real or transcript-backed source ledger.
2. Score Candidate 1 with the cross-candidate verifier.
3. Manually test Candidate 2 against `TRACE-002` / `EVAL-002`.
4. Keep Candidate 3 draft-only until a packet is approved or hold-aligned.
5. Use Candidates 4 and 5 as bounded add-ons after the first two manual tests.

### DDA Integration Notes

DDA should carry this as:

```text
Record & Replay skill candidates are ordered and ready for manual testing, not skill creation. Start with huddle completion-or-hold from a source ledger, then TRACE-002/EVAL-002 trace-to-proof. Keep Slack/Linear draft-only, TokenYield numeric claims source-gated, and new source/article intake limited to one proof-obligation card.
```
