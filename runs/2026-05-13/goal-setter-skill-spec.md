---
title: Goal-Setter Skill Spec
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
created: 2026-05-13
updated: 2026-05-13
approval_status: not_approved
---

# Goal-Setter Skill Spec

## Review Boundary

This is a draft/review-only skill design artifact. It does not create or approve a runnable `SKILL.md`, does not update `skills/`, does not edit `AGENTS.md`, does not enable automation, and does not authorize Codex execution.

Human approval is required before this spec is promoted into `skills/goal-setter/SKILL.md`, committed, pushed, copied into another repo, or treated as an approved workflow.

## Purpose

Define a reusable skill-based goal setter that converts DDA-structured todos into strong, consistent Codex `/goal` prompts.

The skill has one job:

```text
Input: one DDA-structured todo packet
Output: one review-ready Codex /goal prompt plus goal packet fields
```

It should standardize the goal-generation procedure across repos and sessions without becoming a project manager, DDA replacement, Codex executor, or evaluator.

## Why A Reusable Skill Is A Candidate Surface

A reusable skill is the strongest first build candidate because the goal-setting behavior is:

- repeated
- narrow
- output-shaped
- repo-boundary sensitive
- easy to review manually
- portable across target repos
- aligned with the existing repo-local skill pattern

Verified current state:

- The repo already has `skills/todo/SKILL.md`, a narrow draft skill that converts raw notes into `artifacts/todo.md`.
- `runs/2026-05-11/codex-skill-goal-test-plan.md` recommends bounded skill specs with clear inputs, outputs, constraints, checks, and done-when.
- `symphony-pilot/docs/reference/skills-operating-model.md` says early skills should stay narrow, report-first, canonical-doc aware, and trialed before adoption.
- `symphony-pilot/docs/reference/target-repo-pilot-criteria.md` says DDA goal packets remain upstream durable artifacts and `/goal` remains a Codex handoff focus, not source of truth.

Design recommendation:

- Build the reusable skill contract first.
- Keep the first implementation draft-only and repo-local.
- Use it to generate comparable outputs for Notion and ChatGPT pilots.

## Candidate Skill Name

`goal-setter`

## Candidate Skill Description

Convert one DDA-structured todo packet into a review-ready Codex `/goal` prompt and goal packet. Use when DDA has selected or proposed execution-class work for Codex and the operator needs a bounded, source-grounded goal prompt with explicit inputs, outputs, acceptance criteria, and approval boundaries.

## Required Inputs

Require `DDA_TODO_PACKET`.

Minimum packet fields:

- `title`: one todo or requested outcome.
- `source`: where the todo came from.
- `source_status`: raw, draft, accepted working context, reviewed, durable, or unknown.
- `why_now`: priority, blocker, deadline, or active-lane reason.
- `desired_outcome`: concrete output expected from Codex.
- `target_repo`: repo path or `unknown`.
- `read_first`: files, pages, issues, or artifacts Codex should read before acting.
- `acceptance_criteria`: done-when checks.
- `approval_boundaries`: external writes and promotion gates.
- `out_of_scope`: exclusions and no-touch areas.
- `missing_info`: unresolved facts.

Optional inputs:

- `CURRENT_GOAL_PACKET`
- `DAILY_DRIVER_STATE`
- `ORIENTATION_BRIEF`
- `CODEX_HANDOFF_PACKET`
- `PREVIOUS_COMPLETION_PACKET`
- `EVALUATOR_FEEDBACK`
- `MAX_GOAL_LENGTH`
- `TARGET_REPO_RULES`

If `DDA_TODO_PACKET` is missing, the skill should ask for it rather than creating a goal.

## Required Outputs

The skill should produce one Markdown artifact or inline packet with these sections:

- `Goal readiness`: ready, split recommended, blocked, or DDA-only.
- `Selected todo`: normalized one-sentence todo.
- `Codex-owned outcome`: one outcome Codex can execute.
- `Codex /goal draft`: copy-ready prompt.
- `Read-first list`: exact source refs for Codex.
- `In scope`: allowed work.
- `Out of scope`: excluded work.
- `Approval boundaries`: no external writes or promotion without approval.
- `Acceptance criteria`: observable checks.
- `Return requirement`: Codex completion packet fields.
- `Open questions`: unresolved or blocking gaps.
- `Evaluator hooks`: fields a later evaluator can score.

Recommended output path for first implementation test:

`runs/YYYY-MM-DD/goal-setter-output.md`

## How It Would Standardize Goal Generation Across Repos Or Sessions

The skill should enforce a stable conversion algorithm:

1. Validate that the input is one todo, not a broad topic.
2. Decide whether the todo is Codex-owned, DDA-only, Notion-only, Linear-only, Slack-draft-only, or blocked.
3. If Codex-owned, convert the desired outcome into one bounded `/goal`.
4. Attach source refs as `Read first`.
5. Attach acceptance criteria as `Done when`.
6. Attach approval boundaries as `Do not`.
7. Attach completion return requirements as `Return`.
8. Attach missing facts as `Open questions`, not hidden assumptions.
9. Add evaluator hooks so the later evaluation layer can compare intent, execution, and output quality.

Standard `/goal` grammar:

```md
/goal Complete [one outcome] for [target repo/project]. Read first: [source refs]. Produce [specific output]. Keep in scope: [allowed work]. Do not [approval boundaries/out-of-scope items]. Done when [acceptance criteria]. Return a Codex-to-DDA completion packet with summary, files changed, decisions, checks, open questions, next steps, and DDA integration notes.
```

The grammar is intentionally explicit. It favors repeatability over elegant prose.

## Strengths For Portability / Repeatability

The skill surface is strongest because it:

- can be stored and reviewed in the repo
- can travel across Codex sessions
- can be tested against examples
- can preserve approval boundaries mechanically
- can make DDA todo structure consistent
- can produce comparable outputs for Notion and ChatGPT pilots
- can stay useful even if Notion or ChatGPT agent availability changes
- keeps the goal-setting procedure close to `AGENTS.md`, templates, and source-of-truth rules

Best use:

- first build surface
- draft-only goal prompt generation
- cross-repo handoff standardization
- long-task planning when a stable output contract matters
- evaluator-ready trace fields

## Weaknesses Or Risks

The skill is weaker when:

- the todo requires strategic discussion before it can be scoped
- current planning/task status lives only in Notion and is not supplied in the packet
- the operator wants conversational negotiation of tradeoffs
- the target repo context has changed and the skill is run without fresh reads
- the skill is treated as a source-of-truth replacement instead of a procedure

Specific risks:

- a too-rigid skill could produce a technically well-formed but strategically wrong goal
- portability can hide repo-specific constraints unless `TARGET_REPO_RULES` are read
- if promoted too early, it may encode current draft assumptions as policy
- if the skill writes artifacts automatically, it can create noise before the workflow is proven

## Constraints And Approval Boundaries

The skill must not:

- execute the generated `/goal`
- edit files outside the explicitly approved output artifact during first trial
- update Notion
- post to Slack
- send email
- save memory
- commit, push, branch, merge, or open pull requests
- enable automation
- change source-of-truth rules
- treat the generated `/goal` as approved
- collapse DDA, goal-setter, Codex, and evaluator roles

The skill may:

- read supplied source refs
- produce a draft goal packet
- identify missing inputs
- mark a goal blocked
- recommend a surface route
- produce evaluator hooks

## Checks

Before returning, the skill should verify:

- exactly one primary outcome is present
- source refs are listed or marked missing
- target repo/surface is listed or marked unknown
- acceptance criteria are observable
- approval gates are explicit
- external writes are not authorized by implication
- DDA remains the todo/alignment source
- Codex remains the executor
- evaluator remains separate
- output is draft/review-only

## Done-When

The skill run is done when a reviewer can answer:

- What todo was converted?
- What should Codex do?
- What should Codex read first?
- What must Codex not do?
- How will completion be judged?
- What should Codex return to DDA?
- What facts are still missing?
- What should the evaluator score later?

## Open Questions And Risks

- Should the first implementation write a file or only return inline output?
- Should the skill live under `skills/goal-setter/` in this repo or under a user-level Codex skill folder after review?
- Should the skill accept multiple todos and force selection, or require DDA to select one before handoff?
- What evaluator rubric should become mandatory after the first pilot?
- Which target repo rules should be included by default for `dda-agent-ops` vs future target repos?
- Should `templates/goal-packet.md` be revised after the pilot, or should the skill adapt to the existing template first?

## Pilot Recommendation For This Surface

Build this surface first, but only as a draft/review-only skill spec or trial `SKILL.md` after approval.

First test:

1. Use the existing `artifacts/todo.md` or a fresh DDA todo packet as input.
2. Generate one `/goal` prompt for a docs-only Codex task.
3. Have ChatGPT workspace critique the generated prompt.
4. Optionally have Notion AI generate its own draft from the same todo.
5. Compare outputs using the evaluator hooks before any promotion.
