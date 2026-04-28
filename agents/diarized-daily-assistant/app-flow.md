---
title: DDA App Flow
asset_type: app_flow
status: draft
version: v0.2
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: agents/diarized-daily-assistant/app-flow.md
created: 2026-04-28
updated: 2026-04-28
---

# DDA App Flow

## Purpose

Map the daily interaction flow from intake through report and tomorrow seed, with explicit Codex handoff and durable artifact checkpoints.

## Success Condition

A successful day run produces complete daily outputs, routes execution tasks to Codex, and captures carryovers without breaking source-of-truth or approval boundaries.

## Phase A: Morning Intake and Plan

### Inputs

- Morning context.
- Top-of-mind intake.
- Known commitments and open loops.

### Steps

1. Parse commitments, constraints, and dependencies.
2. Extract top priorities and likely blockers.
3. Draft the daily game plan.
4. Decide whether any items require Codex execution.

### Outputs

- Daily game plan.
- Optional DDA-to-Codex handoff packet(s).

## Phase B: Midday Recenter

### Inputs

- Morning plan.
- Progress deltas.
- New constraints or interruptions.

### Steps

1. Compare planned work to actual progress.
2. Keep, change, drop, or defer priorities.
3. Trigger new Codex handoff if build/research tasks emerged.

### Outputs

- Midday recenter update.
- Optional additional Codex handoff packet.

## Phase C: Evening Close and Next-Day Seed

### Inputs

- Day outputs.
- Remaining open loops.
- Returned Codex completion packet(s).

### Steps

1. Summarize completed work.
2. Capture unresolved work and carryovers.
3. Draft evening report.
4. Draft tomorrow seed.

### Outputs

- Evening report.
- Tomorrow seed.

## Codex Handoff Subflow

When a task needs execution:

1. Create `templates/dda-to-codex-handoff.md` packet.
2. Include context, acceptance criteria, and constraints.
3. Wait for `templates/codex-to-dda-completion.md` packet.
4. Integrate completion summary into evening outputs and carryovers.

## Durable Artifact Subflow

For each artifact:

1. Label state: draft, reviewed, or durable.
2. Route to the correct surface (Notion, runs folder, or committed GitHub source).
3. Apply approval gates for external posting, memory persistence, and PR actions.

## Decision Points

- Does this task require build/research/repo execution? -> handoff to Codex.
- Does this output claim durable truth? -> require reviewed durable artifact.
- Does this action cross approval boundary? -> require explicit human approval.

## Failure Modes and Fallbacks

- Missing context -> publish constrained draft and mark assumptions.
- Conflicting artifacts -> apply source-of-truth precedence and escalate if unresolved.
- Unavailable integrations -> produce manual next-step and avoid assumptions.
- Unfinished handoff by day end -> record as carryover with explicit status.

## Daily Exit Criteria

- Morning, midday, and evening outputs exist.
- All execution-class tasks were routed through Codex handoff.
- Assumptions and open questions are explicit.
- Carryovers are ready for next-day intake.
