---
title: DDA Rules Fit Test
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: runs/2026-05-22/dda-rules-fit-test.md
created: 2026-05-22
updated: 2026-05-22
approval_status: not_approved
runtime_claim: none
canon_claim: none
external_write_claim: none
---

# DDA Rules Fit Test

## Review Boundary

This is a review-only fit test for the current `AGENTS.md` rules against the workflow:

```text
David update -> DDA handoff packet -> Codex repo artifact -> verification -> DDA completion packet
```

This artifact does not approve Slack posts, Notion updates, memory saves, automations, commits, pushes, pull requests, source-of-truth changes, runtime readiness, loop 003, Track 2, or final acceptance of the workflow.

Current posture:

- DDA remains the daily alignment layer.
- Codex remains the build/research/repo execution layer.
- Automations remain recurrence only after approval.
- Durable artifacts own truth only after review and promotion.
- This file is a draft run artifact, not final approval.

## 1. Source Basis

| Source | How it was used | Fit-test readout |
|---|---|---|
| `AGENTS.md` | Primary rule source for repo purpose, operating rule, David Codex workloop, Codex permissions, 12-rule contract, source-of-truth rules, handoff/completion rules, approval boundaries, and commit expectations. | Current AGENTS rules add a stricter operating checklist and make review/approval gates explicit. |
| `agents/diarized-daily-assistant/instructions.md` | DDA behavior source for mission, scope, handoff triggers, output rules, approval gates, and fallback behavior. | Confirms DDA should route execution-class work through Codex instead of doing it directly. |
| `agents/diarized-daily-assistant/prd.md` | Product behavior source for manual pilot goals, non-goals, success metrics, and pilot acceptance criteria. | Confirms the tested workflow is a required manual-pilot loop and boundary violation rate must remain zero. |
| `agents/diarized-daily-assistant/app-flow.md` | Workflow source for morning/midday/evening phases, Codex handoff subflow, durable artifact subflow, and decision points. | Confirms the tested loop is already a defined subflow, but now needs the AGENTS workloop applied more explicitly. |
| `agents/diarized-daily-assistant/agent-config.md` | Runtime-status and integration-assumption source. | Confirms no direct apps/actions, runtime config, memory, or automation should be assumed from repo files alone. |
| `agents/diarized-daily-assistant/memory.md` | Memory boundary source. | Confirms memory may be proposed only as a candidate and cannot be saved without explicit approval. |
| `docs/source-of-truth.md` | Durable truth, surface ownership, promotion, and approval model. | Confirms chat history and Codex output are not durable until reviewed and committed or approved in the right surface. |
| `docs/backend-strategy.md` | Repo strategy and role split source. | Confirms GitHub is the durable markdown backend and Codex output becomes durable only after review and commit. |
| `docs/conversion-pipeline.md` | Manual-proof-before-automation source. | Confirms no asset or workflow becomes agent-ready merely because it exists; it must be classified, tested, reviewed, and promoted. |
| `templates/dda-to-codex-handoff.md` | Required handoff packet shape. | Confirms a DDA handoff needs task, context, inputs, expected output, acceptance criteria, constraints, and completion return requirement. |
| `templates/codex-to-dda-completion.md` | Required completion packet shape. | Confirms Codex must return summary, files changed, decisions, open questions, next steps, and DDA integration notes. |
| `evals/dda-core-behavior-evals.md` | Behavior-check source. | Confirms relevant evals are boundary routing, integration assumptions, truth handling, handoff completeness, and assumption marking. |
| `runs/2026-05-19/dda-hard-stops-vs-warnings-register.md` | Prior reviewed-style proof boundary pattern. | Confirms current DDA posture should remain Yellow / not runtime-ready, with loop 003 and Track 2 blocked unless explicitly approved. |

Memory was used only as orientation for prior repo conventions and boundary language. It was not treated as source of truth over current repo files.

## 2. Current Workflow Interpretation

The tested workflow should now be interpreted as a bounded review-and-execution chain:

| Step | Owner | Required artifact or action | Current rule fit |
|---|---|---|---|
| David update | David / human source | A reviewed or explicitly provided update, decision, request, or source packet. | DDA may use it as current context, but should not treat raw chat as durable truth unless converted into a reviewed artifact. |
| DDA handoff packet | DDA | A packet using `templates/dda-to-codex-handoff.md`. | Required when the task involves repo work, research, artifact drafting, prompt refactoring, skill generation, automation planning, or verification. |
| Codex repo artifact | Codex | A draft or patch in the correct repo path, usually under `runs/YYYY-MM-DD/`, `docs/`, `templates/`, `evals/`, `schemas/`, or `agents/diarized-daily-assistant/`. | Codex may create draft markdown and verify it, but must not imply final approval or durability. |
| Verification | Codex, then human reviewer | Mechanical checks plus intent checks against acceptance criteria and approval boundaries. | Verification must prove the requested behavior, not merely that a command passed. |
| DDA completion packet | Codex returns; DDA integrates | A packet using `templates/codex-to-dda-completion.md`. | Completion must list files changed, decisions made, open questions, recommended next steps, and DDA integration notes. |

The important change is that the workflow is not just `handoff -> artifact -> completion`. It must now carry the David Codex workloop fields through each step and keep approval gates visible until a human explicitly moves them.

## 3. David Codex Workloop Application

| Workloop slot | Application to this workflow | Required control |
|---|---|---|
| `intent` | State what David's update is trying to decide, clarify, test, or produce. | DDA should not route vague intent into broad Codex execution. |
| `context` | Attach durable sources, current repo paths, known prior artifacts, open risks, and source conflicts. | Chat, Slack, Notion, memory, and repo claims must be separated by source type. |
| `mode` | Classify the work as draft, review, execution, verification, planning, or external-write request. | Mode determines whether DDA handles it or creates a Codex handoff. |
| `slot` | Place the work in the daily loop or proof lane: morning, midday, evening, run artifact, eval, handoff, completion, blocker register, or carryover. | Prevents broad strategy drift and misplaced artifacts. |
| `cadence` | State whether this is one-time, daily, weekly, recurring candidate, or no-recurrence. | Recurrence does not imply automation. Automation still needs explicit approval. |
| `artifact` | Name the exact file, packet, template, or expected output. | Codex should write only the scoped artifact or files. |
| `verifier` | Define how the result will be checked: source coverage, acceptance criteria, diff check, eval row, manual review, or external-surface confirmation. | Verification must include intent and boundary checks. |
| `memory` | Identify only memory candidates or memory implications. | No memory save without explicit human approval. |
| `gate` | List blocked surfaces and approval requirements. | Slack, email, Notion, memory, automation, PRs, commits, pushes, final status, and source-of-truth changes remain blocked unless approved. |
| `learning update` | Capture what DDA should carry into future reports, templates, evals, or follow-up packets. | Learning is draft until reviewed and promoted. |

Minimum handoff addition:

```text
Workloop:
- intent:
- context:
- mode:
- slot:
- cadence:
- artifact:
- verifier:
- memory:
- gate:
- learning update:
```

## 4. Which 12 Rules Affect DDA Behavior

All 12 rules affect DDA behavior because they constrain how DDA prepares Codex work and how Codex responds. The strongest DDA-facing effects are:

| Rule | Effect on DDA behavior |
|---|---|
| 1. Think before coding | DDA should state assumptions, tradeoffs, missing inputs, and source conflicts before creating a handoff. |
| 2. Simplicity first | DDA should route the smallest useful execution slice, not a broad open-ended build request. |
| 3. Surgical changes | DDA should name allowed files, prohibited files, and expected artifact paths. |
| 4. Goal-driven execution | DDA should define success and acceptance criteria before Codex starts. |
| 5. Use the model for judgment, not deterministic work | DDA should ask Codex for judgment, synthesis, and artifact drafting, while mechanical checks and status inspection stay tool-backed. |
| 6. Respect budget and context limits | DDA should keep handoffs bounded and ask for a fresh pass when context becomes too large or stale. |
| 7. Surface conflicts, do not average them | DDA should preserve source conflicts instead of smoothing repo, Notion, Slack, Linear, memory, or chat into one blended claim. |
| 8. Read before writing | DDA handoffs should require Codex to inspect relevant files, templates, and nearby artifacts before editing. |
| 9. Tests and checks must verify intent | DDA acceptance criteria should include behavioral and boundary checks, not only file-existence checks. |
| 10. Checkpoint significant steps | DDA should expect progress updates for multi-step Codex work and carry forward unresolved items. |
| 11. Convention beats novelty | DDA should route work into existing folders, templates, naming, and conservative proof language. |
| 12. Fail visibly | DDA should require Codex to report skipped sends, blocked writes, unrun checks, partial verification, and approval gaps plainly. |

Practical DDA behavior change:

```text
DDA should produce smaller, source-backed handoff packets with explicit file scope, verifier rows, blocked approvals, and completion requirements.
```

## 5. What Codex Should Do Differently Now

Codex should adjust behavior in this repo as follows:

| Area | Prior risk | Required behavior now |
|---|---|---|
| Handoff intake | Treating the handoff as enough context. | Reconstruct `intent -> context -> mode -> slot -> cadence -> artifact -> verifier -> memory -> gate -> learning update` before editing. |
| Artifact drafting | Writing a useful artifact but under-specifying source and approval status. | Include source basis, review boundary, approval status, and runtime/canon/external-write claims where relevant. |
| Verification | Running `git diff --check` only. | Combine mechanical checks with source coverage, acceptance criteria, and boundary verification. |
| Completion | Returning a summary without DDA integration notes. | Use or mirror `templates/codex-to-dda-completion.md` and explicitly state carryovers, open questions, and DDA report language. |
| External surfaces | Drafting as if Slack/Notion/memory/automation follow automatically. | Keep external writes blocked unless separately approved; provide ready-to-review text only when asked. |
| Truth claims | Letting local draft artifacts sound durable. | Label drafts as review-only until reviewed and promoted. |
| Scope control | Expanding into adjacent docs or strategy cleanup. | Touch only the scoped file or file set unless a conflict blocks the task. |
| Memory | Treating repeated preferences as immediately reusable memory. | Treat memory as candidate only and preserve explicit approval requirement. |

For this specific test, Codex should only create this single run artifact and verify it. It should not stage, commit, push, post, save memory, create automation, update Notion, or declare the workflow approved.

## 6. Approval Boundaries That Remain Blocked

| Boundary | Status | Reason |
|---|---|---|
| Slack posting | `BLOCKED` | Requires explicit human approval. |
| Email sending | `BLOCKED` | Requires explicit human approval. |
| Notion update | `BLOCKED` | Requires explicit human approval and correct surface selection. |
| Persistent memory save | `BLOCKED` | Requires explicit human approval; this file may identify candidates only. |
| Automation creation or enablement | `BLOCKED` | Manual behavior must be proven and approval boundaries defined first. |
| Commit | `BLOCKED` | User explicitly prohibited commit. |
| Push | `BLOCKED` | User explicitly prohibited push. |
| Pull request creation or merge | `BLOCKED` | Requires explicit human approval. |
| Final approval of this fit test | `BLOCKED` | User requested review-only and said not to treat this as final approval. |
| Source-of-truth rule changes | `BLOCKED` | Requires explicit human approval. |
| Runtime readiness claim | `BLOCKED` | Repo evidence does not prove configured runtime readiness. |
| Loop 003 or Track 2 movement | `BLOCKED` | Prior proof boundary keeps these blocked unless explicitly approved. |

## 7. Verification Performed

Verification target:

```text
runs/2026-05-22/dda-rules-fit-test.md
```

Checks performed while drafting:

- Read current `AGENTS.md`, including the David Codex workloop and 12-rule contract.
- Read DDA source docs: `instructions.md`, `prd.md`, `app-flow.md`, `agent-config.md`, and `memory.md`.
- Read source-of-truth and backend strategy docs.
- Read handoff and completion templates.
- Read behavior evals.
- Read prior hard-stops register for current conservative proof posture.
- Confirmed `runs/2026-05-22/` did not exist before creating this artifact.
- Preserved existing modified `AGENTS.md` without editing it.
- Created only this review-only artifact.

Final checks performed before reporting:

- Confirm the file exists at the requested path.
- Ran `git diff --check`; result had no whitespace errors and only the existing AGENTS.md LF-to-CRLF warning.
- Confirmed git status shows the pre-existing modified `AGENTS.md` plus this new untracked `runs/2026-05-22/` artifact folder.

## 8. DDA Integration Notes

DDA should carry forward this rule-fit interpretation:

- When David provides an update that implies repo work or verification, DDA should first turn it into a structured handoff packet.
- The handoff should include the David Codex workloop fields, not only task/context/inputs.
- Codex should return a completion packet with DDA integration notes, not just a file-change summary.
- DDA should integrate Codex completion into daily reports, carryovers, review queues, or follow-up handoffs only after checking approval boundaries.
- DDA should treat this fit test as a draft review artifact, not as a new approved operating standard.

Suggested next review action:

```text
Review whether `templates/dda-to-codex-handoff.md` should be updated later to include the David Codex workloop fields.
```

That template update is not approved by this artifact. It would need a separate handoff or explicit approval.

## Completion Packet For This Fit Test

## Summary

Codex created one draft/review-only DDA Rules Fit Test artifact at `runs/2026-05-22/dda-rules-fit-test.md`. The artifact maps the current AGENTS rules onto the workflow `David update -> DDA handoff packet -> Codex repo artifact -> verification -> DDA completion packet`.

## Files Created or Updated

| File | Path | Notes |
|---|---|---|
| DDA Rules Fit Test | `runs/2026-05-22/dda-rules-fit-test.md` | New review-only run artifact. |

## Decisions Made

- Use the existing `runs/YYYY-MM-DD/` convention for the test artifact.
- Treat current `AGENTS.md` as the controlling repo instruction source for this run.
- Treat memory as orientation only, not source of truth over repo files.
- Keep all approval-boundary actions blocked.

## Open Questions

- Should `templates/dda-to-codex-handoff.md` be updated later to include the David Codex workloop fields?
- Should `templates/codex-to-dda-completion.md` add an explicit verification section?
- Should a new eval be added for AGENTS rule compliance across DDA handoff and Codex completion packets?

## Recommended Next Steps

1. Human reviews this fit test for accuracy.
2. If accepted, create a separate bounded handoff to update the handoff/completion templates.
3. If accepted, consider adding an eval for the David Codex workloop.

## DDA Integration Notes

DDA should use this artifact as a review packet only. It may inform future daily alignment and handoff drafting after human review, but it does not approve memory, automation, external writes, commits, pushes, PRs, or final workflow promotion.
