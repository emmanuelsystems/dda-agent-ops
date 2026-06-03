---
title: DDA Trace Format And Form Factor Decision Matrix
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
related_method_lane: ATDL
created: 2026-06-01
approval_status: not_approved
runtime_claim: none
canon_claim: none
external_write_claim: none
memory_claim: none
automation_claim: none
implementation_claim: none
source_run: runs/2026-06-01/david-may-29-context-review-and-synthesis.md
---

# DDA Trace Format And Form Factor Decision Matrix

## Review Boundary

This is a draft/review-only decision-support artifact.

It converts the June 1 May 29 context synthesis into:

1. a proposed DDA trace format, and
2. a form-factor decision matrix.

It does not approve:

- DDA source-file changes
- `skills/dda-codex-intent-router/` edits
- template or eval edits
- Operating Base doctrine promotion
- Notion, Slack, Linear, Gmail, GitHub, or memory writes
- automations
- realtime voice prototyping
- Codex runtime changes
- treating any candidate form factor as selected

## Source Basis

| Source | How It Was Used |
|---|---|
| `runs/2026-06-01/david-may-29-context-review-and-synthesis.md` | Primary synthesis source for the trace-first recommendation. |
| `runs/2026-06-01/clicky-realtime-dda-form-factor-run.md` | Source for the voice/realtime and Clicky interpretation. |
| `runs/2026-05-21/atdl-dda-alignment-share-overview-for-david.md` | Source for the earlier open form-factor question. |
| `runs/2026-05-25/dda-v2-intent-router-fit-test-and-operating-model.md` | Source for the DDA router packet sequence and work-shape taxonomy. |
| `skills/dda-codex-intent-router/SKILL.md` | Source for current local router modes, gates, and packet discipline. |
| `runs/2026-05-29/bounded-edit-protocol-planning-report.md` | Source for candidate-only bounded learning and Packet 4 posture. |

## Core Thesis

The form-factor question is downstream of trace discipline.

DDA should not choose voice, Codex workflow, workspace agent, NotionAI, repo-local skill, or hybrid Operating Base as the primary form factor until the system can preserve this chain:

```text
source signal
-> interpreted intent
-> route
-> surface
-> artifact
-> verifier
-> gate
-> learning candidate
```

The immediate proof target is therefore:

```text
Can DDA make the full work movement visible and reviewable before execution, after execution, and before memory/canon?
```

## Proposed Trace Format v0.1

### Purpose

The trace format is the smallest shared record that lets a human or future agent reconstruct:

- what triggered the work
- what the human intent was interpreted to mean
- why a surface was selected
- what artifact was produced
- what verified the artifact
- what gate remains
- what learning, if any, is only candidate

### Required Fields

```markdown
# DDA Trace Record

## Trace ID

## Date / Time Window

## Source Signal

## Source Authority Class

## Interpreted Intent

## Work Shape

## Route Decision

## Selected Surface

## Routing Rationale

## Inputs Used

## Artifact Produced Or Requested

## Verifier

## Human Gate

## Stop Conditions

## Learning Candidate

## Candidate Vs Approved Status

## Next Loop
```

### Field Definitions

| Field | Meaning | Required Discipline |
|---|---|---|
| Trace ID | Stable local identifier for the trace record. | Use date + short slug, not a vague title. |
| Date / Time Window | When the source signal or work happened. | Use exact dates when possible. |
| Source Signal | The originating message, artifact, transcript, issue, note, article, or repo event. | Link or path it; if not accessible, mark as supplied context. |
| Source Authority Class | Working signal, repo source, reviewed artifact, candidate research, approved doctrine, etc. | Never let usefulness imply authority. |
| Interpreted Intent | What DDA thinks the human is actually asking. | State as interpretation, not fact, unless explicitly confirmed. |
| Work Shape | Research synthesis, repo implementation, workflow design, external draft, memory decision, automation candidate, etc. | Match the router taxonomy. |
| Route Decision | DDA-only, Codex, `/goal`, NotionAI, Deep Research, browser, human-only, draft external message, etc. | Pick the smallest safe surface. |
| Selected Surface | Where the work should happen. | Distinguish planning surface from execution surface. |
| Routing Rationale | Why this surface is appropriate. | Include one risk and one reason. |
| Inputs Used | Sources actually used. | Do not cite inaccessible sources as read. |
| Artifact Produced Or Requested | The packet, run artifact, draft, proof pack, or decision note. | Must be reviewable. |
| Verifier | Check command, rubric, source comparison, held-out validation, or review criteria. | Passing a command is not enough if it does not prove intent. |
| Human Gate | Approval needed before send, save, edit, automate, promote, or claim final. | Keep exact gate visible. |
| Stop Conditions | Conditions that require pause or reroute. | Include ambiguity, missing verifier, approval risk, and source conflict. |
| Learning Candidate | What may survive as future memory, doctrine, skill, template, eval, or no-op. | Candidate-only unless approved. |
| Candidate Vs Approved Status | Current authority label. | Use `candidate`, `reviewed`, `approved`, `rejected`, or `no-op`. |
| Next Loop | The next bounded action. | Avoid broad "continue improving" language. |

## Trace ID Convention

Recommended local convention:

```text
YYYY-MM-DD__surface-or-source__intent-slug__vN
```

Examples:

```text
2026-06-01__slack-david-may-29__codex-knowledge-work-review__v1
2026-06-01__transcript-clicky__dda-form-factor-routing__v1
2026-06-01__repo-run__trace-format-decision-matrix__v1
```

## Authority Classes

| Class | Meaning | Examples |
|---|---|---|
| Working signal | Useful context, not durable truth. | Slack message, transcript, chat note. |
| Candidate research | Synthesized source material, not doctrine. | Deep Research output, article review, attached research note. |
| Review-only artifact | Repo-local draft for evaluation. | Files under `runs/YYYY-MM-DD/`. |
| Repo source | Current durable prompt/doc source in the repo. | `AGENTS.md`, `agents/`, `docs/`, `templates/`, committed skills. |
| Accepted direction | Human-approved planning direction. | Explicit decision note or reviewed artifact. |
| Approved doctrine | Promoted operating rule. | Approved Notion page or committed doctrine source. |
| Implementation authorization | Explicit permission to change runtime, repo source, automation, or external systems. | Human instruction naming the action and scope. |

## Route Decision Rules

| Condition | Route | Artifact |
|---|---|---|
| Messy source stack or strategic interpretation | DDA Research Preflight | Preflight packet or review run. |
| Clear bounded repo/doc task | Codex | Intent-bounded run packet or direct scoped edit if approved. |
| Persistent multi-turn objective | `/goal` | Goal run artifact and completion packet. |
| Current state / planning / review queue | NotionAI or DDA planning | State checkpoint or decision note. |
| Durable research synthesis | Deep Research / DDA synthesis | Research brief or review packet. |
| External team update | Draft only | Slack/Linear/Notion/email draft; approval before write. |
| Repeated workflow | Manual pilot first | Evidence log; no automation yet. |
| Learning from failures | Packet 4 candidate | Bounded edit candidate packet. |
| Missing authority or verifier | Human-only | Decision note; pause execution. |

## Example Trace Record: May 29 Context Review

```markdown
# DDA Trace Record

## Trace ID

2026-06-01__slack-david-may-29__context-review-synthesis__v1

## Date / Time Window

Source signal: 2026-05-29 05:11:50 CST.
Run artifact: 2026-06-01.

## Source Signal

David shared an Every Codex article and Operating Base / SkillOpt / harness files in Slack `#meetings`.

## Source Authority Class

Working signal plus candidate research.

## Interpreted Intent

Review the new context stack and interpret what it means for DDA, Codex, Operating Base, and the form-factor question.

## Work Shape

Research synthesis + workflow design.

## Route Decision

Use Codex under `/goal` to create a review-only repo artifact.

## Selected Surface

Codex, writing to `runs/2026-06-01/`.

## Routing Rationale

The work requires reading sources, synthesizing them, and producing a durable review artifact; it does not require source-file edits or external writes.

## Inputs Used

Slack thread, Every article, Slack attachments, SkillOpt paper, harness paper, prior June 1 run.

## Artifact Produced Or Requested

`runs/2026-06-01/david-may-29-context-review-and-synthesis.md`

## Verifier

`git diff --check` and review that the artifact includes source review, synthesis, implications, gates, and next steps.

## Human Gate

Human review required before source edits, Slack/Notion/memory writes, automation, runtime, or canon promotion.

## Stop Conditions

Stop if the work drifts into implementation, source links cannot be accessed but are treated as read, or article synthesis becomes doctrine.

## Learning Candidate

DDA form-factor selection should follow trace discipline.

## Candidate Vs Approved Status

Candidate only.

## Next Loop

Draft a trace-format and form-factor decision matrix.
```

## Form-Factor Decision Criteria

Use these criteria before selecting or prototyping any form factor.

| Criterion | Question | Pass Signal |
|---|---|---|
| Intent preservation | Does the form preserve the human's intended meaning before execution? | It can restate intent, assumptions, and likely misread before acting. |
| Context capture | Does it reduce manual context-transfer burden without grabbing unsafe context? | Inputs are explicit, bounded, and authority-labeled. |
| Routing quality | Does it choose the smallest safe surface? | It separates DDA, Codex, NotionAI, Deep Research, external drafts, and human-only decisions. |
| Trace visibility | Can a reviewer reconstruct why the route happened? | A trace record exists with source, route, artifact, verifier, and gate. |
| Artifact quality | Does the form produce durable reviewable output? | Output lands in the right surface with status and scope labels. |
| Verifier quality | Does it prove the intended behavior, not just completion? | Verifier is tied to intent, source, and risk. |
| Gate preservation | Does it preserve approval boundaries? | It blocks external writes, memory, automation, runtime, PRs, and canon until approved. |
| Learning control | Can repeated use improve safely? | Learning routes through candidate memory or Packet 4, not silent edits. |
| Cost and privacy | Are capture, storage, provider routing, and recurring cost bounded? | Privacy and cost preflight exists before deployment. |
| Operational fit | Does it match DDA's current pilot maturity? | It does not require unproven integrations or automation. |

## Form-Factor Matrix

| Form Factor | Primary Job | Best Fit | Main Risk | Trace Requirement | Current Recommendation |
|---|---|---|---|---|---|
| Workspace agent | User-facing daily alignment and guided routing. | Morning/midday/evening planning, lightweight context intake, review queues. | Can imply DDA owns execution or runtime. | Must output trace records and route execution out to Codex or human-only gates. | Keep as candidate; do not select yet. |
| Codex goal/workflow | Bounded repo and knowledge-work execution. | Source review, markdown artifacts, repo-local docs, verification, completion packets. | Codex can look like the alignment owner if DDA boundaries are weak. | Must start from DDA route packet and return completion reconciliation. | Active near-term execution surface after DDA routing. |
| Repo-local skill | Repeatable DDA routing procedure. | Research preflight, run packet, completion reconciliation, memory decision. | Premature canon or runtime-readiness claim. | Must have stable trigger, packet, verifier, and stop conditions. | Keep review-only; do not edit now. |
| NotionAI command center | Planning state and coherence checkpoint. | Active task state, review queues, decision registers, current context. | Planning state can be mistaken for doctrine. | Must label source authority and distinguish state from repo source. | Strong candidate state surface; no external update without approval. |
| Deep Research branch | Durable research synthesis. | Large source stacks, external literature, method papers, team-alignment briefs. | Polished research can be mistaken for canon. | Must mark candidate research, source limitations, and next decision gate. | Use when research depth is needed; not the live router. |
| Voice/realtime layer | Low-friction capture and spoken digestion. | Repeated workflows where typing/pasting context is the bottleneck. | Cost, privacy, and speed can amplify incoherent routing. | Must preserve transcript/source snippets, route rationale, and artifact output. | Defer until trace loop proves stable. |
| Screen-aware assistant | Capture context from current work surface. | Dense work where visible context matters and manual paste is costly. | Sensitive screen capture, unclear consent, unsafe source blending. | Must record what was seen, what was ignored, and source authority. | Future candidate; requires privacy/source policy first. |
| Hybrid Operating Base | Coordinated surfaces governed by trace and gates. | Long-term model where DDA routes, Codex executes, NotionAI tracks state, artifacts preserve truth, and voice captures. | Complexity and role collapse. | Must use trace records as the common spine across surfaces. | Likely long-term direction if manual proof holds. |

## Scoring Matrix

Scale:

```text
1 = weak / not ready
2 = possible but risky
3 = usable with constraints
4 = strong fit now
5 = strong fit after later proof
```

| Form Factor | Coherence Fit | Trace Fit | Current Readiness | Privacy / Cost Risk | Boundary Risk | Overall Read |
|---|---:|---:|---:|---:|---:|---|
| Workspace agent | 3 | 2 | 2 | 3 | 3 | Candidate; useful but under-specified. |
| Codex goal/workflow | 4 | 4 | 4 | 4 | 3 | Best near-term execution surface after DDA route. |
| Repo-local skill | 4 | 4 | 3 | 4 | 3 | Good repeatability candidate; keep review-only. |
| NotionAI command center | 4 | 3 | 3 | 3 | 3 | Strong state surface; needs authority labels. |
| Deep Research branch | 3 | 3 | 3 | 4 | 2 | Good for research; not live operating loop. |
| Voice/realtime layer | 3 | 2 | 1 | 1 | 2 | Defer; only after trace and privacy proof. |
| Screen-aware assistant | 3 | 2 | 1 | 1 | 2 | Defer; needs explicit capture policy. |
| Hybrid Operating Base | 5 | 5 | 2 | 2 | 2 | Likely direction; not ready as runtime. |

Interpretation:

```text
Codex goal/workflow is the strongest near-term execution surface.
The hybrid Operating Base is the strongest long-term architecture candidate.
The missing bridge is a trace spine that lets those surfaces cooperate safely.
```

## Recommended Decision

Do not choose a final DDA form factor yet.

Choose this next operating posture:

```text
DDA is the trace-first coherence router.
Codex is the primary bounded execution surface after DDA routing.
NotionAI is the likely state and review surface.
Repo run artifacts are the current durable review surface.
Skill/voice/screen-aware layers remain candidates until the trace loop is proven.
```

## Prototype Readiness Gates

### Codex Goal / Workflow Gate

Ready to use now when:

- DDA can state interpreted intent.
- Work shape is clear.
- Artifact path is known.
- Verifier is defined.
- Stop conditions are named.
- Human gate is explicit.

Not ready when:

- source stack is still messy
- route is unclear
- artifact cannot be reviewed
- the task implies external write, memory, automation, PR, or canon promotion without approval

### Repo-Local Skill Gate

Ready to promote only when:

- trigger is stable across repeated runs
- inputs and outputs are stable
- verifier is stable
- held-out validation exists
- skill body and metadata can be reviewed separately
- human approval authorizes the edit

### Voice / Realtime Gate

Ready to explore only when:

- a repeated DDA workflow proves typing or paste-based context transfer is the bottleneck
- trace output is already stable in text mode
- screen/audio capture boundaries are explicit
- provider routing and retention are understood
- cost model is bounded
- fallback to text artifact mode exists

### Hybrid Operating Base Gate

Ready to formalize only when:

- at least three real traces show the same loop works across different source types
- DDA routes without role collapse
- Codex returns completion artifacts cleanly
- NotionAI state and repo artifacts stay distinct
- learning candidates remain candidate-only until reviewed

## Trace Verifier

A trace passes when a reviewer can answer:

1. What source signal started this?
2. What was the interpreted intent?
3. Why was this route chosen?
4. What surface owned the next work?
5. What artifact proves progress?
6. What verifier checked the artifact?
7. What gate remains before external write, memory, automation, runtime, or canon?
8. What learning is candidate-only?
9. What is the next bounded loop?

If any answer is missing, the trace is incomplete.

## Suggested Manual Validation Runs

Use this trace format on three prior or upcoming cases before promoting anything:

| Case | Why It Tests The Format | Expected Output |
|---|---|---|
| David May 29 article/docs packet | Source-heavy research and form-factor synthesis. | Review trace + synthesis artifact. |
| Clicky/realtime transcript | Interface signal with implementation temptation. | Trace showing why realtime is deferred. |
| Next bounded Codex docs task | Clear execution after DDA routing. | Trace + Codex run artifact + completion reconciliation. |

Pass condition:

```text
The trace identifies source, intent, route, artifact, verifier, gate, and learning candidate without turning planning into implementation.
```

## Recommended Next Step

Create the first explicit trace record for the already completed May 29 synthesis:

```text
runs/2026-06-01/trace-record-may-29-context-review.md
```

Then create a second trace for the Clicky/realtime transcript:

```text
runs/2026-06-01/trace-record-clicky-realtime-form-factor.md
```

Do not update skills, templates, source docs, Notion, Slack, memory, or automations until those traces are reviewed.

## Completion Packet

### Summary

Created a review-only trace format and form-factor decision matrix for DDA.

The main decision is to treat trace discipline as the bridge before any form-factor selection. Codex goal/workflow is the strongest near-term execution surface after DDA routing; hybrid Operating Base is the likely long-term architecture candidate; voice and screen-aware assistants remain deferred until trace, privacy, cost, and routing proof exist.

### Files Created Or Updated

| File | Path | Notes |
|---|---|---|
| DDA Trace Format And Form Factor Decision Matrix | `runs/2026-06-01/dda-trace-format-and-form-factor-decision-matrix.md` | New review-only decision-support artifact. |

### Decisions Made

- Do not choose a final DDA form factor yet.
- Use trace records as the common spine across DDA, Codex, NotionAI, repo artifacts, future voice, and future screen-aware capture.
- Treat Codex goal/workflow as the best near-term execution surface after DDA routing.
- Defer realtime and screen-aware exploration until the trace loop is stable.
- Keep repo-local skill changes gated by held-out validation and human approval.

### Open Questions

- Should the trace format become a reusable template later?
- Should the first trace records be separate files or appended to this decision artifact?
- Which surface should eventually own trace records: `runs/`, NotionAI, Operating Knowledge, or a future trace registry?
- What exact manual validation cases should count as enough proof for trace v0.1?

### Recommended Next Steps

1. Review this matrix.
2. Draft `runs/2026-06-01/trace-record-may-29-context-review.md`.
3. Draft `runs/2026-06-01/trace-record-clicky-realtime-form-factor.md`.
4. After both traces are reviewed, decide whether to create a reusable `templates/dda-trace-record.md`.

### DDA Integration Notes

DDA should use the trace fields as a checklist before routing work into Codex, NotionAI, Deep Research, future voice, or any external write surface.

This artifact is candidate-only. It does not authorize source edits, template creation, memory persistence, external posting, automations, runtime behavior, or canon promotion.
