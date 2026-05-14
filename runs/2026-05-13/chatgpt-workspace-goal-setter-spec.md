---
title: ChatGPT Workspace Goal-Setter Spec
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

# ChatGPT Workspace Goal-Setter Spec

## Review Boundary

This is a draft/review-only design artifact. It does not create a ChatGPT workspace agent, configure a GPT, create a skill, update project instructions, save memory, or authorize Codex execution.

Human approval is required before this spec is copied into a ChatGPT workspace agent, converted into instructions, committed, pushed, or treated as an approved operating procedure.

## Purpose

Define how a ChatGPT workspace goal-setter agent could work with the operator to turn DDA-structured todos into consistent Codex `/goal` prompts.

The ChatGPT workspace goal setter should sit between DDA and Codex:

```text
DDA structures todos
-> ChatGPT workspace goal setter refines the goal with the operator
-> Codex receives a bounded /goal prompt
-> evaluator scores the result later
```

This surface is best understood as a conversational refinement and simulation surface, not the durable source of truth.

## Why ChatGPT Workspace Is A Candidate Surface

ChatGPT workspace is a candidate because goal setting often needs fast back-and-forth:

- clarifying what outcome the operator actually wants
- testing whether the todo is too broad
- splitting an overloaded todo into one Codex-sized work slice
- comparing candidate `/goal` phrasings
- turning messy DDA todo packets into operator-approved goal language
- simulating how Codex might misunderstand the prompt before execution

Verified current state:

- The fetched Agentic Team Deployment Context positions ChatGPT as the research, synthesis, prompt-package, simulation, and orchestration surface.
- The DDA architecture decisions preserve DDA as daily alignment and Codex as execution, with a manual artifact bridge for now.
- The field-guide notes frame `/goal` as a durable execution lane for bounded work, while DDA remains workflow intelligence and evidence structure.

Design recommendation:

- Use ChatGPT workspace as the best human-collaboration surface for refining difficult goals.
- Do not make it the canonical source for goal rules unless the final contract is saved into reviewed repo artifacts.

## Required Inputs

The ChatGPT workspace goal setter should accept the same normalized DDA todo packet as the other surfaces.

Minimum DDA todo handoff fields:

- `todo_title`: one action-oriented todo.
- `source_context`: where the todo came from and why it matters.
- `desired_outcome`: expected end state.
- `evidence_refs`: repo paths, Notion pages, Linear issues, Slack links, or DDA artifacts.
- `target_surface`: repo, Notion, Linear, Slack draft, research brief, unknown, or mixed.
- `known_constraints`: approval gates, readiness boundaries, no-touch areas, review status.
- `acceptance_criteria`: done-when checks.
- `missing_info`: unresolved facts DDA identified.

Recommended extra inputs:

- Current `templates/goal-packet.md` shape.
- Current `workflows/goal-setting-workflow.md` rules.
- Current `templates/dda-to-codex-handoff.md` and `templates/codex-to-dda-completion.md` when execution is likely.
- Prior evaluator notes when available.

The workspace agent should ask at most one or two clarification questions when the todo is under-specified. If the missing fact can be safely marked as an assumption, it should proceed and label the assumption.

## Required Outputs

The ChatGPT workspace goal setter should produce:

1. `Goal diagnosis`: whether the todo is ready, too broad, blocked, or should be split.
2. `Recommended goal frame`: one outcome-based goal.
3. `Codex /goal draft`: copy-ready prompt.
4. `Why this phrasing`: short rationale for operator review.
5. `Read-first context`: source files/pages/issues Codex should read before acting.
6. `Boundaries`: what Codex must not do.
7. `Acceptance criteria`: checks Codex should satisfy.
8. `Return requirement`: expected Codex completion packet.
9. `Open questions`: unresolved facts and whether they block execution.

Suggested output format:

````md
## Goal Diagnosis
[ready | too broad | blocked | split recommended]

## Recommended Codex /goal
```md
/goal [bounded outcome]. Read first: [source refs]. Produce: [output]. Do not: [boundaries]. Done when: [acceptance criteria]. Return: [completion packet].
```

## Operator Review Notes
- Why this goal is the right slice:
- What was excluded:
- What is still unknown:
````

## Strengths For Conversational Refinement And Operator Collaboration

ChatGPT workspace is strongest when:

- the operator is still deciding scope
- DDA has multiple candidate todos and needs help picking one Codex-sized slice
- the todo has strategic nuance that should be discussed before execution
- the goal needs to be rewritten several times before it becomes precise
- the same goal should be simulated against likely Codex failure modes
- the output should remain in chat for immediate human review before being copied into Codex

Best use:

- goal-quality rehearsal
- prompt phrasing refinement
- long-task planning before a repo execution run
- splitting broad todos into several candidate `/goal` prompts
- operator-facing explanation of tradeoffs

## Weaknesses Or Risks

ChatGPT workspace is weaker when:

- the source context is not attached or searchable in the current workspace
- repo truth has changed since the conversation context was loaded
- the agent relies on memory-like conversation continuity instead of fresh source reads
- the operator expects the chat output to become durable without saving it in repo/Notion/issue artifacts
- the workspace agent grows into a broad project manager instead of a narrow goal-setter

Specific risks:

- conversational drift can make the output feel persuasive but under-sourced
- project instructions may become stale
- connected app availability may differ from what the prompt assumes
- the workspace agent may blur DDA and goal-setter responsibilities if not constrained
- if goal-setting happens only in chat, future evaluators may not know which source evidence shaped the prompt

## Constraints And Approval Boundaries

The ChatGPT workspace goal setter must not:

- execute Codex tasks
- edit repo files
- update Notion
- post to Slack
- send email
- save persistent memory
- create branches, commits, pull requests, pushes, or merges
- enable automation
- change source-of-truth rules
- treat chat history as durable truth
- merge DDA, goal-setter, Codex, and evaluator roles

The agent may:

- draft candidate goal prompts
- ask bounded clarification questions
- simulate likely failure modes
- recommend whether the goal should route to Codex, DDA, Notion, Linear, or a blocked decision
- produce a copy-ready goal packet for human review

Human approval is required before any generated `/goal` is used for execution.

## Open Questions And Risks

- ChatGPT workspace agent availability and configuration were not verified in this run.
- Workspace-level memory, file access, and connector behavior were not verified.
- The exact relationship between a ChatGPT workspace agent and reusable Codex skills remains a design decision.
- It is not yet clear whether this should be a full workspace agent, a project instruction set, or a prompt package used manually.
- The evaluator layer has not yet been specified, so feedback fields must remain provisional.
- Long-running tasks may exceed what a chat-only surface can track unless the goal packet is saved to a durable artifact.

## Pilot Recommendation For This Surface

Do not build ChatGPT workspace goal setter first as a persistent agent.

Use ChatGPT workspace first as a manual test harness after the reusable skill contract exists. Ask it to refine and challenge the skill-generated `/goal` prompt for one DDA-derived todo. If it consistently improves the prompt, then promote those refinement questions back into the skill spec.
