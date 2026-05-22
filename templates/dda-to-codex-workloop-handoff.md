---
title: DDA to Codex Workloop Handoff Packet
asset_type: template
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: templates/dda-to-codex-workloop-handoff.md
created: 2026-05-22
updated: 2026-05-22
approval_status: not_approved
runtime_claim: none
canon_claim: none
external_write_claim: none
---

# DDA to Codex Workloop Handoff Packet

## Purpose

Use this template when DDA routes build, research, repo work, artifact drafting, prompt refactoring, skill generation, automation planning, or verification to Codex.

This template makes David's Codex workloop explicit:

```text
intent -> context -> mode -> slot -> cadence -> artifact -> verifier -> memory -> gate -> learning update
```

This is a practical handoff structure, not approval to bypass repo or external-action boundaries.

## Review Boundary

This handoff does not approve Slack posts, email sends, Notion updates, Linear updates, GitHub writes, memory saves, automation creation, commits, pushes, pull requests, source-of-truth changes, runtime readiness claims, loop 003, Track 2, or final acceptance unless those approvals are explicitly listed in `Gate`.

## Workloop

| Slot | Fill this in before Codex starts |
|---|---|
| `intent` | [What are we trying to decide, produce, verify, or clarify?] |
| `context` | [Durable sources, current surfaces, prior artifacts, known conflicts, and source hierarchy.] |
| `mode` | [draft / review / repo-edit / verification / research / planning / external-write-draft / no-write test] |
| `slot` | [DDA phase or lane: morning brief, state map, eval, proof gate, Codex handoff, completion, carryover, etc.] |
| `cadence` | [one-time / daily / weekly / recurring candidate / no recurrence / manual before automation] |
| `artifact` | [Exact expected output path, packet, template, eval, or report.] |
| `verifier` | [How Codex and the human reviewer will check success.] |
| `memory` | [Memory implication or candidate only; state `none` if not applicable.] |
| `gate` | [Required approvals, blocked actions, stop conditions, and no-touch surfaces.] |
| `learning update` | [What DDA should carry into reports, future templates, eval rows, or next packets.] |

## Task

[Clear task statement.]

## Source Basis

| Source | Required / optional | How Codex should use it |
|---|---|---|
| [Source 1] | [Required] | [Use as primary truth / context / comparison / template.] |
| [Source 2] | [Optional] | [Use only if needed.] |

## Inputs

- [Input 1]
- [Input 2]
- [Input 3]

## Expected Output

[Markdown file, repo update, PRD patch, research brief, consistency report, template draft, eval packet, or completion packet.]

## Acceptance Criteria

- [Criterion 1]
- [Criterion 2]
- [Criterion 3]
- Codex names all unverified, blocked, skipped, partial, or external-write items.
- Codex returns a completion packet or mirrors `templates/codex-to-dda-completion.md`.

## Constraints

- Do not assume direct app integrations unless confirmed.
- Do not treat chat history as durable truth.
- Do not collapse DDA and Codex responsibilities.
- Do not create automations.
- Do not post to Slack, send email, update Notion, update Linear, save memory, commit, push, create PRs, or change source-of-truth rules unless explicitly approved in `Gate`.
- Do not overwrite approved source files without preserving changelog context.
- Do not mark speculative assumptions as facts.
- Keep changes surgical and limited to the allowed files or paths.

## Allowed Files Or Paths

- [Path 1]
- [Path 2]

## Prohibited Files Or Paths

- [Path 1]
- [Path 2]

## Verification Plan

Codex should verify:

1. Source coverage: [required sources checked].
2. Intent fit: [output answers the intended question].
3. Boundary fit: [blocked actions remain blocked].
4. Mechanical checks: [for example `git diff --check`, template consistency, link/path check].
5. Completion quality: [completion packet includes files, decisions, open questions, next steps, and DDA integration notes].

## Return Requirement

Codex must return a Codex to DDA Completion Packet with:

- Summary
- Files created or updated
- Decisions made
- Open questions
- Recommended next steps
- DDA integration notes
- Verification performed
- Blocked or unverified items

## Completion Packet Stub

### Summary

[What Codex completed.]

### Files Created or Updated

| File | Path | Notes |
|---|---|---|
| [File] | [Path] | [Notes] |

### Decisions Made

- [Decision]

### Open Questions

- [Question]

### Recommended Next Steps

1. [Next step]

### DDA Integration Notes

[What DDA should add to reports, carryovers, Notion logs, Slack-safe summaries, memory candidates, or PRD updates.]

### Verification Performed

- [Check]

### Blocked Or Unverified Items

- [Blocked or unverified item]
