---
title: TokenYield Preflight - SSI-102
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
related_linear_issue: SSI-102
created: 2026-06-09
approval_status: not_approved
external_write_claim: none
linear_write_claim: none
runtime_claim: none
canon_claim: none
memory_claim: none
automation_claim: none
implementation_claim: none
github_path: runs/2026-06-09/2026-06-09__tokenyield-preflight-ssi-102.md
---

# TokenYield Preflight - SSI-102

## Review Boundary

This is a draft/review-only measurement preflight for TokenYield and AI capacity visibility.

It does not build an analytics dashboard, fetch account billing, update Linear, update Notion, post to Slack, write memory, enable automation, commit, push, create a PR, or make numeric token/credit claims.

## Target Issue

| Field | Value |
|---|---|
| Issue | `SSI-102` |
| Title | `Build AI capacity analytics ledger and Codex usage snapshot MVP` |
| URL | `https://linear.app/systemsshaper/issue/SSI-102/build-ai-capacity-analytics-ledger-and-codex-usage-snapshot-mvp` |
| Current status checked | `Todo` |
| Priority | High |
| Draft purpose | Define the smallest measurement slice needed before token/context claims or analytics work. |

## Purpose

Convert token/context friction from anecdote into a small, reviewable measurement loop.

The preflight question is:

```text
What data would prove that DDA/Codex huddle work is producing enough verified value for the token, credit, time, and review burden it consumes?
```

## Current Read

| Claim | Status | Evidence |
|---|---|---|
| Token/context burn is now a real workflow concern. | Source-grounded | June 3 huddle notes and June 5 runtime packet. |
| Numeric token/credit usage is not yet available in reviewed artifacts. | Source-grounded gap | June 3 post-huddle bundle and June 5 dry-test both mark usage source missing/partial. |
| The next measurement should be manual and report-only. | Inferred | Closed-loop pilot requires TokenYield row but does not authorize analytics build. |
| `SSI-102` is the best capacity measurement issue home. | Source-grounded candidate | Linear search/check shows `SSI-102` is high priority and directly about AI capacity analytics. |

## TokenYield Definition

```text
TokenYield = verified value produced per unit of token/credit spend, time, review burden, and operational risk.
```

Do not reduce TokenYield to "use fewer tokens." The stronger measure is whether a run produces accepted artifacts, reduces reconstruction burden, prevents rework, and creates durable evidence.

## Minimum Ledger v0.1

Use this manual row for each huddle/Codex run.

| Field | Required? | Entry guidance |
|---|---|---|
| Date | Yes | Exact date. |
| Run ID | Yes | `YYYY-MM-DD__surface__short-slug`. |
| Related issue | Yes | `SSI-118`, `SSI-102`, etc. |
| Route | Yes | `huddle-state-recovery`, `codex-execution-packet`, `linear-alignment-draft`, `tokenyield-preflight`, `vee-trace-to-eval`, or `human-decision-hold`. |
| Surface used | Yes | DDA, Codex, repo, Slack, Notion, Drive, Linear, etc. |
| Time box | Yes | Planned and actual if available. |
| Token/credit usage available? | Yes | Yes / No / Partial. |
| Usage source | Yes | Dashboard, export, session stats, manual estimate, `[Missing Source]`. |
| Artifact produced | Yes | Path/link/title. |
| Artifact status | Yes | Draft, reviewed, accepted, held, rejected, committed. |
| Review burden | Yes | Low / Medium / High with one sentence. |
| David reconstruction burden | Live only | Low / Medium / High / Not measured. |
| Rework cause | If applicable | Missing source, wrong route, unclear verifier, excessive context, owner gate, etc. |
| Value produced | Yes | Decision clarity, source recovery, bounded packet, issue draft, eval candidate, no value. |
| Boundary risk | Yes | None / low / medium / high, with held actions named. |
| Next measurement | Yes | What to capture next run. |

## Manual Ledger Starter Rows

| Date | Run ID | Route | Usage available? | Usage source | Artifact | Review burden | David reconstruction burden | Value produced | Status |
|---|---|---|---|---|---|---|---|---|---|
| 2026-06-05 | `2026-06-05__codex__weekly-huddle-runtime-dry-test` | `codex-execution-packet` | Partial | Goal/session usage existed conceptually, but no user-facing export reviewed | `runs/2026-06-05/2026-06-05__goal-run-result__weekly-huddle-runtime-dry-test.md` | Medium | Not measured | Sequence verification, next live packet | Draft/local |
| 2026-06-09 | `2026-06-09__repo__weekly-review-alignment` | `huddle-state-recovery` | No | `[Missing Source]` | `runs/2026-06-09/2026-06-09__weekly-review-and-alignment.md` | Medium | Not measured | Cross-surface current read and next queue | Draft/local |
| 2026-06-09 | `2026-06-09__repo__closed-loop-pilot` | `codex-execution-packet` | No | `[Missing Source]` | `runs/2026-06-09/2026-06-09__closed-loop-pilot-dda-huddle-runtime.md` | Low/Medium | Not measured | Control loop and verifier | Draft/local |
| 2026-06-09 | `2026-06-09__repo__linear-ssi-118-draft` | `linear-alignment-draft` | No | `[Missing Source]` | `runs/2026-06-09/2026-06-09__linear-ssi-118-update-draft.md` | Low | Not measured | Paste-ready issue update draft | Draft/local |

## Data Sources To Recover

| Source | Needed for | Current status | Recovery action |
|---|---|---|---|
| Codex session/goal usage | Actual token/usage for repo artifacts. | Missing / not reviewed. | Check whether Codex exposes per-run token or usage stats in current app/session. |
| ChatGPT workspace/admin usage | Account-level usage and limits. | Missing / not reviewed. | David/Emmanuel decide whether admin/account access is available and appropriate. |
| Manual time log | Time box and actual duration. | Can start immediately. | Record start/end timestamps for huddle/Codex runs. |
| Artifact acceptance status | Whether output survived review. | Not yet reviewed for June 5/9 local artifacts. | Mark accepted/held/rework/rejected after human review. |
| Review burden | Whether artifact reduces or increases human load. | Needs human confirmation. | Reviewer labels low/medium/high with reason. |
| David reconstruction burden | Whether the loop reduces live explanation. | Needs live huddle. | Measure during next huddle. |
| Rework cause | Why a run failed or needed revision. | Needs reviewed run outcomes. | Add after each completion packet. |

## Measurement Rules

| Rule | Reason |
|---|---|
| No numeric token/credit claims without a usage source. | Prevents anecdote from becoming evidence. |
| Measure value and review burden together. | Cheap output that increases review burden is not high-yield. |
| Mark usage source as `[Missing Source]` when unavailable. | Keeps gaps visible without blocking manual learning. |
| Separate verification from validation. | A sequence can be executable but still not useful live. |
| Track accepted/held/rework/rejected. | Artifact acceptance is the clearest value signal. |
| Keep measurement manual before automation. | The fields need to prove useful before building analytics. |

## Pass / Fail Criteria For The Preflight

| Criterion | Pass condition |
|---|---|
| Ledger fields defined | Minimum Ledger v0.1 exists. |
| Missing sources named | Usage/account/session gaps are explicit. |
| Manual row can be filled today | At least current artifact rows can be recorded without external access. |
| Numeric claims blocked | Any missing usage remains labeled `[Missing Source]`. |
| Linear draft available | `SSI-102` update bullets can be reviewed before posting. |
| No external writes | Nothing posted or updated. |

## Draft SSI-102 Update Bullets

Do not post without approval.

- Token/context friction is now part of the DDA huddle runtime proof lane, but numeric token/credit source is still missing.
- Created a report-only TokenYield preflight to define the smallest measurement slice before analytics work.
- Proposed definition: TokenYield = verified value produced per unit of token/credit spend, time, review burden, and operational risk.
- Starting manual ledger fields: run ID, route, surface, time box, usage source, artifact, status, review burden, David reconstruction burden, rework cause, value produced, boundary risk, next measurement.
- Current rows can be filled for June 5 and June 9 repo artifacts, but usage source remains `[Missing Source]`.
- Recommended next action: use the next live huddle to capture time box, source count, missing-source count, artifact acceptance, review burden, and David reconstruction burden before building any dashboard.

## Recommended Next Measurement

For the next live huddle, capture:

| Metric | Target |
|---|---|
| Start/end time | Exact huddle segment duration. |
| Route selected | One primary route. |
| Sources opened | Count and list. |
| Missing sources | Count and list. |
| Artifact produced | Path/link/title. |
| Token/usage source | Available / partial / missing. |
| Review burden | Low / Medium / High. |
| David reconstruction burden | Low / Medium / High. |
| Acceptance status | Accepted / Held / Rework / Rejected. |
| Rework cause | If any. |

## Completion Packet

### Summary

Created a report-only TokenYield preflight tied to `SSI-102`.

### Files Created Or Updated

| File | Action | Notes |
|---|---|---|
| `runs/2026-06-09/2026-06-09__tokenyield-preflight-ssi-102.md` | Created | Defines minimum manual ledger, data sources to recover, measurement rules, preflight pass/fail criteria, and draft `SSI-102` update bullets. |

### Decisions Made

- Treat TokenYield as value per spend/time/review/risk, not just fewer tokens.
- Keep the first measurement loop manual and report-only.
- Use `SSI-102` as the candidate issue home for capacity/usage measurement.
- Block numeric token/credit claims until a usage source is recovered.

### Open Questions

- Is a Codex per-run usage source available in the current app/session?
- Is a ChatGPT workspace/admin usage source available and appropriate to use?
- Should June 5 and June 9 local artifacts be reviewed before they become ledger rows in a committed source?
- What review-burden scale should David use: simple low/medium/high or numeric 1-5?

### Recommended Next Steps

1. Review this preflight.
2. If approved, use the ledger fields in the next live huddle.
3. Draft or post `SSI-102` update only after approval.
4. Do not build analytics until two or three manual rows prove the fields are useful.

### DDA Integration Notes

DDA should carry this measurement posture:

```text
TokenYield is a manual proof field for now.
Numeric token/credit claims remain blocked until a usage source is recovered.
The next live huddle should measure value, review burden, and David reconstruction burden, not just token spend.
```
