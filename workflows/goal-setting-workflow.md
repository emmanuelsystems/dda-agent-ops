---
title: Goal Setting Workflow
asset_type: workflow
status: draft
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: workflows/goal-setting-workflow.md
created: 2026-05-07
updated: 2026-05-07
---

# Goal Setting Workflow

## Purpose

Define how DDA should turn scattered work context into one active goal before it builds an orientation brief, pre-stages an artifact, or routes execution work to Codex.

This workflow is the repo-backed draft for the DDA `/goal` operating pattern.

Codex CLI currently exposes an under-development `goals` feature in this workspace. DDA may use that feature as a downstream execution focus tool, but the Codex CLI goal is not a replacement for the DDA goal packet, source evidence, approval boundaries, or durable artifacts.

## Why This Exists

Daily Driver work depends on knowing what the operator is actually trying to advance.

When work spans ChatGPT, Notion AI, Codex, Linear, Slack, GitHub, and repo artifacts, the goal can drift. A clear goal-setting workflow gives DDA a stable first step:

```txt
messy context -> candidate goals -> selected active goal -> state object -> orientation brief -> pre-staged artifact
```

When execution is routed to Codex, the flow extends to:

```txt
DDA goal packet -> Codex CLI /goal -> Codex execution session -> Codex completion packet -> DDA state refresh
```

## Trigger Conditions

Use this workflow when:

- the operator says `/goal`
- the operator wants to set or refine a Codex CLI `/goal`
- the operator asks what the current goal is
- the operator wants to continue a work loop from scattered context
- DDA is about to produce an orientation brief
- DDA is about to pre-stage an artifact
- multiple surfaces disagree about the next action
- a Linear issue, Slack thread, Notion note, or Codex session needs a shared goal

## Inputs

DDA may use these inputs when available:

- operator statement of intent
- David's latest reviewed direction
- active Linear issue
- relevant Slack thread or channel update
- Notion project context
- repo docs, templates, schemas, or run artifacts
- Codex handoff or completion packets
- current Daily Driver state object
- open questions or blocked decisions

If a required input is missing, DDA should ask for it or mark it as an assumption. It should not silently invent source evidence.

## Output

The workflow produces a `goal-packet.md` artifact or an inline goal packet with the same sections.

The output should be short enough to use as working context, but specific enough to route work.

When the dispatch lane is Codex, the output should also include a **Codex CLI Goal Handoff** section with a concise goal string the operator can use in the Codex CLI `/goal` command.

## Workflow Steps

### 1. Gather Candidate Context

Collect the smallest evidence set needed to understand the work.

Minimum evidence should include:

- direct operator intent
- latest reviewed David direction when relevant
- active issue or task reference when relevant
- newest durable repo or run artifact when relevant

### 2. Extract Candidate Goals

Identify possible goals from the evidence.

Each candidate goal should be phrased as an outcome, not a topic.

Weak:

`Work on DDA.`

Better:

`Define the Daily Driver goal-setting workflow so DDA can orient across surfaces before pre-staging artifacts.`

### 3. Select The Active Goal

Choose one active goal for the current work loop.

Selection rules:

- Prefer the newest reviewed instruction over older context.
- Prefer explicit operator direction over inferred intent.
- Prefer active Linear or Notion task framing for task status.
- Prefer GitHub/repo for agent source, templates, schemas, and version history.
- If two goals conflict, mark the conflict instead of merging them silently.

### 4. Define Goal Boundaries

State what the goal includes and excludes.

Boundaries should prevent DDA from:

- executing Codex work inline
- posting externally without approval
- treating drafts as durable truth
- upgrading readiness without proof
- expanding a narrow goal into unrelated refactors

### 5. Map Surfaces

List the active surfaces needed to advance the goal.

For each surface, capture:

- why it matters
- whether it is source, planning, discussion, execution, or trace context
- whether it has been checked in the current run
- what gap remains

### 6. Define The First Action

Recommend the first concrete action after the goal is set.

The first action should be one of:

- build orientation brief
- refresh Daily Driver state
- pre-stage artifact
- create Codex handoff
- draft Slack update
- draft Linear comment
- draft Notion summary
- ask operator for missing decision
- stop because the goal is blocked

### 7. Record Trace

Capture the evidence supporting the active goal.

At minimum, trace should include:

- source surface
- source reference
- claim supported
- confidence
- open gap

### 8. Mark Approval Gates

Before any external action, mark required approvals.

Common approval gates:

- Slack posting
- Notion update
- memory save
- email send
- commit or push
- automation enablement
- source-of-truth change
- runtime readiness claim

### 9. Prepare Codex CLI Goal Handoff When Needed

If the selected dispatch lane is Codex, translate the DDA goal packet into a concise Codex CLI goal.

The Codex CLI goal should:

- state one implementation or repo-work outcome
- include the most important boundaries
- mention required review status
- avoid broad project context that belongs in the DDA goal packet
- preserve approval gates such as no commit, push, external post, memory save, Notion update, or readiness promotion without approval

The Codex CLI goal should not:

- replace the DDA goal packet
- omit source evidence or approval boundaries from the broader workflow
- claim that under-development CLI goal behavior is stable
- become durable truth unless captured in a reviewed artifact

Example DDA active goal:

```md
Define the Daily Driver Agent goal/state/pre-stage workflow and package the May 7 SSI-113 evidence packet without promoting readiness beyond Yellow.
```

Example Codex CLI `/goal` handoff:

```md
Implement the Daily Driver v0.1 repo artifacts for goal-setting, state tracking, pre-staging, and May 7 evidence capture. Keep changes draft/review-only, preserve Yellow readiness, and do not commit or push without approval.
```

## Goal Quality Rules

A valid active goal should be:

- specific
- outcome-based
- bounded
- traceable to evidence
- useful for deciding the next action
- narrow enough for one work loop

A goal is not valid if it:

- is only a theme
- contains multiple unrelated outcomes
- depends on unverified evidence without marking that gap
- requires external action without approval
- collapses DDA and Codex responsibilities

## Relationship To Daily Driver State

The active goal becomes the `active_goal` field in `schemas/daily-driver-state-object.md`.

The goal source becomes the `goal_source` field.

The goal's evidence becomes part of the state object's `trace_log`.

The recommended first action informs the state object's `dispatch_lane` and `pre_staged_artifacts`.

If a Codex CLI goal is generated, capture it in the state object's `latest_outputs`, `pre_staged_artifacts`, or trace notes as a draft execution focus item. Do not treat it as durable truth unless it is reviewed and saved in a repo artifact, Linear comment, Notion page, or other approved surface.

## Relationship To Orientation Brief

DDA should not create an orientation brief until it has either:

- a clear active goal, or
- a clearly marked blocked goal decision

The orientation brief should use the goal packet as its first input.

## Manual-Supervised Boundary

This workflow is manual-supervised for v0.1.

DDA may draft a goal packet, recommend a first action, and prepare a Codex CLI `/goal` handoff string. It must not execute external updates, commit repo changes, update Notion, post to Slack, save memory, or enable automation without explicit approval.

The Codex CLI `goals` feature is under development in this workspace. Treat it as session guidance, not a stable source-of-truth mechanism.

## Pass Criteria

The workflow passes when:

- one active goal is selected or a blocked goal decision is marked
- source evidence is listed
- boundaries are explicit
- first action is concrete
- approval gates are visible
- the goal can feed a Daily Driver state object or orientation brief
- Codex CLI goal handoff is present when the dispatch lane is Codex

## Fail Criteria

The workflow fails when:

- the goal is too broad to route work
- DDA merges conflicting goals without saying so
- source evidence is missing
- approval gates are omitted
- the first action is vague
- DDA treats the goal packet as final durable truth before review
- DDA treats Codex CLI `/goal` as a replacement for reviewed DDA state or source-of-truth artifacts

## Related Artifacts

- `docs/daily-driver-operating-model.md`
- `schemas/daily-driver-state-object.md`
- `templates/goal-packet.md`
- `templates/orientation-brief.md`
