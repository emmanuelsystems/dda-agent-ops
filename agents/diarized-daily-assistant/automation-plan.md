---
title: DDA Automation Plan
asset_type: automation_plan
status: draft
version: v0.2
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: agents/diarized-daily-assistant/automation-plan.md
created: 2026-04-28
updated: 2026-04-29
---

# DDA Automation Plan

## Purpose

Capture future automation ideas without enabling them during the scaffold phase.

## Current Boundary

No automation is enabled by this file.

Automation is not ready until the manual pilot proves stable inputs, stable outputs, approval gates, and logging destinations.

## Candidate Recurrence Schedule

These are planning candidates only:

| Candidate | Timing | Output |
|---|---|---|
| Morning alignment | Start of workday | Morning context, top-of-mind intake, daily game plan |
| Midday recenter | Midday or after interruption | Reprioritized plan and new handoff needs |
| Evening close | End of workday | Evening report and tomorrow seed |
| Pre-meeting staging | Before scheduled check-ins | Artifact-backed agenda and proof/non-proof summary |

## Required Integrations Before Automation

Do not automate until these are confirmed:

- Calendar or scheduling surface for meeting-aware timing.
- Approved daily context source.
- Approved logging destination.
- Approval-gated Slack or email draft flow, if outbound communication is needed.
- Codex handoff routing method for repo/build/research execution.

## Manual Approval Gates

Automation must remain draft-only or reminder-only unless human approval is explicit for:

- Slack posts.
- Email or calendar sends.
- Notion updates.
- Memory writes.
- Pull requests.
- Workflow activation or schedule changes.

## Failure and Fallback Behavior

If an automation candidate lacks required context:

1. Produce a constrained draft.
2. Mark missing context.
3. Do not post externally.
4. Do not create durable memory.
5. Carry the missing input into the next manual review.

If a source conflicts with repo-backed source files:

1. Apply `docs/source-of-truth.md`.
2. Preserve the conflict in the run summary.
3. Ask for review before treating the result as final.

## Promotion Criteria

A DDA recurrence candidate can move beyond manual operation only after:

- At least five manual run days are complete.
- At least four of five days include the full required artifact set.
- No approval-boundary violations occur.
- At least one DDA-to-Codex-to-DDA handoff loop is documented.
- The human operator approves the exact recurrence, inputs, outputs, and external action gates.
