---
title: DDA David Showcase Packet
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

# DDA David Showcase Packet

## Review Boundary

This is a draft/review-only showcase packet for Emmanuel to use with David.

It does not approve loop 003, Track 2, automation, Slack sends, Notion writes, Linear writes, GitHub writes, memory saves, PRD drafting, reusable skill implementation, commits, pushes, canonical promotion, or DDA runtime readiness.

The current proof posture remains:

- DDA remains Pilot 001.
- DDA remains `Yellow / not runtime-ready`.
- Loop 003 remains blocked.
- Track 2 remains blocked.
- The current agent remains Emmanuel-owned team-test infrastructure, not proven David-authenticated morning-driver infrastructure.
- Current proof gaps still include memory after-state / diff-test handling, owner/admin acceptance, and exact Linear / Notion principal proof if David requires it.
- Schedule has `PASS` evidence from the latest no-active-schedule screenshot, with prior schedule drift preserved.
- Slack write posture has `CONDITIONAL PASS` evidence from visible disabled toggles, not runtime Slack safety proof.

## 1. Showcase Thesis

Use this as the core David-facing sentence:

```text
DDA is a supervised orientation, proof-routing, and packet-prep layer. It rebuilds current state from durable inputs, separates proof from assumptions, identifies what is blocked, recommends the next smallest action, and prepares a reviewable packet or Codex handoff.
```

Short version:

```text
DDA turns scattered daily context into a decision-ready packet without pretending it is the executor.
```

## 2. What Emmanuel Should Demonstrate

Emmanuel should demonstrate DDA as a control layer before execution, not as autonomous runtime.

The showcase should make three points clear:

1. DDA orients: it rebuilds the current state from durable sources and names the active lane.
2. DDA routes proof: it separates proven evidence, non-proof, hard stops, warnings, and open decisions.
3. DDA prepares packets: when repo/build/research work is needed, it shapes a bounded DDA-to-Codex handoff and waits for completion evidence.

This is the safe articulation:

```text
DDA does not replace Codex. DDA decides what needs to be clarified, packaged, or handed off. Codex performs bounded repo-local execution after a handoff and returns a completion packet.
```

## 3. Before / After Flow

| Moment | Before DDA | With DDA |
|---|---|---|
| Source context | Notion, Linear, Slack, repo artifacts, screenshots, and Codex outputs are spread across surfaces. | DDA names the source basis and rebuilds the current state. |
| Proof posture | Strategy, proof, candidate work, and runtime blockers can blend. | DDA separates proven evidence, non-proof, hard stops, warnings, and review decisions. |
| Next action | The lane can expand into broad strategy, skills, automation, or PRD work. | DDA recommends one next smallest packet or handoff. |
| Execution | The system can be misread as ready to act. | DDA routes execution to Codex or a human approval step. |
| Approval | Unknowns can sound like confidence. | DDA keeps `UNKNOWN = BLOCK` unless David explicitly accepts a limitation. |

## 4. Demo Narrative

### Opening

```text
David, I want to show DDA as it works today: a supervised orientation and proof-routing layer, not an autonomy claim.

The value is that it takes scattered context and turns it into a smaller decision. It tells us what is proven, what is not proven, what is blocked, and what should happen next.
```

### Show The Current SSI-113 Posture

```text
For SSI-113, DDA is still Yellow / not runtime-ready. Loop 003 and Track 2 stay blocked. The proof packet improved in some areas, but memory handling and owner/admin acceptance are still decision points.
```

Use this spoken readout:

```text
Schedule has latest screenshot PASS, but prior drift stays visible.
Slack write posture is conditional PASS from visible disabled toggles, but not runtime safety proof.
Memory after-state / diff-test handling remains incomplete.
Owner/admin acceptance remains open.
The current agent is Emmanuel-owned team-test infrastructure, not proven David-authenticated morning-driver infrastructure.
```

### Show The DDA Loop

```text
Input context
-> current truth rebuild
-> evidence vs assumption split
-> hard stop / warning / review classification
-> one next action
-> reviewable packet or Codex handoff
-> human approval before any external movement
```

### Explain The DDA / Codex Split

| Layer | Owns | Does not own |
|---|---|---|
| DDA | Orientation, current-state rebuild, evidence classification, blocker routing, next-action recommendation, packet prep, Codex handoff prep | Repo execution, automation, runtime proof, final approval, external writes |
| Codex | Bounded repo-local drafting, research, implementation, verification, completion packets | DDA readiness decisions, external approval, autonomous daily operation |
| Human reviewer | Approval, readiness movement, external writes, route decisions, source-of-truth changes | Reconstructing every context thread manually when DDA can orient first |

## 5. Live-Safe Demo Script

Run this as a no-tool, no-write supervised preview. Do not connect live tools. Do not authorize external writes.

### Step 1: State The Demo Boundary

```text
This demo is only a supervised preview. We are not running loop 003, Track 2, automation, Slack sends, Notion updates, Linear updates, GitHub writes, or memory saves.
```

### Step 2: Paste The Demo Prompt

```text
Using only the context I provide below, act as DDA in supervised preview mode.

Context:
- DDA remains Pilot 001.
- DDA remains Yellow / not runtime-ready.
- Loop 003 is blocked.
- Track 2 is blocked.
- Current proof gaps include memory after-state / diff-test handling, owner/admin acceptance, and exact Linear / Notion principal proof if required.
- Schedule has latest screenshot PASS but prior drift.
- Slack write posture is conditional PASS from visible toggles, not runtime safety proof.
- The current agent is Emmanuel-owned team-test infrastructure, not proven David-authenticated morning-driver infrastructure.

Task:
Return a supervised DDA orientation packet with:
1. Current state
2. Proven evidence
3. Not proven
4. Hard stops
5. Warnings
6. One recommended next action
7. Codex handoff trigger
8. Prohibited actions

Rules:
- Do not claim runtime readiness.
- Do not propose automation.
- Do not ask to run loop 003.
- Do not treat Slack, Notion, Linear, GitHub, Gmail, Drive, or memory writes as approved.
- Keep DDA separate from Codex execution.
```

### Step 3: Narrate What To Look For

```text
The thing to evaluate is not whether DDA can execute. The thing to evaluate is whether DDA preserves the boundary, classifies the proof state correctly, and reduces the next decision to one reviewable action.
```

## 6. Expected DDA Output Shape

```markdown
# Supervised DDA Orientation Packet

## Current State
- DDA remains Pilot 001.
- DDA remains Yellow / not runtime-ready.
- Loop 003 remains blocked.
- Track 2 remains blocked.
- Current agent posture is Emmanuel-owned team-test infrastructure.

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
- Owner/admin acceptance for the next test route.

## Hard Stops
- Memory after-state / diff-test handling.
- Owner/admin acceptance until David decides the infrastructure route.
- Loop 003 execution.
- Track 2 execution.
- Green readiness claim.

## Warnings
- Slack posture is conditional, not runtime proof.
- Schedule evidence has prior drift.
- Connector screenshots are configuration evidence, not action tests.
- Long visible prompts may become attachments in some UI paths.

## One Recommended Next Action
Produce or review a DDA Hard Stops vs Warnings Register before considering any loop 003 movement.

## Codex Handoff Trigger
If a repo artifact, proof register, research brief, or verification pass is needed, DDA should prepare a bounded DDA-to-Codex handoff packet and require Codex to return a completion packet.

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

## 7. Packet-Prep And Handoff Demonstration

Use the existing handoff templates to show how DDA routes work:

1. DDA identifies that the next movement requires repo-local drafting or verification.
2. DDA writes a bounded handoff using `templates/dda-to-codex-handoff.md`.
3. Codex executes only the bounded task.
4. Codex returns a completion packet using `templates/codex-to-dda-completion.md`.
5. DDA uses that completion packet as input for the next orientation cycle.

Talk track:

```text
This is why DDA and Codex should not be collapsed. DDA prepares the decision and the handoff. Codex does the bounded repo work. The completion packet gives DDA a clean return signal for the next daily orientation.
```

## 8. Approval Boundaries To Say Out Loud

Say:

```text
This packet is not asking to approve runtime readiness. It is only asking whether David agrees this is the right way to describe and demonstrate DDA's current supervised value.
```

Then name the boundaries:

- No loop 003 approval.
- No Track 2 approval.
- No automation approval.
- No Slack / Notion / Linear / GitHub / Gmail / Drive write approval.
- No memory-save approval.
- No PRD or canonical-source promotion.
- No claim that the current DDA Agent is David-authenticated morning-driver infrastructure.
- No claim that screenshots prove runtime behavior.

## 9. What Not To Claim

Do not claim:

- DDA is autonomous.
- DDA is runtime-ready.
- DDA is Green.
- Loop 003 is ready.
- Track 2 is ready.
- Memory is safe.
- Slack is runtime-safe.
- Connector identities are fully proven.
- David/admin ownership is proven.
- The current DDA Agent is David's personal morning-driver instance.
- Goal-setter, `/todo`, or skill artifacts close SSI-113 proof gaps.
- Codex output is final without review.

## 10. What David Should Be Able To Review

David should be able to answer:

- Is this the right articulation of DDA's current value?
- Does the showcase preserve `Yellow / not runtime-ready`?
- Does it keep DDA separate from Codex execution?
- Does it make proof and non-proof easy to inspect?
- Does it identify hard stops without inflating confidence?
- Does it produce a concrete next packet instead of broad strategy expansion?
- Are the approval boundaries explicit enough for a live demo?

## 11. Recommended Close

Use this closing:

```text
The immediate success condition is not that DDA runs the day automatically. The immediate success condition is that DDA can reliably orient us, preserve proof boundaries, prepare a reviewable packet, and route bounded execution to Codex only when approved.
```

If David accepts this framing, the next review surface is:

```text
DDA Hard Stops vs Warnings Register
```

That register should decide what remains a hard stop, what is only a warning, what David must accept or reject, and what still stays prohibited before any loop 003 movement.
