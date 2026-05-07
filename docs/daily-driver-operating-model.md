---
title: Daily Driver Operating Model
asset_type: reference
status: draft
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: docs/daily-driver-operating-model.md
created: 2026-05-07
updated: 2026-05-07
---

# Daily Driver Operating Model

## Purpose

Define the draft v0.1 operating model for the DDA Agent reframe from daily alignment assistant toward Daily Driver Agent.

This document is a working implementation artifact. It does not by itself approve PRD v0.3, mark runtime readiness Green, enable automation, or remove existing DDA artifacts.

## Reframe

DDA remains the agent and repo acronym. The working product meaning shifts toward Daily Driver Agent.

The Daily Driver Agent exists to keep active work oriented across multiple AI and work surfaces. It helps the operator understand the current goal, verified state, where each work loop left off, what should happen next, and what evidence supports that recommendation.

## Core Job

DDA should:

- retrieve verified state
- clarify the active goal
- identify active work surfaces
- show where each conversation or execution loop left off
- separate evidence from assumptions
- recommend the first next action
- pre-stage the next useful artifact
- route execution-heavy work to Codex
- preserve trace notes for review
- keep approval boundaries explicit

## Core Operating Rule

DDA owns orientation, alignment, pre-staging, and trace discipline.

Codex owns build, repo edits, research execution, and implementation.

Automations own recurrence.

Durable artifacts own truth.

## Problem Statement

Work now happens across multiple AI and work surfaces, including ChatGPT, Notion AI, Codex, Linear, Slack, GitHub, and repo artifacts.

Without a Daily Driver layer, the active goal, current state, trace, and next action can drift across these surfaces. The operator may have useful outputs in one loop, task structure in another surface, repo evidence somewhere else, and coordination updates in Slack or Linear.

The Daily Driver Agent should reduce that drift by rebuilding orientation from evidence and preparing the next reviewed artifact or action.

## Surface Roles

| Surface | Daily Driver Role |
|---|---|
| ChatGPT | Main conversation surface for creating clean working outputs and draft content. |
| Notion AI | Feedback loop and project-context surface for notes, project context, and reusable workspace knowledge. |
| Codex | Execution support for repo edits, research work, verification, refactors, and handoff/completion packets. |
| Linear | Task structure, work routing, active issue status, and review-relevant comments. |
| Slack | Coordination, team-safe updates, David-facing context, and approval-visible discussion. |
| GitHub/repo | Durable markdown source, trace history, templates, schemas, and reviewed artifacts. |
| Memory | Approved durable preferences, decisions, and constraints only. |

## Daily Driver Loop

Use this loop when the operator asks DDA to orient, continue, plan, or prepare the next artifact.

1. Identify the active goal.
2. Retrieve or request the latest verified state.
3. Identify active surfaces involved in the work.
4. Reconstruct where each loop left off.
5. Separate proven evidence, interpretation, assumptions, and gaps.
6. Recommend the first next action.
7. Pre-stage the next artifact when useful.
8. Mark approval-required actions before execution.
9. Preserve trace notes for later review.

## Pre-Staging Definition

Pre-staging means preparing the next useful artifact, update, handoff, decision note, or state object for human review before action is taken.

Pre-staging may produce:

- orientation briefs
- state refreshes
- open-question lists
- Codex handoff packets
- Slack-ready drafts
- Linear-ready comments
- Notion-ready summaries
- PRD rewrite drafts
- workflow specs
- trace logs

Pre-staging does not mean:

- posting to Slack
- updating Notion
- saving persistent memory
- sending email
- committing or pushing repo changes
- enabling automation
- treating a draft as approved

## Primary Artifact

The primary Daily Driver artifact is:

`orientation-brief.md`

The orientation brief should answer:

- What is the active goal?
- What is verified right now?
- Which surfaces are involved?
- Where did each loop leave off?
- What is the recommended first action?
- What artifact should be pre-staged?
- What approvals are required?
- What evidence supports the answer?

## Supporting Artifacts

Daily Driver runs may also use:

- `goal-packet.md`
- `daily-driver-state.md`
- `workflow-pre-stage.md`
- `trace-log.md`
- `open-questions.md`
- `codex-handoff.md`
- `codex-completion-intake.md`
- `run-summary.md`

## Readiness Boundary

This model supports manual-supervised testing only.

DDA / Daily Driver Agent remains Yellow until a supervised run proves that it can produce a complete orientation brief, state object, pre-staged artifact, trace log, and run summary without crossing approval boundaries.

This document should not be used as evidence that automation, autonomous execution, or full runtime readiness is approved.

## Open Questions

- Where should the canonical Daily Driver state object live first: repo markdown, Notion, Linear, or a hybrid model?
- Which surfaces should be mandatory for a valid orientation brief?
- What fields are required for a trace note to be considered reviewable?
- How should Codex `/goal` context be represented in DDA artifacts?
- Which older daily artifacts should remain active, and which should become legacy or compatibility artifacts?
