# DDA to Codex Handoff Packet

**Date:** 2026-05-04
**Prepared By:** DDA
**Target Executor:** Codex
**Status:** Draft handoff packet
**Execution Slice:** Workspace Agents PRD v0.3 planning/update

## Task

Prepare the next DDA PRD v0.3 execution slice from the verified Workspace Agents source and PRD requirements.

Codex should produce a bounded repo-ready plan or draft patch for updating `agents/diarized-daily-assistant/prd.md` from v0.2 toward v0.3, without changing unrelated source files unless the acceptance criteria require cross-link notes.

## Context

The May 4 run resolved the earlier Workspace Agents source gap. The durable planning source is the Notion project page `Transforming DABs Into Workspace Agents`, not a page literally named `Workspace Agents updates`.

The alignment delta shows that the current repo PRD v0.2 is narrower than the Notion `DDA PRD Update Requirements` page. The repo PRD covers the manual pilot baseline, but it does not yet include the full v2 architecture, responsibility boundaries, app strategy, memory governance, reporting boundaries, improvement loop, feature IDs, user stories, risks, success metrics, and preserved open questions called out in Notion.

This handoff should keep DDA and Codex responsibilities separate:

- DDA owns daily alignment, source clarification, and handoff preparation.
- Codex owns repo analysis, PRD planning, markdown drafting, consistency checks, and verification.
- Human approval is required before treating Codex output as final or durable.

## Inputs

- `runs/2026-05-04/workspace-agents-source-clarification.md`
- `runs/2026-05-04/workspace-agents-alignment-delta.md`
- `runs/2026-05-04/status-snapshot.md`
- `agents/diarized-daily-assistant/prd.md`
- `agents/diarized-daily-assistant/app-flow.md`
- `agents/diarized-daily-assistant/instructions.md`
- `docs/source-of-truth.md`
- `templates/dda-to-codex-handoff.md`
- `templates/codex-to-dda-completion.md`
- Notion source: `Transforming DABs Into Workspace Agents` at https://www.notion.so/34f2570090e580d5b605d0c02b74aa40
- Notion comparison source: `DDA PRD Update Requirements` at https://www.notion.so/b694cc01338c411e9e1048257a9016de
- Notion comparison source: `DDA Pilot Build Brief` at https://www.notion.so/fabe0307d45449168208261339ea8b02

## Expected Output

Codex should return one of these outputs, depending on scope safety after repo review:

1. A repo-ready PRD v0.3 draft patch for `agents/diarized-daily-assistant/prd.md`, plus a concise changelog note.
2. Or, if a direct PRD patch would be too broad, a structured PRD v0.3 implementation plan with section-by-section changes, open questions, and recommended next handoff.

In either case, Codex should also return a `Codex to DDA Completion Packet` using `templates/codex-to-dda-completion.md`.

## Acceptance Criteria

- The output preserves the core rule: DDA owns daily alignment; Codex owns build/research execution; automations own recurrence; durable artifacts own truth.
- The output does not assume direct Notion, Slack, Gmail, Calendar, GitHub, Codex, or automation integrations beyond what is confirmed in source artifacts.
- The output explicitly separates v0.1 manual pilot behavior from v2/v0.3 product direction.
- The output incorporates or plans the Notion PRD requirement areas:
  - system architecture;
  - responsibility boundaries;
  - DDA-to-Codex bridge;
  - app connection strategy;
  - memory governance;
  - automation strategy;
  - reporting boundaries;
  - agent improvement loop;
  - source-of-truth model;
  - manual pilot plan;
  - feature IDs;
  - user stories;
  - risks;
  - success metrics;
  - preserved open questions.
- The repo direction question remains explicit: `dda-agent-ops` pilot repo vs. shared `systems-shaper-agents` repo is not resolved unless the operator has provided a decision.
- Any proposed source-file change preserves changelog context and does not overwrite approved material without a clear version/update note.
- The completion packet lists files changed or files proposed for change, decisions made, open questions, and DDA integration notes.

## Constraints

- Do not update Notion.
- Do not post to Slack.
- Do not send email.
- Do not save persistent memory.
- Do not create or enable automations.
- Do not create commits, branches, pull requests, or pushes without explicit human approval.
- Do not treat chat history as durable truth.
- Do not mark speculative assumptions as facts.
- Do not collapse DDA and Codex responsibilities.
- Do not broaden into app-flow, instructions, skills, evals, or template rewrites unless needed for cross-link references or called out as follow-up work.

## Open Questions For Codex To Preserve

1. Is `dda-agent-ops` the durable long-term repo or only the pilot repo?
2. Has `systems-shaper-agents` been approved or created?
3. Should PRD v0.3 be a direct update to the current repo PRD, a separate draft file, or a planned future patch?
4. Which Notion PRD requirements should be included now versus deferred to app-flow, instructions, memory, automation, or reporting docs?
5. What evidence is required before any recurring automation language moves from candidate status to enabled behavior?

## Return Requirement

Codex must return a Codex to DDA Completion Packet with:

- summary;
- files changed or proposed;
- decisions made;
- open questions;
- recommended next steps;
- DDA integration notes.
