---
title: DDA David Showcase Script
asset_type: run_artifact
status: draft_review_only
version: v0.2
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
related_issue: SSI-113
created: 2026-05-18
updated: 2026-05-18
approval_status: not_approved
runtime_claim: none
canon_claim: none
---

# DDA David Showcase Script

## Review Boundary

This is a docs-only, draft/review-only showcase script for Emmanuel to use with David.

It does not approve loop 003, Track 2, automation, Slack sends, Notion writes, Linear writes, GitHub writes, Gmail writes, Drive writes, memory saves, commits, pushes, branches, PRs, merges, PRD changes, skill implementation, canonical promotion, or DDA runtime readiness.

Current posture to preserve throughout the showcase:

- DDA remains Pilot 001.
- DDA remains `Yellow / not runtime-ready`.
- Loop 003 remains blocked.
- Track 2 remains blocked.
- Current agent posture remains Emmanuel-owned team-test infrastructure, not proven David-authenticated morning-driver infrastructure.
- Screenshots are configuration evidence only, not runtime action proof.
- Candidate artifacts are not canon until explicitly promoted.

## Source Basis Used

| Source | How it is used |
|---|---|
| `runs/2026-05-18/dda-method-adjustment-review.md` | Primary method frame: DDA should narrow, preserve proof boundaries, use hard-stops vs warnings, and keep `UNKNOWN = BLOCK` unless David accepts a limitation. |
| `runs/2026-05-13/friday-decision-packet.md` | Current SSI-113 decision posture: keep loop 003 blocked; do not move until memory after-state / diff-test handling and owner/admin acceptance are reviewed. |
| `runs/2026-05-13/owner-view-proof-status.md` | Current proof readout: schedule latest screenshot PASS, Slack write posture conditional PASS, memory and owner/admin still incomplete, Linear / Notion exact principals partial. |
| `runs/2026-05-13/david-side-dda-track-1-review.md` | Behavioral evidence: DDA passed as supervised orientation behavior, not runtime proof; Codex must still verify execution and external truth. |
| `runs/2026-05-13/owner-view-screenshot-appendix.md` | Screenshot evidence and limits: no-active-schedule latest modal, Slack toggles off, but no runtime action proof or memory safety proof. |
| `templates/dda-to-codex-handoff.md` | Handoff frame: DDA packages bounded work for Codex when build, research, repo work, drafting, or verification is needed. |
| `templates/codex-to-dda-completion.md` | Return frame: Codex reports summary, files changed, decisions, open questions, next steps, and DDA integration notes. |

## One-Line Thesis

DDA turns scattered daily context into a supervised, proof-aware, decision-ready packet before anyone executes.

## Opening Talk Track

David, I want to show DDA as it works today, not as an autonomy claim.

DDA is a supervised orientation, proof-routing, and packet-prep layer. It does not execute repo work, approve readiness, post to Slack, update Notion or Linear, save memory, enable automation, or replace Codex.

Its job is to take scattered context across repo artifacts, Linear status, Notion context, Slack coordination, screenshots, and Codex outputs, then turn that into:

- current state
- proven evidence
- not-proven items
- hard stops
- warnings
- review decisions
- one recommended next action
- a packet or Codex handoff

The value is that DDA makes the next decision smaller, clearer, and safer.

## Before / After Flow

| Moment | Before DDA | With DDA |
|---|---|---|
| Context | Notes, screenshots, repo packets, Slack/Linear/Notion context, and Codex outputs are spread across surfaces. | DDA rebuilds the current state from durable inputs and names the active lane. |
| Proof | Strategy, proof, runtime blockers, and candidate artifacts can blend. | DDA separates proven evidence, not-proven items, hard stops, warnings, and review decisions. |
| Unknowns | Unknowns can sound like confidence. | DDA keeps `UNKNOWN = BLOCK` unless David explicitly accepts a limitation. |
| Next action | The work can expand into strategy, PRD, skills, or automation too early. | DDA recommends the next smallest reviewable packet or bounded Codex handoff. |
| Execution | DDA can be mistaken for the executor. | DDA orients and routes; Codex executes bounded repo-local work after handoff; humans approve external movement. |

## Current Proof Posture To Show

Use this short readout before the live-safe prompt:

```text
Current SSI-113 posture:
- DDA is Yellow / not runtime-ready.
- Loop 003 remains blocked.
- Track 2 remains blocked.
- Schedule has PASS evidence from the latest no-active-schedule screenshot, but prior schedule drift stays visible.
- Slack write posture is conditional PASS from visible disabled toggles, not runtime Slack safety proof.
- Memory after-state / diff-test handling remains incomplete.
- Owner/admin acceptance remains unresolved.
- Exact Linear / Notion principal proof remains partial if David requires it.
- Current infrastructure is Emmanuel-owned team-test infrastructure, not proven David-authenticated morning-driver infrastructure.
```

## Live-Safe Demo Prompt

Use this only as a no-tool, no-write supervised preview. Do not connect live tools. Do not authorize Slack, Notion, Linear, GitHub, Gmail, Drive, or memory writes.

```text
Using only the context I provide below, act as DDA in supervised preview mode.

Context:
- DDA remains Pilot 001.
- DDA remains Yellow / not runtime-ready.
- Loop 003 is blocked.
- Track 2 is blocked.
- Current infrastructure is Emmanuel-owned team-test infrastructure, not proven David-authenticated morning-driver infrastructure.
- Current proof gaps include memory after-state / diff-test handling, owner/admin acceptance, and exact Linear / Notion principal proof if required.
- Schedule has latest screenshot PASS, but prior schedule drift must stay visible.
- Slack write posture is conditional PASS from visible disabled toggles, not runtime safety proof.
- Screenshots are configuration evidence only, not runtime action proof.
- Candidate artifacts are not canon.

Task:
Return a supervised DDA orientation packet with:
1. Current state
2. Proven evidence
3. Not proven
4. Hard stops
5. Warnings
6. REVIEW items
7. One recommended next action
8. Prohibited actions

Rules:
- Do not claim Green or runtime readiness.
- Do not propose automation.
- Do not ask to run loop 003.
- Do not ask to run Track 2.
- Do not treat Slack, Notion, Linear, GitHub, Gmail, Drive, or memory writes as approved.
- Do not treat screenshots as runtime action proof.
- Do not treat candidate artifacts as canon.
- Keep DDA separate from Codex execution.
```

## Expected DDA Output Shape

```markdown
# Supervised DDA Orientation Packet

## Current State
- DDA remains Pilot 001.
- DDA remains Yellow / not runtime-ready.
- Loop 003 remains blocked.
- Track 2 remains blocked.
- Current infrastructure is Emmanuel-owned team-test infrastructure.

## Proven Evidence
- Repo-backed DDA evidence packets exist.
- DDA can preserve proof boundaries in supervised Track 1 behavior.
- Latest schedule screenshot shows no active schedule listed.
- Latest Slack screenshot shows visible write toggles off.

## Not Proven
- Runtime readiness.
- Memory after-state / diff-test behavior.
- David-authenticated morning-driver infrastructure.
- Exact Linear / Notion principals if required.
- Slack runtime safety.
- Owner/admin acceptance for the next route.

## Hard Stops
- Memory after-state / diff-test handling.
- Owner/admin acceptance until David decides the infrastructure route.
- Loop 003 execution.
- Track 2 execution.
- Green/runtime-ready claim.

## Warnings
- Slack posture is conditional, not runtime proof.
- Schedule evidence has prior drift.
- Connector screenshots are configuration evidence, not action tests.
- Long visible prompts can become attachments in some UI paths.

## REVIEW Items
- Should David accept the latest no-active-schedule screenshot as sufficient schedule proof?
- Should David accept Slack disabled-toggle evidence as enough for pre-test posture, with runtime recheck later?
- Are partial Linear / Notion principal views acceptable for supervised testing?
- Is Emmanuel-owned supervised infrastructure acceptable, or is a David-authenticated DDA instance required?
- Is memory after-state capture enough, or is a disable/gate proof required?

## One Recommended Next Action
Produce or review a DDA Hard Stops vs Warnings Register before considering any loop 003 movement.

## Prohibited Actions
- No loop 003.
- No Track 2.
- No automation.
- No Slack, Notion, Linear, GitHub, Gmail, or Drive writes.
- No memory saves.
- No commits or pushes.
- No PRD drafting.
- No skill implementation.
- No readiness promotion.
```

## DDA vs Codex Responsibility Split

| Layer | Owns | Does not own |
|---|---|---|
| DDA | Daily orientation, current-state rebuild, source-basis summary, proof/non-proof split, hard-stop and warning classification, next-action recommendation, DDA-to-Codex handoff prep | Repo execution, runtime proof, automation, external writes, final approval, Green readiness claim |
| Codex | Bounded repo-local drafting, research, implementation, consistency checks, verification, Codex-to-DDA completion packet | Approving DDA readiness, replacing DDA daily alignment, approving external writes, treating DDA outputs as canon |
| Human reviewer | Approval, readiness movement, external writes, owner/admin route decisions, source-of-truth changes, canon promotion | Manually reconstructing every source thread when DDA can provide the orientation packet |

Use this talk track:

```text
DDA prepares the decision and the handoff. Codex performs bounded repo-local execution after a handoff. Humans approve external movement and readiness changes.
```

## Approval Boundaries

Say this explicitly:

```text
This showcase is not asking to approve runtime readiness. It is only asking whether David agrees this is the right way to describe and demonstrate DDA's supervised value today.
```

Approval is still required before:

- Slack posts or messages
- Notion writes
- Linear writes
- GitHub writes, commits, branches, PRs, or merges
- Gmail or Drive writes
- memory saves
- automation
- loop 003
- Track 2
- PRD changes
- skill implementation
- readiness promotion
- candidate-to-canon promotion

## What David Should Be Able To Judge

David should be able to answer:

- Does DDA preserve `Yellow / not runtime-ready`?
- Does DDA avoid autonomy and runtime-readiness claims?
- Does DDA separate proven evidence from not-proven items?
- Does DDA classify hard stops, warnings, and REVIEW items clearly?
- Does DDA recommend one smaller next action instead of broad expansion?
- Does DDA keep screenshots in the correct evidence category?
- Does DDA keep candidate artifacts out of canon?
- Does DDA make the Codex handoff boundary clear?
- Does the demo prompt stay safe to run without tools or writes?

## What Not To Demo Yet

Do not demo:

- loop 003
- Track 2
- live Slack send
- live Notion update
- live Linear update
- live GitHub write, branch, commit, PR, or merge
- live Gmail or Drive write
- memory save behavior
- automation setup or scheduler behavior
- autonomous daily operation
- Green/runtime-ready claim
- PRD drafting
- skill implementation
- candidate artifact promotion

Do not frame DDA as:

- autonomous
- runtime-ready
- a product pitch
- a replacement for Codex
- David-authenticated morning-driver infrastructure
- proven safe because screenshots exist

## REVIEW Register

| Item | Current classification | Why it matters | David decision needed |
|---|---|---|---|
| Memory after-state / diff-test handling | HARD STOP / REVIEW | Loop 003 cannot be proof if memory mutation or capture behavior is uncontrolled. | Decide whether after-state capture is enough or disable/gate proof is required. |
| Owner/admin acceptance | REVIEW / HARD STOP until decided | Emmanuel-owned team-test infrastructure is not the same as David-authenticated morning-driver infrastructure. | Accept supervised Emmanuel-owned route or require a David-authenticated DDA instance. |
| Linear / Notion exact principals | REVIEW | Exact principals are partial in screenshot evidence. | Decide whether partial visibility is acceptable for supervised testing. |
| Slack write posture | CONDITIONAL PASS / WARNING | Visible toggles appear off, but screenshots do not prove runtime safety. | Decide whether disabled-toggle evidence is enough for pre-test posture, with runtime recheck later. |
| Schedule state | PASS / WARNING | Latest screenshot shows no active schedule, but prior drift must stay visible. | Decide whether screenshot 11 is sufficient current schedule proof. |
| Runtime readiness | HARD STOP | Evidence remains Yellow and partial. | Do not approve Green/runtime-ready claim. |
| Loop 003 | HARD STOP | Latest SSI-113 gate keeps loop 003 blocked. | Do not revisit until hard stops and review decisions are resolved. |
| Track 2 | HARD STOP | Track 2 depends on owner-view proof and runtime posture. | Keep blocked. |
| Goal-setter, `/todo`, skills, PRD expansion | STOP EXPANDING in SSI-113 | Useful candidate work does not close current proof blockers. | Park outside SSI-113 unless separately approved. |

## Closing Talk Track

The near-term success condition is not:

```text
DDA runs the day automatically.
```

The near-term success condition is:

```text
DDA can reliably orient us from scattered context, preserve proof boundaries, identify the next smallest action, and hand off bounded execution to Codex when approved.
```

If David accepts that framing, the next reviewable movement is not more strategy and not runtime execution. It is:

```text
DDA Hard Stops vs Warnings Register
```

That register should make the next decision explicit: what is a hard stop, what is only a warning, what David must accept or reject, and what remains prohibited before any loop 003 movement.
