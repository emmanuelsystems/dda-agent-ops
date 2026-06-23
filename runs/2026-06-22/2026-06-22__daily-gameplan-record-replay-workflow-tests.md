---
title: Daily Gameplan - Record Replay Workflow Tests
date: 2026-06-22
status: draft
approval_status: not_approved
artifact_type: daily-gameplan
review_boundary: review-only
related_lanes:
  - DDA huddle runtime
  - TRACE-002
  - EVAL-002
  - Codex Record & Replay
---

# Daily Gameplan - Record Replay Workflow Tests

## Boundary

This is a repo-local, review-only gameplan.

It does not approve:

- Slack posts
- Notion, Linear, Gmail, Drive, or GitHub writes
- memory saves
- eval file creation
- automation creation
- skill promotion
- commits, pushes, or pull requests
- runtime-readiness, canon, or final DDA claims

## Current Safe State

```text
DDA remains review-only.
Current huddle state: 8 / 12, Yellow-plus / source-recovered partial.
TRACE-002 is verified for dry-test sequence structure.
EVAL-002 remains validation-held.
The next proof needs live or transcript-backed huddle evidence with reviewer status, pass threshold, measured David reconstruction burden, TokenYield source status, and human gate.
```

## Recent Updates To Carry Forward

| Update | Current meaning | Workflow consequence |
|---|---|---|
| June 18 TRACE-002 proof packet | Dry-test sequence is structurally verified but not live-validated. | Keep verified vs validated explicit. |
| June 18 EVAL-002 hold packet | Current result is hold, not completion. | Use EVAL-002 as a checklist, not an eval file yet. |
| June 18 connector intake | June 17 live-huddle workspace was surfaced, but available highlights still lacked TokenYield source and measured David burden. | Source identified; validation still held. |
| Codex Record & Replay | Codex can turn a demonstrated stable workflow into a reusable skill on supported macOS setups with Computer Use enabled. | Treat as a future skill-candidate path after manual workflow proof, not as automation today. |
| Codex skills guidance | Demonstrated workflows can become skills when the workflow is known and easier to show than describe. | Candidate workflows need stable steps, clear success criteria, and review gates before capture. |

Source links for Codex update:

- https://developers.openai.com/codex/record-and-replay
- https://developers.openai.com/codex/changelog
- https://developers.openai.com/codex/skills

## Today Main Goal

Select and dry-run a small set of DDA/Codex workflows that could later be tested with Codex Record & Replay.

The goal is not to create a skill today.

The goal is to identify which workflow is stable enough to record later, what inputs it needs, what output it should create, and what verifier would reject a bad replay.

## Workloop For Today

```text
intent -> context -> mode -> slot -> cadence -> artifact -> verifier -> memory -> gate -> learning update
```

Today's filled version:

| Workloop field | Entry |
|---|---|
| Intent | Identify Record & Replay candidate workflows for DDA/Codex use-case testing. |
| Context | June 18 TRACE-002/EVAL-002 hold state, June 16 scorecard, June 15 open-order review, Codex Record & Replay docs. |
| Mode | Review-only workflow selection and dry-run planning. |
| Slot | Today, 2026-06-22. |
| Cadence | One planning pass; no recurrence. |
| Artifact | This gameplan plus optional follow-up use-case test packet. |
| Verifier | Each candidate has stable steps, clear inputs, expected output, failure triggers, and human gate. |
| Memory | Candidate-only; no save. |
| Gate | David/Emmanuel approval before skill creation, replay capture, memory, eval, external write, or automation. |
| Learning update | Candidate workflow notes only after review. |

## Candidate Record & Replay Use Cases

| Rank | Candidate workflow | Why it is a good candidate | Replay risk | Today's test output |
|---:|---|---|---|---|
| 1 | Create a huddle completion-or-hold packet from a source ledger | Highly repeated, already has templates and verifier fields. | Replay may overclaim validation if live evidence is missing. | Dry-run checklist for one packet path and hold triggers. |
| 2 | Convert a trace into a proof packet using EVAL-002 | Directly matches the trace-to-eval lane and current proof gap. | Could create eval/memory/source updates too early. | Review-only source-to-proof card with no file promotion. |
| 3 | Draft a Slack-ready quick update from an approved completion packet | Useful repeated communication workflow. | Posting is approval-gated; replay must draft only. | Paste-ready draft shape, not sent. |
| 4 | Draft a Linear update from a reviewed repo packet | Useful for keeping owner surfaces aligned. | Linear write is approval-gated and issue ownership may be unclear. | Linear comment draft only. |
| 5 | Capture TokenYield/account note after a run | Repeated and measurable if fields are fixed. | Numeric usage source may be missing. | Qualitative TokenYield row with missing-source handling. |
| 6 | Article/source update to proof-obligation card | Useful when David shares new model/source context. | Broad synthesis may become doctrine. | One operational claim, one route, one verifier, one gate. |

## Recommended Focus For Today

Use three workflow tests, in this order:

1. Huddle completion-or-hold packet workflow.
2. Trace-to-proof packet workflow using EVAL-002.
3. Slack-ready update draft workflow, draft-only.

Reason:

These are closest to repeated real work, have explicit hold gates, and can be tested without external writes.

## Record & Replay Suitability Check

Before any workflow becomes a Record & Replay candidate, it must pass this table:

| Check | Pass condition | Hold trigger |
|---|---|---|
| Repetition | Workflow has happened or is expected to happen more than twice. | One-off exploratory task. |
| Stable inputs | Input sources can be named before the run. | Input source changes every time or requires hidden context. |
| Stable output | Output artifact shape is known. | Output destination or format is unclear. |
| Verifier | Bad output can be rejected by checklist or rubric. | Success depends only on subjective judgment. |
| Boundary | External writes and durable promotions are blocked unless approved. | Replay would post, update, save memory, create evals, or automate by default. |
| Environment | Record & Replay is available on the machine used for capture. | Current machine/session cannot run Record & Replay. |

## Important Environment Note

Record & Replay is a macOS Codex feature and requires Computer Use to be available and enabled. This current repo session is on Windows, so today's repo work should prepare workflow candidates and recording scripts, not claim that Record & Replay was executed here.

## Suggested Time Box

| Time box | Focus | Output |
|---:|---|---|
| 15 min | Re-open latest durable state. | Current state remains hold or is updated with evidence. |
| 20 min | Select one Record & Replay candidate. | Candidate row filled with inputs, output, verifier, gate. |
| 30 min | Dry-run the candidate manually. | Draft artifact or hold note. |
| 15 min | Score replay suitability. | Pass/hold table completed. |
| 15 min | Decide next action. | Record later, revise workflow, or hold. |

## Today's Success Criteria

Success means:

```text
One or more candidate workflows are ready for future Record & Replay testing, with source inputs, output shape, verifier, hold triggers, and human gate named.
```

Hold means:

```text
The workflow is still too unstable, source-dependent, or approval-sensitive to record.
```

## Open Questions

| Question | Owner | Needed before |
|---|---|---|
| Which machine/account will be used for actual Record & Replay capture? | Emmanuel | Any real recording attempt. |
| Is Computer Use enabled and eligible on that machine? | Emmanuel | Record & Replay execution. |
| Which workflow should be recorded first? | David / Emmanuel | Skill candidate selection. |
| Should the first captured workflow become a repo skill, user skill, or stay as a draft procedure? | David / Emmanuel | Skill promotion. |
| What held-out case should test whether replay generalizes? | David / Emmanuel | Skill acceptance. |

## Recommended Next Step

Create one follow-up packet:

```text
runs/2026-06-22/2026-06-22__record-replay-candidate-workflow-test.md
```

Use it to test the top candidate:

```text
Create huddle completion-or-hold packet from source ledger
```

The packet should end as either:

- `Record & Replay candidate - ready for later capture`, or
- `Hold - workflow not stable enough to record`.
