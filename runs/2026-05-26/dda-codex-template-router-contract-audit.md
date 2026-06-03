---
title: DDA Codex Template Router Contract Audit
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
related_skill: skills/dda-codex-intent-router/
created: 2026-05-27
approval_status: not_approved
runtime_claim: none
canon_claim: none
external_write_claim: none
memory_claim: none
automation_claim: none
template_edit_claim: none
---

# DDA Codex Template Router Contract Audit

## Review Boundary

This is a review-only audit of:

- `templates/dda-to-codex-handoff.md`
- `templates/codex-to-dda-completion.md`

No templates, PRD files, `AGENTS.md`, Notion pages, Slack messages, Linear records, Gmail messages, GitHub records, automations, memory, commits, pushes, or pull requests were changed.

This artifact does not approve template changes. It only lists the smallest bounded follow-up change set if the templates should be aligned to the current intent-router contract.

## Source Basis

- Notion: `DDA Intent Router - Context`, fetched 2026-05-26, status `Drafting`.
- Notion child page: `DDA Pilot 001 Operating Contract + Router Matrix v0.2`, fetched 2026-05-26, labeled current DDA Pilot 001 operating contract and candidate operating artifact.
- Local skill: `skills/dda-codex-intent-router/SKILL.md`.
- Local templates:
  - `templates/dda-to-codex-handoff.md`
  - `templates/codex-to-dda-completion.md`

## Contract Baseline Used

The current router contract requires DDA to preserve this operating sequence:

```text
preflight before routing -> routing before execution -> reconciliation before memory -> approval before external writes or canon claims
```

For Codex handoffs and completions, the required fields are the union of the Notion contract and the repo-local skill.

### Packet 1: DDA to Codex Intent-Bounded Run Packet

Required fields:

- Human intent
- Work shape classification
- Recommended surface
- Routing rationale
- Scope boundary
- Inputs
- Required output artifact
- Verifier
- Human gate
- Stop conditions
- Return format
- No-touch zones

Cross-cutting requirements from the same contract:

- Authority class
- Candidate-only memory handling or memory path
- Clear approval boundary
- No canon, runtime, automation, external-write, or memory-promotion claims unless explicitly approved

### Packet 2: Codex to DDA Completion Reconciliation Packet

Required fields:

- Original intent
- Run outcome
- Artifact produced
- Evidence and verification
- Files or systems touched
- Decisions made
- Open risks
- Human review needed
- Memory candidates
- Recommended next loop
- Authority class

Additional local-skill requirements:

- Verifier
- Human gate
- Stop conditions
- Candidate-vs-approved labels where relevant

## Audit Verdict

The templates are directionally compatible with the older DDA-to-Codex workflow, but they do not yet match the current intent-router contract.

The handoff template covers basic task framing, inputs, expected output, acceptance criteria, constraints, and the requirement to return a completion packet. It does not yet force DDA to classify work shape, choose the smallest safe surface, state routing rationale, name a verifier, define human gates, or define stop conditions.

The completion template covers summary, files changed, decisions, open questions, next steps, and integration notes. It does not yet force Codex to restate original intent, label run outcome, attach evidence and verification, list systems touched, name open risks separately from questions, identify human review needed, or label authority and memory candidates safely.

## DDA to Codex Handoff Template Field Audit

| Router-required field | Current coverage | Current template field | Audit note |
|---|---|---|---|
| Human intent | Ambiguous | `Task`, `Context` | The template asks for a task and background, but not the underlying human intent. This can let an execution-shaped task hide unclear intent. |
| Work shape classification | Missing | None | No explicit classification such as research, repo implementation, docs, QA, automation candidate, GUI/browser, planning, or human-only. |
| Recommended surface | Missing | None | The template assumes Codex by being a handoff, but the router contract requires choosing the smallest safe surface before execution. |
| Routing rationale | Missing | None | There is no place to explain why Codex is the right surface instead of DDA-only, `/goal`, automation candidate, human-only, or another route. |
| Scope boundary | Ambiguous | `Constraints` | Constraints say what not to assume or do, but they do not require a positive in-scope / out-of-scope boundary. |
| Inputs | Covered | `Inputs` | Covered directly. |
| Required output artifact | Covered with naming drift | `Expected Output` | Functionally close, but the contract uses artifact language and proof-oriented outputs. |
| Verifier | Ambiguous | `Acceptance Criteria` | Acceptance criteria can imply a verifier, but the router contract requires an explicit verification method. |
| Human gate | Missing | None | The constraints imply some blocked actions, but do not name the review or approval gate for this run. |
| Stop conditions | Missing | None | No field tells Codex when to stop and return to DDA or the human. |
| Return format | Ambiguous | `Return Requirement` | It only says Codex must return a completion packet; it does not specify required completion fields. |
| No-touch zones | Partial | `Constraints` | Some no-touch rules are present, but not the fuller router list: repo edits if unauthorized, `AGENTS.md`, runtime skill moves, automations, canon promotion, external writes, memory write-back, production changes. |
| Authority class | Missing | None | v0.2 requires DDA outputs to be labeled by authority class. |
| Candidate memory handling / memory path | Missing | None | Parent context requires a memory path; v0.2 requires candidate-only memory handling. |

## Codex to DDA Completion Template Field Audit

| Router-required field | Current coverage | Current template field | Audit note |
|---|---|---|---|
| Original intent | Missing | None | `Summary` describes what happened, but does not preserve the intent Codex executed against. |
| Run outcome | Missing | None | No explicit status such as completed, partial, blocked, needs review, needs reroute, unsafe, or out of scope. |
| Artifact produced | Ambiguous | `Summary`, `Files Created or Updated` | Works for file-only runs, but not for PRs, branches, proof packs, drafts, screenshots, state notes, or review packets. |
| Evidence and verification | Missing | None | No required place for tests, commands, screenshots, citations, validation notes, or skipped checks. |
| Files or systems touched | Partial | `Files Created or Updated` | Covers files, but not systems, branches, tools, external surfaces, or no-touch confirmation. |
| Decisions made | Covered | `Decisions Made` | Covered directly. |
| Open risks | Ambiguous | `Open Questions` | Questions are not the same as risks, unresolved evidence gaps, scope risks, or review hazards. |
| Human review needed | Missing | None | No explicit review decision such as approve, revise, reject, merge, publish, bank, or schedule follow-up. |
| Memory candidates | Ambiguous | `DDA Integration Notes` | Mentions memory candidates, but bundles them with reports, logs, Slack-safe summaries, and PRD updates without candidate-vs-approved labels. |
| Recommended next loop | Partial | `Recommended Next Steps` | Next steps exist, but the router expects next loop language: accept, revise, reroute, new Codex packet, tracker update, skill candidate, automation candidate, close. |
| Authority class | Missing | None | v0.2 requires authority classification. |
| Verifier | Missing | None | The local skill's completion packet includes verifier as a required reconciliation field. |
| Human gate | Missing | None | The local skill's completion packet includes human gate as a required reconciliation field. |
| Stop conditions | Missing | None | The local skill's completion packet includes stop conditions as a required reconciliation field. |
| Candidate-vs-approved labels | Missing | None | Required for memory, canon, skill, automation, runtime, and external-write items. |

## Missing Or Ambiguous Contract Themes

1. The templates do not yet encode the full workloop:

```text
intent -> context -> mode -> slot -> cadence -> artifact -> verifier -> memory -> gate -> learning update
```

2. The handoff template still reads like a generic Codex task brief, not a router decision output.

3. The completion template still reads like a generic completion report, not a reconciliation-ready packet.

4. Authority classification is absent from both templates.

5. Memory handling is either absent or bundled into broad integration notes.

6. Human gates and stop conditions are not first-class fields.

7. No-touch zones are partially present in the handoff template but not current enough for the v0.2 no-touch boundary.

8. Verification is implied by acceptance criteria in the handoff template, and absent from the completion template.

## Smallest Bounded Follow-Up Change Set

If the templates should match the router contract, the smallest bounded change is to revise only the two template files and avoid touching PRD, `AGENTS.md`, skill files, evals, Notion, memory, or automations.

### Change 1: Update `templates/dda-to-codex-handoff.md`

Keep the existing file, frontmatter shape, and review posture. Replace or augment the body with the Packet 1 fields:

```markdown
# DDA to Codex Intent-Bounded Run Packet

## Human Intent

## Work Shape Classification

## Recommended Surface

## Routing Rationale

## Scope Boundary

## Inputs

## Required Output Artifact

## Verifier

## Human Gate

## Stop Conditions

## No-Touch Zones

## Authority Class

## Candidate Memory Handling

## Return Format
```

Retain the current constraints, but move them under `No-Touch Zones` and expand them only to match the v0.2 contract.

### Change 2: Update `templates/codex-to-dda-completion.md`

Keep the existing file, frontmatter shape, and completion role. Replace or augment the body with the Packet 2 fields:

```markdown
# Codex to DDA Completion Reconciliation Packet

## Original Intent

## Run Outcome

## Artifact Produced

## Evidence And Verification

## Files / Systems Touched

## Decisions Made

## Open Risks

## Human Review Needed

## Verifier

## Human Gate

## Stop Conditions

## Memory Candidates

## Authority Class

## Recommended Next Loop
```

Keep `Files Created or Updated` only if it is reframed as a subsection or table under `Files / Systems Touched`.

### Change 3: Preserve Approval Labels

In both templates, include a short instruction that memory, skill, automation, canon, runtime, external-write, PR, merge, and source-of-truth items must be labeled as candidate-only unless explicitly approved.

### Change 4: Version As Template v0.2

If approved, update each template frontmatter from `version: v0.1` to `version: v0.2` and set `updated` to the approval date. Do not claim approval in the file unless the human explicitly approves the template change.

## Recommended Next Review

Before editing templates, decide whether the source of truth for template fields should be:

1. The Notion v0.2 operating contract as the current planning contract.
2. The repo-local `skills/dda-codex-intent-router/SKILL.md` as the local execution procedure.
3. The union of both, with the stricter field retained when they differ.

The safest bounded path is option 3 because the user asked to audit against both sources, and it preserves verifier, human gate, stop condition, authority, and candidate-only boundaries.
