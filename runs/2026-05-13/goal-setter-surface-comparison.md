---
title: Goal-Setter Surface Comparison
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

# Goal-Setter Surface Comparison

## Review Boundary

This is a draft/review-only comparison and recommendation artifact. It does not approve a Notion AI agent, ChatGPT workspace agent, reusable skill, automation, external write, repo commit, or Codex execution.

## Progress Log

- Reviewed repo boundary rules, source-of-truth rules, Daily Driver operating model, goal-setting workflow, goal packet template, May 7 goal packet, and May 11 `/todo` and skill artifacts.
- Reviewed `symphony-pilot` repo-boundary, target-repo pilot, skills operating model, skill prep, and parallel execution docs.
- Read relevant Notion planning pages in read-only mode: DDA Pilot Build Brief, DDA Agent Architecture Decisions, Codex Operating Model, Agentic Team Deployment Context and Research, SSI Agent Orchestration Field Guide notes, and DDA / Workspace Agents Review & Feedback Log.
- No Slack, Notion, Linear, memory, commit, push, branch, PR, runtime, or config writes were performed.

## Current Verified State

- DDA owns daily alignment, orientation, todo structuring, pre-staging, trace, and routing.
- The goal-setting layer is not yet implemented as an agent or skill.
- Codex owns build/research/repo execution after a bounded handoff.
- `/goal` should be treated as a Codex execution focus, not the durable source of truth.
- The evaluator layer is future work and should remain separate from DDA, goal setter, and Codex.
- `dda-agent-ops` is still Yellow/manual-supervised and should not be described as autonomous or Green.
- Notion planning pages are useful source context but many are draft or accepted working context, not final canon.
- Repo artifacts own prompt, workflow, template, skill, schema, and eval source after review and commit.

## DDA Todo Structure Before Goal-Setter Handoff

DDA should not hand raw todos or chat snippets directly to any goal setter. It should normalize the todo first.

Minimum DDA todo packet:

```yaml
todo_id: optional stable id
todo_title: one action-oriented todo
source_surface: notion | linear | slack | repo | chat | mixed
source_ref: link, path, issue id, or artifact ref
source_status: raw | draft | accepted_working_context | reviewed | durable | unknown
why_now: priority, blocker, deadline, active lane, or operator instruction
desired_outcome: concrete end state
target_repo_or_surface: repo/path/surface or unknown
read_first:
  - path or page or issue
acceptance_criteria:
  - observable done condition
approval_boundaries:
  - no Slack post without approval
  - no Notion write without approval
  - no memory save without approval
  - no commit/push/PR without approval
out_of_scope:
  - excluded work
missing_info:
  - unresolved fact or decision
return_requirement: Codex-to-DDA completion packet
```

DDA should mark a todo as blocked when the desired outcome, source, target repo/surface, or approval boundary is too unclear to safely convert into a `/goal`.

## Side-By-Side Comparison

| Surface | Best For | Weak At | Source Posture | Output Quality Risk | Write Risk | Build Complexity |
|---|---|---|---|---|---|---|
| Notion AI goal-setter agent | Planning/task context, project status, Notion research synthesis, draft goal packets close to active work | Repo-source fidelity, permission clarity, silent status promotion, overusing draft planning context | Notion wins for planning/status; repo wins for prompt/source/skill rules | May overweight Notion context and under-read repo | Medium if write permissions exist | Medium/high because permissions and page destinations must be designed |
| ChatGPT workspace goal-setter agent | Conversational refinement, operator collaboration, goal simulation, ambiguity resolution | Durable trace, source freshness, repeatability across sessions, canonical storage | Chat is working context only unless output is saved | Persuasive but under-sourced goals | Low/medium depending connectors and memory | Medium because instructions/files/workspace behavior must be configured |
| Reusable skill-based goal setter | Standardized prompt generation, portability, repeatability, repo-native review, evaluator hooks | Strategic negotiation, live Notion task context unless supplied, nuanced operator tradeoffs | Repo-backed procedure; canonical docs outrank skill | Rigid but traceable goals | Low in draft-only mode | Low/medium because first build can be a narrow `SKILL.md` |

## What Each Surface Is Best For

### Notion AI

Best for:

- reading planning and task context near the source
- summarizing project state before a goal is framed
- identifying conflicting Notion tasks or draft context
- producing draft goal packets inside a planning workflow
- later filing or routing goal packets after write approval

Do not use first for:

- canonical goal rules
- repo-source transformations without explicit repo source refs
- automated task/page writes

### ChatGPT Workspace

Best for:

- operator-facing conversation
- refining ambiguous goals
- comparing candidate `/goal` phrasings
- simulating how Codex might misunderstand the prompt
- turning strategy-heavy todos into one bounded execution prompt

Do not use first for:

- durable storage
- source-of-truth updates
- unattended goal generation

### Reusable Skill

Best for:

- first build surface
- repeatable goal grammar
- cross-session and cross-repo portability
- approval-boundary preservation
- evaluator-ready output fields
- keeping goal-setting close to repo instructions and templates

Do not use first for:

- strategic debate
- broad planning context synthesis
- Notion task-state discovery unless the DDA packet supplies the task context

## What Should Be Built First

Build the reusable skill-based goal setter first.

Reason:

- It is the narrowest and most reviewable surface.
- It aligns with existing repo-local skill patterns.
- It can be tested without Notion, Slack, Linear, memory, commits, or automation writes.
- It gives Notion and ChatGPT a shared output contract to compare against.
- It keeps the goal-generation rules in the repo where skill specs and workflow source belong.

The first build should be draft-only:

- candidate path: `skills/goal-setter/SKILL.md`
- only after human approval
- no `AGENTS.md` trigger at first
- no scripts
- no external writes
- trial output path: `runs/YYYY-MM-DD/goal-setter-output.md`

## What Should Be Tested First

Test the skill-generated goal first, with ChatGPT workspace as the critique/refinement surface.

This separates build from evaluation:

- Skill generates the standardized `/goal`.
- ChatGPT workspace critiques clarity, scope, and likely Codex failure modes.
- Human selects or edits the final prompt.
- Codex executes only if the human approves the actual `/goal`.
- Evaluator later scores the result.

Do not test Notion writes first. The first Notion test should be draft-only and comparative, after the skill output contract exists.

## Smallest Useful Pilot Loop

Use one DDA-derived todo and one docs-only Codex task.

Pilot loop:

1. DDA produces one normalized todo packet from an existing source such as `artifacts/todo.md` or a current DDA planning note.
2. Skill-based goal setter converts it into one `/goal` prompt and a goal packet.
3. ChatGPT workspace reviews the prompt for ambiguity, overreach, missing source refs, and likely Codex failure modes.
4. Human approves the final `/goal` or marks it blocked.
5. Codex runs the approved `/goal` against a low-risk docs/spec artifact only.
6. Codex returns a Codex-to-DDA completion packet.
7. Evaluator scores:
   - goal matched todo
   - source refs were sufficient
   - boundaries were preserved
   - Codex completed the requested output
   - no unauthorized writes occurred
   - completion packet gave DDA useful carryover
8. DDA updates the next todo/goal quality notes as a draft, with no memory, Notion, Slack, Linear, or commit action unless approved.

Minimum pilot artifact set:

- `runs/YYYY-MM-DD/dda-todo-packet.md`
- `runs/YYYY-MM-DD/goal-setter-output.md`
- `runs/YYYY-MM-DD/codex-goal-completion.md`
- `runs/YYYY-MM-DD/goal-quality-eval.md`

## Recommended Next Artifact After This Spec Pass

Recommended next artifact:

`runs/YYYY-MM-DD/goal-setter-pilot-test-plan.md`

It should define:

- the exact DDA todo input
- the chosen low-risk docs-only Codex task
- the first draft `/goal`
- the evaluator rubric
- pass/fail criteria
- allowed files
- no-touch files
- approval gates
- stop conditions

Do not create the skill implementation until this test plan is reviewed or the operator explicitly approves implementation.

## Build Order Recommendation

1. Draft/review `goal-setter-skill-spec.md`.
2. Create `goal-setter-pilot-test-plan.md`.
3. If approved, implement a draft `skills/goal-setter/SKILL.md`.
4. Run one manual skill-generated `/goal` pilot on a docs-only task.
5. Use ChatGPT workspace to critique and improve the prompt.
6. Use Notion AI in draft-only mode to compare context-aware goal drafting from a Notion planning page.
7. Promote only the pieces that improve goal quality without weakening source-truth and approval boundaries.

## Open Questions

- Should DDA always select exactly one todo before goal-setting, or should the goal setter select among candidates?
- Should the first skill implementation write a file or return inline output only?
- What is the evaluator rubric and who owns it?
- Which Notion page/database should store draft goal packets if Notion becomes an approved surface?
- Should ChatGPT workspace be a persistent agent, a Project instruction, or a reusable prompt package?
- How much repo context should be embedded in the skill versus read fresh from repo files?
- When is a `/goal` prompt considered reviewed enough to execute?
- How should long-running Codex goals checkpoint back to DDA without turning DDA into the executor?
