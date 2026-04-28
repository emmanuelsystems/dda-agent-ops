---
title: DDA Product Requirements
asset_type: prd
status: draft
version: v0.2
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: agents/diarized-daily-assistant/prd.md
created: 2026-04-28
updated: 2026-04-28
---

# DDA Product Requirements

## Purpose

Define what the Diarized Daily Assistant must do for the manual pilot.

## Problem Statement

Daily alignment currently depends on scattered context across Notion, chat history, and working docs. Without a repeatable daily loop and clear role boundaries, planning quality degrades, execution routing blurs, and durable artifacts drift.

## Target User

- Primary: a human operator managing daily priorities, project context, and execution handoffs.
- Secondary: collaborators who need clear, team-safe daily summaries and explicit carryovers.

## Goals (v0.1 Manual Pilot)

- Establish a reliable daily operating loop: morning -> midday -> evening.
- Enforce DDA vs Codex boundaries during execution-class tasks.
- Produce durable, reviewable markdown artifacts for pilot runs.
- Preserve assumptions, decisions, and carryovers with minimal ambiguity.

## Non-Goals (v0.1)

- Full automation.
- Unapproved direct integrations.
- Autonomous external communication.
- Multi-agent orchestration beyond DDA-Codex handoff.

## Core Workflows

- Morning context intake and daily game plan.
- Midday recenter and re-prioritization.
- Evening report and tomorrow seed.
- DDA-to-Codex handoff and Codex completion integration.

## Functional Requirements

DDA must:

1. Produce all required daily output packets.
2. Route build/research/repo tasks through Codex handoff packets.
3. Mark assumptions and open questions explicitly.
4. Follow source-of-truth precedence and approval boundaries.
5. Preserve carryovers for next-day planning.

## Success Metrics

- Daily output completeness rate >= 90% during pilot window.
- Correct handoff routing rate for execution-class tasks >= 95%.
- Explicit assumptions in outputs >= 90%.
- Boundary violations (unapproved posting, memory writes, automation claims) = 0.

## Risks

- Role collapse (DDA performing execution tasks).
- Source-of-truth ambiguity across Notion/GitHub/memory.
- Incomplete eval definitions causing inconsistent review.
- Pilot drift if outputs are generated but not reviewed.

## Mitigations

- Explicit trigger matrix in instructions.
- Promotion workflow and precedence order in source-of-truth doc.
- Pilot eval cases with pass/fail criteria.
- Daily run summary with unresolved items and carryovers.

## Pilot Acceptance Criteria

The v0.1 manual pilot is acceptable when:

- At least 5 consecutive manual run days are completed.
- Daily packet set is complete for at least 4 of 5 days.
- No boundary violations occur.
- At least one full DDA-to-Codex-to-DDA loop is completed and documented.

## Open Questions

- Which Notion source record is canonical for DDA source extraction?
- Which outputs remain Notion-only vs archived in runs folders?
- What is the preferred release tag convention after v0.1?
