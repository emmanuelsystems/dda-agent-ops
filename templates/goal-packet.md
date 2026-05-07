---
title: Goal Packet Template
asset_type: template
status: draft
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: templates/goal-packet.md
created: 2026-05-07
updated: 2026-05-07
---

# Goal Packet

## Date

[YYYY-MM-DD]

## Active Goal

[One specific outcome for the current work loop.]

## Goal Source

[operator | david | linear | slack | notion | repo | codex | mixed]

## Goal Evidence

| Source Surface | Source Ref | Claim Supported | Confidence | Gap |
|---|---|---|---|---|
| [surface] | [link/path/ref] | [claim] | [confirmed/likely/assumption/unknown] | [gap] |

## Candidate Goals Considered

1. [Candidate goal]
2. [Candidate goal]
3. [Candidate goal]

## Selected Goal Rationale

[Why this goal is the active goal now.]

## In Scope

- [What this goal includes]

## Out Of Scope

- [What this goal excludes]

## Active Surfaces

| Surface | Role | Checked This Run | Current Gap |
|---|---|---|---|
| [surface] | [source/planning/discussion/execution/trace] | [yes/no] | [gap] |

## First Recommended Action

[One concrete next action.]

## Dispatch Lane

[dda_only | codex | linear | notion | slack | github_repo | operator_decision | blocked]

## Codex CLI Goal Handoff

Use this section only when the dispatch lane is `codex` or when Codex execution is likely next.

### `/goal` Draft

```md
[One concise Codex CLI goal focused on implementation, repo work, verification, or structured execution.]
```

### Codex Boundaries

- [Boundary, such as no commit or push without approval]
- [Boundary, such as preserve Yellow readiness]
- [Boundary, such as keep outputs draft/review-only]

### Return Requirement

[What Codex should return to DDA when the session or work slice is done.]

## Artifact To Pre-Stage

[Artifact name, target surface, and review status.]

## Approval Required

- [Approval gate]

## Blocked Decisions

- [Decision, owner, and blocking reason]

## Notes For Orientation Brief

[What should carry into `orientation-brief.md`.]
