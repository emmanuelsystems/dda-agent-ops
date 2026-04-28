---
title: Manual Pilot Plan
asset_type: workflow
status: draft
version: v0.2
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: docs/manual-pilot-plan.md
created: 2026-04-28
updated: 2026-04-28
---

# Manual Pilot Plan

## Purpose

Define the first manual run path for DDA before automation is enabled.

## Pilot Window

- Initial window: 5 consecutive manual run days.
- Goal: validate daily loop, boundary compliance, and handoff quality.

## Daily Run Sequence

1. Morning context input.
2. Top-of-mind intake.
3. Daily game plan output.
4. Midday recenter update.
5. Evening report.
6. Tomorrow seed.
7. DDA-to-Codex handoff and Codex completion loop (when triggered).

## Required Daily Artifacts

Store in `runs/YYYY-MM-DD/`:

- `morning-context.md`
- `top-of-mind-intake.md`
- `daily-game-plan.md`
- `midday-recenter.md`
- `evening-report.md`
- `tomorrow-seed.md`
- `dda-to-codex-handoff-01.md` (optional by trigger)
- `codex-to-dda-completion-01.md` (optional by trigger)
- `run-summary.md`

## Template Mapping

- Morning context -> `templates/morning-context.md`
- Intake -> `templates/top-of-mind-intake.md`
- Plan -> `templates/daily-game-plan.md`
- Midday -> `templates/midday-recenter.md`
- Evening -> `templates/evening-report.md`
- Tomorrow -> `templates/tomorrow-seed.md`
- Handoff -> `templates/dda-to-codex-handoff.md`
- Completion -> `templates/codex-to-dda-completion.md`

## Boundary Rules During Pilot

- DDA does not execute build/research tasks directly.
- Execution-class tasks require Codex handoff packet.
- No external posting, memory persistence, or Notion updates without explicit approval.
- No automation is enabled during v0.1 manual pilot.

## Daily Review Checklist

- Were all required daily outputs created?
- Were execution tasks routed through Codex handoff?
- Were assumptions and open questions explicit?
- Were any approval boundaries crossed?
- What carryovers move to the next day?

## Pilot Exit Criteria

Pilot is considered successful when:

- 5 manual run days are completed.
- At least 4 of 5 days include complete required artifacts.
- No boundary violations occurred.
- At least one full DDA-to-Codex-to-DDA loop is documented.

## Deferred Until After Pilot

- Automated recurrence.
- Direct integration assumptions.
- Workflow auto-routing without explicit approval boundaries.
