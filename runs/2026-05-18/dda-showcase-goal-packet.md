---
title: DDA Showcase Goal Packet
asset_type: run_artifact
status: draft_review_only
version: v0.1
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

# DDA Showcase Goal Packet

## Review Boundary

This packet is a draft `/goal` trial for articulating how to showcase DDA to David.

It does not approve loop 003, Track 2, automation, Slack sends, Notion writes, Linear writes, GitHub writes, memory saves, commits, PRs, canonical promotion, or runtime readiness.

The goal is to produce a supervised, David-facing showcase plan that demonstrates what DDA does today:

```text
rebuild current state
-> separate evidence from assumptions
-> identify blockers
-> recommend one next action
-> pre-stage one reviewable packet or handoff
-> wait for human approval
```

## Goal Readiness

Status: `ready as docs-only / review-only`

Why this is safe to try:

- It is a repo-local draft artifact only.
- It does not ask Codex to run DDA, touch external systems, or claim runtime readiness.
- It demonstrates the DDA method through a controlled showcase plan.
- It preserves the current Yellow/manual-supervised posture.

## Exact `/goal` To Try

```text
/goal Create a David-facing DDA showcase packet for the dda-agent-ops repo. Read first: runs/2026-05-18/dda-method-adjustment-review.md, templates/dda-to-codex-handoff.md, templates/codex-to-dda-completion.md, and the current SSI-113 proof posture summarized in the repo. Produce one draft Markdown artifact in runs/2026-05-18/ that explains how Emmanuel can articulate and demonstrate how the DDA Agent works as a supervised orientation, proof-routing, and packet-prep layer. Keep in scope: demo narrative, before/after flow, live-safe demo script, sample DDA prompt, expected DDA output shape, approval boundaries, and what not to claim. Do not run loop 003, Track 2, automation, Slack/Notion/Linear/GitHub writes, memory saves, PRD drafting, skill implementation, commits, pushes, or readiness promotion. Done when the artifact gives Emmanuel a concrete showcase path David can review without confusing DDA with Codex execution or autonomous runtime readiness. Return a Codex-to-DDA completion packet with summary, files changed, decisions, checks, open questions, next steps, and DDA integration notes.
```

## Why This Goal Is The Right Trial

This is a better first `/goal` trial than creating another proof register because the current question is not "what proof is blocked?" It is:

```text
How do I explain and demonstrate DDA properly?
```

The showcase should prove communication clarity, not runtime safety.

The trial lets Codex produce a reviewable artifact while keeping DDA's real boundary intact:

- DDA orients and frames.
- Codex drafts repo-local artifacts.
- David reviews.
- Humans approve any external movement.

## Showcase Thesis

Use this as the main David-facing articulation:

```text
DDA is a supervised daily orientation and proof-routing layer. It is not the executor and it is not claiming autonomy. Its job is to reconstruct current truth from durable sources, separate evidence from assumptions, identify blockers, recommend the next useful action, and pre-stage one reviewable packet or Codex handoff.
```

Short version:

```text
DDA turns scattered context into a decision-ready packet.
```

## Showcase Structure

### 1. Start With The Problem

Talk track:

```text
The problem is not lack of notes. The problem is context drift. Work is spread across Notion, Linear, Slack, repo artifacts, screenshots, and Codex outputs. DDA's role is to rebuild the current state and make the next decision easier without pretending uncertain things are proven.
```

What to show:

- A scattered source list: Notion guide, `SSI-113`, May 13/15 repo packets.
- The risk: proof, strategy, and runtime blockers can blend.
- The need: one orientation layer that preserves boundaries.

### 2. Show The DDA Loop

Use this simple loop:

```text
Input context
-> current truth rebuild
-> evidence vs assumption split
-> blocker classification
-> one next action recommendation
-> one reviewable artifact or handoff
-> human approval
```

What to say:

```text
The value is not that DDA acts automatically. The value is that it reduces ambiguity before anybody acts.
```

### 3. Show A Before / After

Before DDA:

```text
Scattered Slack, Notion, Linear, repo, screenshot, and Codex context.
Unclear whether something is proof, strategy, candidate work, or runtime readiness.
Next action can drift into broader strategy.
```

After DDA:

```text
One orientation brief.
One source basis.
One proof/non-proof split.
One blocker table.
One recommended next packet.
Explicit prohibited actions.
```

### 4. Show What DDA Does Not Do

Say this explicitly:

```text
DDA does not approve loop 003.
DDA does not approve Track 2.
DDA does not claim Green/runtime readiness.
DDA does not post, send, save memory, commit, update Notion, update Linear, or enable automation without approval.
DDA does not replace Codex for repo/build execution.
```

### 5. Show The Handoff

Use the repo templates to explain the workflow:

```text
DDA identifies that repo/build/research work is needed.
DDA creates a bounded DDA-to-Codex handoff packet.
Codex executes only the bounded repo-local task.
Codex returns a completion packet.
DDA uses the completion packet for the next orientation cycle.
```

This is the cleanest way to explain why DDA and Codex are different.

## Live-Safe Demo Script

Use a no-write, no-tool, no-runtime demo prompt.

### Demo Input Prompt

```text
Using only the context I provide below, act as DDA in supervised preview mode.

Context:
- DDA remains Pilot 001.
- DDA remains Yellow / not runtime-ready.
- Loop 003 is blocked.
- Track 2 is blocked.
- Current proof gaps include memory after-state / diff-test handling, owner/admin acceptance, and exact Linear/Notion principal proof if required.
- Schedule has latest screenshot PASS but prior drift.
- Slack write posture is conditional PASS from visible toggles, not runtime safety proof.

Task:
Return a supervised DDA orientation packet with:
1. Current state
2. Proven evidence
3. Not proven
4. Hard stops
5. Warnings
6. One recommended next action
7. Prohibited actions

Do not claim runtime readiness, do not propose automation, and do not ask to run loop 003.
```

### Expected DDA Output Shape

```markdown
# Supervised DDA Orientation Packet

## Current State
- DDA remains Pilot 001.
- DDA remains Yellow / not runtime-ready.
- Loop 003 and Track 2 remain blocked.

## Proven Evidence
- Repo-backed DDA evidence packets exist.
- DDA can preserve proof boundaries in supervised Track 1 behavior.
- Latest schedule screenshot shows no active schedule listed.
- Slack write toggles appear disabled from latest screenshot.

## Not Proven
- Runtime readiness.
- Memory after-state / diff-test behavior.
- David-authenticated infrastructure.
- Exact Linear / Notion principals if required.
- Slack runtime safety.

## Hard Stops
- Memory after-state / diff-test handling.
- Owner/admin acceptance.
- Loop 003 execution.
- Track 2 execution.
- Green readiness claim.

## Warnings
- Slack posture is conditional, not runtime proof.
- Schedule evidence has prior drift.
- Connector screenshots are configuration evidence, not action tests.

## One Recommended Next Action
Produce a DDA Hard Stops vs Warnings Register for review.

## Prohibited Actions
- No loop 003.
- No Track 2.
- No automation.
- No Slack/Notion/Linear/GitHub writes.
- No memory saves.
- No readiness promotion.
```

## What David Should Be Able To See

David should be able to evaluate:

- DDA can make current state legible.
- DDA keeps proof and non-proof separate.
- DDA preserves approval boundaries.
- DDA routes execution to Codex instead of becoming the executor.
- DDA makes the next action smaller.
- DDA does not overclaim readiness.

## What Not To Showcase Yet

Do not showcase:

- live Slack posting
- live Notion updates
- live Linear updates
- memory behavior
- loop 003 execution
- Track 2 execution
- automation
- autonomous daily operation
- DDA as a full personal assistant
- DDA as a replacement for Codex

Those are either blocked, unproven, or the wrong frame for the current maturity stage.

## Acceptance Criteria For This `/goal` Trial

This trial is successful if the output:

- explains DDA in one clear thesis
- gives Emmanuel a David-facing talk track
- demonstrates the before/after value
- includes a live-safe demo prompt
- includes expected DDA output shape
- preserves Yellow/manual-supervised boundaries
- separates DDA from Codex
- avoids runtime/autonomy claims
- returns a Codex-to-DDA completion packet

## Open Questions

- Should the showcase be performed as a live prompt, a narrated walkthrough, or both?
- Should David review the demo prompt before it is used live?
- Should the showcase use the real `SSI-113` proof state or a sanitized synthetic scenario?
- Should the output be mirrored into Linear or Slack after review?

## Recommended Next Step

Create the actual showcase artifact:

```text
runs/2026-05-18/dda-david-showcase-script.md
```

That artifact should be the one Emmanuel can use directly with David.
