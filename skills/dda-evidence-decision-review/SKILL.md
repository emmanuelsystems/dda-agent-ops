---
name: dda-evidence-decision-review
description: Create review-only DDA evidence decision packets from meeting transcripts, generated notes, Notion or Slack context, Linear lane status, and repo run artifacts. Use when Codex needs to compare DDA/ATDL source material, separate proven from unsupported claims, classify hard stops vs warnings, identify feedback items and failure modes, and recommend the next eval criteria or proof packet without making readiness claims.
---

# DDA Evidence Decision Review

## Purpose

Turn mixed DDA/ATDL evidence into a bounded decision-review packet. Keep the work source-aware, conservative, and review-only: transcripts and generated notes explain what was said, but committed repo artifacts and approved source files define what is proven.

## Inputs

Require at least one source bundle:

- `MEETING_OR_NOTE_SOURCE`: transcript, generated meeting notes, Tactiq/Gemini notes, Slack thread, or pasted meeting summary.
- `REPO_EVIDENCE`: relevant files under `runs/YYYY-MM-DD/`, `agents/diarized-daily-assistant/`, `docs/`, `templates/`, `evals/`, or `schemas/`.

Accept optional sources:

- `NOTION_CONTEXT`: latest David-created or lane-relevant Notion pages.
- `LINEAR_CONTEXT`: active issue status, comments, or lane labels.
- `SLACK_CONTEXT`: David's latest instructions, daily thread, or outbound draft context.
- `OUTPUT_PATH`: preferred path under `runs/YYYY-MM-DD/`. If omitted, propose a path before writing.

If a needed source is unavailable, state the gap and continue only if the remaining evidence can still support a clearly bounded review.

## Source Order

Use this order when sources disagree:

1. Committed repo source files and run artifacts for proof state, prompt source, version history, and file truth.
2. Notion for planning, task status, and latest David-created method/context pages.
3. Linear for active issue state and gating comments.
4. Slack for discussion, requests, and delivery context.
5. Generated notes or transcripts for conversation evidence, not proof.
6. Memory only as discovery context; verify important claims against current sources when possible.

When generated notes, transcript language, or Slack discussion conflict with repo evidence, keep the repo proof boundary explicit.

## Procedure

1. Restate the review boundary: date, lane, artifacts, and what the packet is allowed to decide.
2. Read the relevant repo anchors before writing. For DDA/ATDL work, check the latest applicable `runs/YYYY-MM-DD/` packets plus `agents/diarized-daily-assistant/` and source-of-truth docs when needed.
3. Pull optional connected context only when it materially changes current truth. Treat Notion/Linear/Slack as live surfaces that need fresh verification for status or instructions.
4. Extract claims from meeting notes or transcripts into three buckets: project-proof claims, personal/reflection context, and off-scope or unsupported claims.
5. Compare each project-proof claim against durable evidence. Mark each as `PROVEN`, `PARTIAL`, `UNPROVEN`, `CONFLICT`, or `OUT OF SCOPE`.
6. Classify blockers as `HARD STOP`, `REVIEW / HARD STOP until decided`, `CONDITIONAL PASS / WARNING`, `REVIEW`, or `STOP EXPANDING`.
7. Preserve the DDA operating boundary unless current source evidence explicitly changes it: DDA is a supervised alignment/proof-routing pilot, Yellow/not runtime-ready, with runtime movement blocked until the relevant proof rows are closed or accepted.
8. Recommend the next smallest proof packet or eval criteria. Do not recommend broad strategy, runtime promotion, automation enablement, PR creation, or external writes unless the evidence and human approval both support it.
9. If writing a file, place it under `runs/YYYY-MM-DD/` and keep the artifact review-only unless the user explicitly asks for another status.
10. Verify the packet against the done-when checklist before reporting completion.

## Required Packet Shape

Use this structure for new review artifacts unless the user asks for a narrower output:

```markdown
# DDA Evidence Decision Review

## Review Boundary
- Date:
- Lane:
- Review status: Draft / review-only
- Primary sources:
- Not decided here:

## Current Standing
- DDA readiness:
- Active gate:
- Runtime / automation posture:

## Source Map
| Source | Type | Date / freshness | Used for | Trust boundary |
|---|---|---|---|---|

## Real Decisions
- Decision:
  - Evidence:
  - Remaining condition:

## Proven vs Unproven Claims
| Claim | Status | Evidence | Notes |
|---|---|---|---|

## Inaccurate, Off-Scope, or Unsupported Notes
| Note / claim | Issue | Safer wording |
|---|---|---|

## Feedback Items
- Feedback:
  - Source:
  - Decision needed:

## Hard Stops vs Warnings
| Item | Classification | Why | Required next evidence |
|---|---|---|---|

## Recurring Failure Modes
- Failure mode:
  - Cause:
  - Prevention:

## Next Eval Criteria
- Criterion:
  - Passing evidence:
  - Failing evidence:

## Recommended Next Step
- Next smallest packet:
- Why this before broader execution:
```

## Write Boundaries

- Do not post to Slack, update Notion, send email, save persistent memory, create automations, create pull requests, or claim final readiness without explicit human approval.
- Do not treat raw chat history as durable truth.
- Do not overwrite approved source files without preserving changelog context.
- Do not collapse DDA and Codex responsibilities: DDA owns daily alignment; Codex owns build/research execution; automations own recurrence; durable artifacts own truth.
- Do not turn personal reflection material into team-facing proof unless the user explicitly asks for a shareable reflection.

## Done-When

The review is complete only when:

- Every major claim is tied to a source or marked unknown.
- Generated notes and transcripts have been checked for inaccurate, off-scope, or unsupported content.
- Current standing distinguishes proven, partial, unproven, blocked, and review-needed items.
- The packet identifies hard stops, warnings, recurring failure modes, and next eval criteria.
- The final response names files created or changed and states any verification that was skipped or blocked.
