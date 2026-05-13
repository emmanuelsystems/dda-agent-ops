---
title: DDA to Codex Handoff Skill Spec
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
source_templates:
  - templates/dda-to-codex-handoff.md
  - templates/codex-to-dda-completion.md
created: 2026-05-11
updated: 2026-05-11
approval_status: not_approved
---

# DDA to Codex Handoff Skill Spec

## Review Boundary

This is a draft/review-only skill spec. It is not an approved Codex skill, not an automation, and not a source-of-truth rule change.

Human approval is required before this draft can be promoted into `skills/`, copied into an executable `SKILL.md`, committed, pushed, posted externally, added to Notion, or used as an approved operating procedure.

## Candidate Skill Name

`dda-codex-handoff-completion`

## Skill Goal

Convert a DDA handoff packet into a bounded Codex execution loop, then require Codex to return a completion packet that DDA can use for daily alignment, carryovers, repo traceability, and review-ready follow-up.

The skill has one job: preserve the DDA-to-Codex boundary while making a handoff actionable and making the Codex return artifact predictable.

## When To Use

Use this skill when DDA has a task that requires Codex to do build work, research, repo edits, artifact drafting, prompt refactoring, skill generation, automation planning, or verification.

Do not use this skill for routine daily alignment that DDA can handle without Codex execution.

## Required Inputs

The caller must provide a filled or partially filled DDA handoff packet based on `templates/dda-to-codex-handoff.md`.

Required handoff fields:

- `Task`: the concrete job Codex is being asked to complete.
- `Context`: why the task matters and what background Codex needs.
- `Inputs`: repo paths, source artifacts, packet links, issue references, or other durable evidence Codex should read.
- `Expected Output`: the artifact, patch, report, packet, or verification result Codex should produce.
- `Acceptance Criteria`: the observable checks that decide whether the Codex work is complete.
- `Constraints`: the approval boundaries and unsafe assumptions Codex must preserve.
- `Return Requirement`: confirmation that Codex must return a completion packet.

Optional inputs:

- Active goal packet or run packet.
- Relevant source-of-truth notes.
- Known approval boundary for Slack, Notion, email, GitHub, automation, or memory updates.
- Target path for the output artifact.
- Known reviewer or routing surface.

## Fixed Output

Codex must return one completion packet based on `templates/codex-to-dda-completion.md`.

The completion packet must include:

- `Summary`: what Codex completed.
- `Files Created or Updated`: table of changed paths and notes.
- `Decisions Made`: implementation or drafting decisions Codex made.
- `Open Questions`: unresolved items that still need a human, DDA, or source-of-truth check.
- `Recommended Next Steps`: ordered next actions.
- `DDA Integration Notes`: what DDA should carry into reports, carryovers, Slack-safe summaries, memory candidates, Notion logs, or PRD updates.

If Codex cannot complete the requested work, the fixed output is still a completion packet, but the `Summary`, `Open Questions`, and `Recommended Next Steps` must clearly state the blocker and the safest next move.

## Operating Steps

1. Read the DDA handoff packet.
2. Extract the task, context, inputs, expected output, acceptance criteria, constraints, and return requirement.
3. Read the repo paths or durable artifacts named in the handoff before treating any claim as current truth.
4. Identify whether the task is draft-only, review-ready, or approved for external action.
5. Execute only the work allowed by the handoff constraints and repo instructions.
6. Preserve DDA/Codex ownership:
   - DDA owns daily alignment.
   - Codex owns build and research execution.
   - Automations own recurrence.
   - Durable artifacts own truth.
7. Produce the expected output artifact, patch, report, or verification result.
8. Return the Codex-to-DDA completion packet.

## Constraints

- Do not assume direct Notion, Slack, Gmail, Calendar, GitHub, Codex, or automation integrations exist unless confirmed.
- Do not treat raw chat history as durable truth.
- Do not auto-create automations.
- Do not store private reflection in team-facing files.
- Do not collapse DDA and Codex responsibilities.
- Do not overwrite approved source files without preserving changelog context.
- Do not mark speculative assumptions as facts.
- Do not post to Slack, send email, update Notion, save persistent memory, create pull requests, merge pull requests, enable automations, commit, or push without explicit human approval.
- Do not treat a draft skill spec as approved.
- If Notion and GitHub conflict, preserve the repo's source-of-truth split instead of guessing:
  - planning and active task status: Notion wins unless mirrored to GitHub issues.
  - prompt and agent source files: GitHub wins.
  - version history: GitHub wins.
  - discussion and context: newest reviewed artifact wins.

## Checks

Before returning the completion packet, Codex must verify:

- The task from the handoff is restated clearly in the completion summary.
- Every required handoff input was read, used, or explicitly marked unavailable.
- The expected output is present or the blocker is stated.
- Acceptance criteria are addressed one by one.
- Approval boundaries are preserved.
- Any changed files are listed with paths.
- Any assumptions are labeled as assumptions.
- Any external writes are absent unless explicitly approved.
- The completion packet includes DDA integration notes.

## Done-When

The loop is done when:

- A reviewer can compare the DDA handoff packet to the Codex completion packet without reconstructing missing context.
- Codex has produced the requested output or named the blocker preventing completion.
- The completion packet identifies files changed, decisions made, open questions, recommended next steps, and DDA integration notes.
- The DDA/Codex boundary remains intact.
- No unapproved external action, automation, commit, push, Notion update, Slack post, email, memory write, PR creation, or source-of-truth change occurred.

## Failure Modes To Catch

- The handoff is too vague to execute, but Codex proceeds anyway.
- Codex uses chat memory as truth instead of reading durable artifacts.
- Codex completes the work but does not return a completion packet.
- Codex changes source files when the handoff only requested a review artifact.
- Codex posts, commits, pushes, or updates an external surface without approval.
- The completion packet omits DDA integration notes, leaving DDA without a clean daily-alignment carryover.

## Promotion Notes

If reviewed and approved later, this draft could become a real skill under `skills/dda-codex-handoff-completion/SKILL.md`.

Minimum promotion requirements:

- Human review confirms the skill name, trigger conditions, constraints, and fixed output.
- A reviewer decides whether this belongs in `skills/` or remains a run artifact.
- The approved version keeps `SKILL.md` concise and moves examples or long references into optional bundled resources only if needed.
- The repo changelog or relevant source file records the promotion context if this becomes an approved source artifact.
