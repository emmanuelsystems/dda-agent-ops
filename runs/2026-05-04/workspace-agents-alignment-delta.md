# Workspace Agents Alignment Delta

**Date:** 2026-05-04
**Timezone:** Asia/Shanghai
**Inputs:** Notion `Transforming DABs Into Workspace Agents`, `DDA Pilot Build Brief`, `DDA PRD Update Requirements`, `Create DDA Agent Configuration Dossier`, and saved May 4 run artifacts
**Status:** Draft comparison artifact; no Notion or GitHub source files updated

## Summary

The Workspace Agents source confirms the May 4 operating lane: DDA should stay focused on becoming the first workspace-agent pilot, with Notion holding planning context and GitHub/repo markdown becoming the durable backend for source files.

The Pilot Brief and PRD requirements are broadly aligned with the Workspace Agents source. The main delta is not conceptual disagreement; it is execution state. The project page lists PRD v0.3, repo direction, configuration dossier, app flow, packet templates, and manual pilot checklist as current priorities, while the fetched comparison documents remain draft context and do not prove those updates are complete.

## Source Comparison

| Alignment point | Workspace Agents source | Pilot Brief | PRD requirements | Delta |
|---|---|---|---|---|
| First pilot | DDA is the first pilot for the repeatable DAB-to-agent conversion path. | Matches: DDA pilot should not be a one-off prompt rewrite. | Matches: DDA v2 requirements center the Diarized Daily Assistant Agent. | No mismatch. |
| Source-of-truth model | Notion is planning/operating surface; GitHub becomes durable backend. | Matches but still uses placeholder paths and destinations in places. | Matches and adds a formal source-of-truth model. | Need concrete repo/path decisions before claiming source model is complete. |
| Ownership boundaries | DDA handles daily alignment; Codex handles repo/build/research; automations own recurrence. | Matches exactly as key design rule. | Matches and expands into responsibility tables. | No mismatch; this is the strongest stable rule. |
| Current priorities | PRD v0.3, repo planning prompt, repo direction decision, config dossier, app flow, packet templates, manual checklist. | Covers most outputs as pilot deliverables. | Covers PRD update requirements and feature IDs. | Priorities should be converted into a dated work queue or handoff packet. |
| Manual-before-automation | Do not automate until trigger/input/output/approval/manual runs/fallback are stable. | Matches through manual pilot and v0.1 non-goals. | Matches through automation strategy and readiness gates. | No automation work should be treated as enabled. |
| Codex bridge | Codex supports repo setup, markdown conversion, implementation planning, prompt refactoring, verification. | Includes DDA-to-Codex and Codex-to-DDA packet outputs. | Defines packet fields and completion intake. | Packet templates are still the next execution surface if repo work is needed. |
| Repo direction | Project asks to decide `dda-agent-ops` pilot repo vs `systems-shaper-agents` shared repo. | Mentions GitHub paths as placeholders such as `/dda-pilot/v0.1/...`. | Recommends `systems-shaper-agents` or explicit deferral. | This remains an unresolved decision. |

## What Stays

1. Keep DDA as the first pilot for the broader workspace-agent conversion system.
2. Keep the DDA/Codex/Automations/Durable Artifacts ownership rule unchanged.
3. Keep Notion as the planning and task surface.
4. Keep GitHub/repo markdown as the durable backend for source artifacts after review and commit.
5. Keep manual-before-automation as a hard gate.
6. Keep artifact-based DDA-to-Codex and Codex-to-DDA handoffs.

## What Changes Or Tightens

1. The May 4 status should stop treating the Workspace Agents source as missing; the durable source is now identified as the Notion project page.
2. DDA should not jump directly into PRD or app-flow rewriting. It should first create a scoped handoff or work queue from the project priorities.
3. The repo direction question should be explicit in every follow-on packet until resolved.
4. The same-day Agent Configuration Dossier task can be treated as active project work, but not as completed or durable unless separately reviewed and saved.
5. The existing repo PRD v0.2 is narrower than the Notion PRD requirements: it covers the manual pilot but does not yet include the full v2 architecture, app strategy, memory governance, reporting boundaries, improvement loop, feature IDs, user stories, and success metrics.

## What Remains Unproven

1. Whether DDA PRD v0.3 has been drafted or accepted.
2. Whether `dda-agent-ops` is the long-term repo or only the pilot repo.
3. Whether `systems-shaper-agents` exists or has been approved as the shared repo.
4. Whether the DDA App Flow v0.1 and Agent Configuration Dossier v0.1 have been reviewed as durable artifacts.
5. Whether any automation candidate has passed manual proof gates.
6. Whether Notion pages should be updated directly from this run; approval is required before any Notion write.

## DDA-Owned Next Actions

1. Preserve the clarified source reference in the May 4 run artifacts.
2. Keep the daily lane focused on Workspace Agents alignment and artifact routing.
3. Decide whether the next packet should target PRD v0.3, app flow, agent configuration dossier, or repo direction.
4. Mark unresolved repo direction as an open decision, not an assumption.

## Codex-Owned Next Actions

1. If approved, update repo artifacts from the Notion PRD requirements without collapsing boundaries.
2. Produce a DDA-to-Codex handoff packet for the next selected execution target.
3. Run a cross-file consistency review across PRD, app flow, instructions, templates, source-of-truth, and run artifacts.
4. Keep changes draft/reviewable until human approval and commit.

## Recommended Durable Artifact Next

Create a DDA-to-Codex handoff packet for the next execution slice.

Recommended path: `runs/2026-05-04/codex-handoffs/workspace-agents-prd-v03-handoff.md`

Recommended scope: update or plan the DDA PRD v0.3 against the Notion PRD requirements and Workspace Agents project source, while preserving source-of-truth boundaries and leaving repo direction as an explicit open question unless the operator decides it.
