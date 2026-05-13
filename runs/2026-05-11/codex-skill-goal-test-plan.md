---
title: Codex Skill Goal Test Plan
asset_type: run_artifact
status: draft
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
created: 2026-05-11
updated: 2026-05-11
---

# Codex Skill Goal Test Plan

## Source Page

- Notion page: Riley Brown - Favorite Codex Skill (workflow-specific)
- Source URL: https://www.notion.so/3a7c0b1df5ff472abb76c569afaac967
- Page status: Draft
- Core claim: high-leverage Codex skills package repeated workflows into bounded jobs with clear inputs, outputs, constraints, checks, and done-when.

## Analysis

The page is useful less as a Riley-specific implementation and more as a reusable operating pattern:

1. Identify a workflow that repeats often enough to justify skillizing.
2. Convert it into a narrow job, not a broad assistant persona.
3. Require explicit inputs and a fixed output artifact.
4. Preserve constraints and approval boundaries inside the skill.
5. Define checks and done-when before execution starts.

This maps directly onto the DDA repo because DDA already has a repeatable boundary:

- DDA owns daily alignment.
- Codex owns build and research execution.
- Durable artifacts own truth.
- Handoffs and completions already have templates.

## Recommended Test Use Case

Skillize the DDA-to-Codex handoff loop.

This is the strongest first test because it is repeated, bounded, repo-native, and already covered by templates:

- Input template: `templates/dda-to-codex-handoff.md`
- Output template: `templates/codex-to-dda-completion.md`
- Goal wrapper: `templates/goal-packet.md`
- Candidate skill list: `agents/diarized-daily-assistant/skills.md`

## `/goal` Draft

```md
Test the Codex Skill pattern by converting the DDA-to-Codex handoff loop into a bounded skill spec. Use the existing repo templates as inputs, keep the output draft/review-only, and produce one reviewable Markdown artifact that defines the skill goal, required inputs, fixed output, constraints, checks, and done-when. Do not commit, push, post externally, update Notion, create automations, or treat the skill as approved.
```

## Skill Spec Skeleton

### Goal

Turn a DDA handoff packet into a Codex-ready execution packet and require Codex to return a completion packet with traceable decisions, files changed, open questions, next steps, and DDA integration notes.

### Inputs

- A filled or partially filled DDA handoff packet.
- Relevant repo paths or source artifacts.
- Current approval boundaries.
- Optional active goal packet.

### Output Artifact

- Preferred path for test run: `runs/2026-05-11/dda-to-codex-skill-spec.md`
- Format: Markdown
- Status: draft/review-only

### Steps

1. Read the handoff packet and identify task, context, inputs, expected output, acceptance criteria, constraints, and return requirement.
2. Check the relevant repo source files before assuming current truth.
3. Normalize the handoff into a Codex execution plan.
4. Preserve approval boundaries explicitly.
5. Produce or update only the approved draft artifact.
6. Return a completion packet using the Codex-to-DDA completion structure.

### Constraints

- Do not assume direct Notion, Slack, Gmail, Calendar, GitHub, or Codex integrations exist unless confirmed.
- Do not create automations.
- Do not treat chat history as durable truth.
- Do not overwrite approved source files without preserving changelog context.
- Do not commit or push without explicit human approval.
- Keep outputs draft/review-only until reviewed.

### Checks

- The skill has one clear job.
- Inputs are explicit.
- Output path and format are explicit.
- Approval boundaries are preserved.
- Completion return format is defined.
- No external write is performed.

### Done-When

- A reviewer can run the skill from a DDA handoff packet without re-explaining the workflow.
- The output artifact has a stable structure.
- The completion packet tells DDA what changed, what remains open, and what should carry into daily alignment.

## Candidate Follow-Up Artifact

If approved, the next artifact should be:

`runs/2026-05-11/dda-to-codex-skill-spec.md`

That artifact can later be promoted into `agents/diarized-daily-assistant/skills.md` or a dedicated `skills/` entry only after review.

## Approval Boundaries

- Human approval is required before promoting this draft into source files.
- Human approval is required before saving persistent memory or updating Notion.
- Human approval is required before committing, pushing, or opening a pull request.

## Recommendation

Use this test as a review-only `/goal` run. If the resulting skill spec works, the same pattern can be repeated for morning planning, midday recenter, evening report, memory candidate extraction, and orientation brief generation.
