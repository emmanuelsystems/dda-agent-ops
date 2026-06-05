---
title: Review Initiation Protocol Test
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
related_method_lane: ATDL
created: 2026-06-03
target_meeting_date: 2026-06-03
meeting_members:
  - Emmanuel Olana
  - David
approval_status: not_approved
runtime_claim: none
canon_claim: none
external_write_claim: none
memory_claim: none
automation_claim: none
implementation_claim: none
---

# Review Initiation Protocol Test

## Review Boundary

This is a draft/review-only huddle operator sheet for the Wednesday, 2026-06-03 huddle with David.

It tests whether Emmanuel and the agent can recover current state, trace source locations, capture David's corrections, choose the next route, and produce a baton pass without David rebuilding the whole work state live.

It does not approve runtime readiness, Loop 003, Track 2, automation, memory promotion, canon claims, source edits, commits, pushes, pull requests, Notion updates, Linear updates, Slack posts, Drive writes, or dashboard/product implementation.

## Test Objective

```text
Can Emmanuel and the agent reconstruct the current state, source trail, proof gaps, router decision, and next action in the first 20-30 minutes of the huddle without David rebuilding the architecture live?
```

## Member Roles

| Member | Role In This Flow | Owns | Does Not Own |
|---|---|---|---|
| Emmanuel | Operator / state-recovery driver | Opens sources, reconstructs current state, marks readiness, captures exact locations, drafts the packet, names route and baton pass. | Approval, canon promotion, external writes, runtime-readiness claims. |
| David | Reviewer / correction source / gate owner | Corrects state, validates or rejects route, names missing context, chooses gate, defines what counts as pass. | Reconstructing all state live, hidden operating-system work, unbounded architecture explanation. |

## Prep Readiness

Mark one before starting.

| Status | Use When | Selected |
|---|---|---|
| Green | Required source tabs and repo artifacts are open; operator can name current lane and next packet. |  |
| Yellow | Some sources are missing or stale, but enough context exists to run a bounded state-recovery test. |  |
| Red | Source trail, active lane, or next packet cannot be named without David reconstructing the work live. |  |

Readiness reason:

```text
TBD
```

## Source Locations To Capture

Capture exact locations used during the huddle. Do not treat a source as read unless it was actually opened or supplied in the meeting.

| Source | Authority Class | Exact Location | Used For | Gap / Note |
|---|---|---|---|---|
| Meeting prep synthesis | Local review-only artifact | `runs/2026-06-02/david-june-03-meeting-prep-synthesis.md` | Current huddle stance and 20-30 minute loop. |  |
| Recording walkthrough timeline | Local review-only artifact | `runs/2026-06-02/june-03-recording-walkthrough-timeline.md` | First 15-20 minute run shape. |  |
| Trace format / form-factor matrix | Local review-only artifact | `runs/2026-06-01/dda-trace-format-and-form-factor-decision-matrix.md` | Trace-first rule and route fields. |  |
| Source-of-truth model | Repo source | `docs/source-of-truth.md` | Authority separation and approval boundaries. |  |
| Router skill | Local skill draft | `skills/dda-codex-intent-router/SKILL.md` | Router decision discipline. |  |
| Linear SSI-113 | External review surface | `https://linear.app/systemsshaper/issue/SSI-113` | Broader DDA proof-gate history. | Confirm live state if used. |
| Linear SSI-118 | External review surface | `https://linear.app/systemsshaper/issue/SSI-118` | Active intent-router review lane. | Confirm live state if used. |
| Linear SSI-115 | External review surface | `https://linear.app/systemsshaper/issue/SSI-115` | Weekly proof-gate / feedback-loop method. | Confirm live state if used. |
| Notion | Working / review surface | TBD | Decision capture or current state, if David directs. | Do not update without approval. |
| Slack | Coordination / working signal | TBD | Links, context, or David signal, if referenced. | Do not post without approval. |
| Drive / transcript | Raw evidence / working analysis | TBD | Meeting evidence and transcript markers. | Capture timestamps if used. |
| GitHub / repo | Durable backend after review/commit | `F:\Codex Projects\dda-agent-ops` | Local run artifacts and source files. | Local drafts are not durable until reviewed/committed. |

## Current State Reconstruction

Use this section live. Keep it short enough for David to correct.

### Last Known State

```text
DDA has shifted from broad daily-status framing toward a trace-first state-recovery and meeting-system proof lane.
```

### Current Active Lane

```text
DDA router / state recovery / meeting-system proof.
```

### What Is Proven

| Proven Item | Evidence Location | Confidence |
|---|---|---|
| Repo contains review-only artifacts for the SSI-113 to SSI-118 lane shift. | `runs/2026-05-27/ssi-113-blocker-reconciliation.md` | Medium |
| June 1 trace matrix defines the trace-first posture. | `runs/2026-06-01/dda-trace-format-and-form-factor-decision-matrix.md` | Medium |
| June 2 prep frames the huddle as the next live state-recovery test. | `runs/2026-06-02/david-june-03-meeting-prep-synthesis.md` | Medium |

### What Is Draft / Review Only

| Draft Item | Location | Required Gate |
|---|---|---|
| Meeting prep synthesis | `runs/2026-06-02/david-june-03-meeting-prep-synthesis.md` | David review before treating as accepted direction. |
| Recording walkthrough timeline | `runs/2026-06-02/june-03-recording-walkthrough-timeline.md` | David correction before reuse. |
| This protocol test | `runs/2026-06-03/review-initiation-protocol-test.md` | David review after huddle. |

### What Is Still Unknown

| Unknown | Why It Matters | Owner To Decide |
|---|---|---|
| Whether the first huddle output should live in repo, Notion, Drive, Slack, Linear, or hybrid. | Determines the repeatable handoff surface. | David |
| Whether feedback should go primarily to SSI-118, SSI-115, or a new issue. | Determines the active review lane. | David |
| What score is enough to call the huddle loop reusable. | Prevents vague success claims. | David |

## David Corrections

Capture corrections verbatim enough to preserve meaning.

| Time / Marker | Correction Or Signal From David | Impact On State | Follow-Up |
|---|---|---|---|
| TBD | TBD | TBD | TBD |

## Experiment And Measurement Log

| Experiment | Question | Measurement | Result | Evidence |
|---|---|---|---|---|
| State recovery front door | Can Emmanuel and the agent recover state without David reconstructing it live? | Re-entry time, correction count, route quality, next-packet clarity. | TBD | Huddle transcript / this artifact. |
| Meeting-as-runtime | Can the first 20-30 minutes become a repeatable huddle protocol? | Agent-ready context pack and role-specific baton pass. | TBD | Huddle transcript / follow-up artifact. |
| Trace discipline | Can each decision show source, route, artifact, verifier, and gate? | Missing-field count. | TBD | This artifact. |

## Transcript Markers

Use these markers while reviewing transcript or notes.

| Marker | Meaning | Example Capture |
|---|---|---|
| `SOURCE` | A source, path, issue, page, Slack thread, Drive file, or transcript location is named. | `SOURCE: SSI-118 active review surface.` |
| `STATE` | Current state, proof status, or unknown is clarified. | `STATE: huddle runtime is current proof lane.` |
| `CORRECTION` | David corrects the operator's read. | `CORRECTION: not dashboard yet; protocol first.` |
| `DECISION` | A route, owner, artifact, or gate is chosen. | `DECISION: feedback goes to SSI-115.` |
| `EXPERIMENT` | A test or measurement is named. | `EXPERIMENT: no-live-reconstruction test.` |
| `BATON` | A next action is assigned. | `BATON: create post-huddle packet in runs/2026-06-03/.` |
| `STOP` | A boundary or blocker requires pause. | `STOP: no external write approval.` |

## Router Decision

Choose one primary route for the next action.

| Route | Use When | Selected |
|---|---|---|
| DDA review lane | State, source trail, or proof gaps need more review before execution. |  |
| Codex bounded execution | A clear repo artifact, source edit, synthesis, or verification task is approved. |  |
| Linear feedback loop | The next action is issue tracking, gate clarification, or proof-loop ownership. |  |
| Notion decision capture | The next action is a working decision page or shared review surface. |  |
| Slack coordination draft | The next action is a team-safe update requiring approval before posting. |  |
| Human-only decision | Authority, verifier, or source conflict requires David to decide before routing. |  |

Routing rationale:

```text
TBD
```

## Run Score

Score after the first 20-30 minutes.

| Criterion | 0 | 1 | 2 | Score |
|---|---|---|---|---|
| Prep readiness | Sources not ready. | Partial source trail. | Required sources and lane visible. |  |
| Source precision | Sources vague or missing. | Some exact paths / links. | Exact source locations captured. |  |
| State reconstruction | David had to rebuild state. | David corrected several gaps. | Emmanuel and agent reconstructed state with limited correction. |  |
| Proof separation | Draft/context/proof blurred. | Some boundaries visible. | Proof, context, draft, REVIEW clearly separated. |  |
| Router decision | No route chosen. | Candidate route named. | Route, artifact, verifier, and gate named. |  |
| Baton pass | No next action. | Next action named but underspecified. | Owner, artifact, verifier, gate, and stop condition captured. |  |

Total:

```text
TBD / 12
```

Pass threshold proposed for this dry run:

```text
8 / 12 or higher, with no approval-boundary violations.
```

David override:

```text
TBD
```

## Baton Pass

Fill this before closing the huddle segment.

| Field | Value |
|---|---|
| Next packet | TBD |
| Proposed default | `runs/2026-06-03/review-initiation-protocol-test.md` updated with huddle results |
| Owner | Emmanuel |
| Reviewer / gate owner | David |
| Verifier | Check that source locations, state, route, artifact, verifier, gate, and stop conditions are all visible. |
| Human gate | David review before external writes, memory, automation, canon, commits, or runtime claims. |
| Stop condition | Pause if the route depends on unverified live Linear/Notion/Slack/GitHub state or if David changes the ownership surface. |

## Questions For David

1. Is this the right two-person flow: Emmanuel operates and drafts, David corrects and gates?
2. Should the huddle output live first in repo `runs/`, Notion, Drive, Slack thread, Linear, or a hybrid trace surface?
3. Should feedback after this meeting go to `SSI-118`, `SSI-115`, `SSI-113`, or a new issue?
4. What score or evidence would make this huddle loop reusable?
5. What should the agent receive after the first 20-30 minutes: transcript markers, markdown packet, trace record, task list, or all of these?

## Completion Notes

Complete this section after the huddle.

### Summary

TBD

### Files Changed

| File | Notes |
|---|---|
| `runs/2026-06-03/review-initiation-protocol-test.md` | Draft huddle operator sheet and test packet. |

### Decisions Made

TBD

### Open Questions

TBD

### Recommended Next Steps

TBD

### DDA Integration Notes

This packet should be used as a review-only huddle test record. It is not approval to update external systems, save memory, promote canon, enable automation, claim runtime readiness, move Loop 003 or Track 2, or build a dashboard.
