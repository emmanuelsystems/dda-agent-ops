---
title: Todo Skill Sample Use Case
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
created: 2026-05-11
updated: 2026-05-11
---

# Todo Skill Sample Use Case

## Review Boundary

This is a draft/review-only sample. It does not approve the `/todo` skill as canonical DDA behavior, does not enable automation, and does not authorize Slack, Notion, GitHub, memory, or email writes.

## Source Context

- Latest reviewed DDA Driver loop workflow update: `#diarized-daily`, 2026-05-11 10:28 CST.
- Reference page: Riley Brown - Favorite Codex Skill (workflow-specific): <https://www.notion.so/3a7c0b1df5ff472abb76c569afaac967>
- Reference page: Using Claude Code: The Unreasonable Effectiveness of HTML (Thariq): <https://www.notion.so/51b3f702c9c0475192f04d663ab58237>
- Synthesis page: DDA Driver Loop - Skillized Todo Workflow Review: <https://www.notion.so/35d2570090e581348b15de4c37d85cf1>

## Why This Skill Fits

The DDA Driver loop needs a narrow way to turn mixed operating context into a reviewable action queue. The Riley Brown skill pattern supports this because `/todo` is a bounded job with required inputs, one fixed output artifact, constraints, checks, and done-when. The Thariq HTML pattern is useful later if the todo artifact becomes a visual review surface, but Markdown is the correct first format because the immediate output is a durable repo artifact.

## Sample Invocation

```text
/todo

CONTEXT: DDA Pilot 001 readiness
DEFAULT_OWNER: Emmanuel
TIMEZONE: Asia/Shanghai
MAX_TASKS: 10

INPUT_TEXT:
Create acceptance criteria for Pilot 001 readiness (minimum bar).
Need to decide where state-snapshot.md lives. Option A: repo runs/YYYY-MM-DD/. Option B: Notion page mirror.
Emmanuel to run 2 simulations and capture failure modes / friction (evidence packet style).
David: DDA should do a tight "session start" orientation brief, not journaling.
Check: does Slack integration allow reading public channels? what about private? clarify.
We should add a skill skeleton doc into KB as canonical template.
Next check-in next Tuesday afternoon.
```

## Expected Output

The skill writes one file:

`artifacts/todo.md`

Expected sections:

- `Context`
- `Now (Top 3)`
- `Task List`
- `Backlog / Parking lot`
- `Questions / Missing Info`

Expected task fields:

- priority
- owner
- due date
- next action
- definition of done
- source quote

## Observed Sample Output

`artifacts/todo.md` now contains a generated DDA Pilot 001 readiness queue with:

- P0 acceptance criteria.
- P0 state snapshot location proposal.
- P0 two readiness simulations and failure-mode capture.
- P1 session-start orientation criteria.
- P1 Slack public/private channel read capability clarification.
- P1 canonical skill skeleton KB task.
- P1 next Tuesday readiness check-in packet.

## Open Questions Captured By The Sample

- Confirm whether "next Tuesday afternoon" means 2026-05-12 afternoon in Asia/Shanghai, or a later Tuesday.
- Confirm the target KB location for the canonical skill skeleton doc.
- Confirm whether `state-snapshot.md` should be created during this readiness pass or only proposed for review.
- Confirm which Slack workspace and channels should be used to verify public/private read capability.

## Validation Notes

- The sample keeps repo truth local in `artifacts/todo.md`.
- The sample does not claim loop 003 runtime readiness.
- The sample does not use HTML because the first proof artifact is a task queue, not a visual review surface.
- The sample leaves unresolved decisions as questions instead of converting them into false commitments.

## Recommended Next Step

Review whether `skills/todo/SKILL.md` is acceptable as a draft repo-local skill. If approved later, decide whether it should remain under `skills/todo/`, move into a Codex user skill location, or become part of a broader Daily Driver skill packet.
