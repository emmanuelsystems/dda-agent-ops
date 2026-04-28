---
title: Conversion Pipeline
asset_type: workflow
status: draft
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: docs/conversion-pipeline.md
created: 2026-04-28
updated: 2026-04-28
---

# Conversion Pipeline

## Purpose

This document defines the repeatable process for converting a DAB, skill, prompt, prompt snippet, workflow, or prompt-adjacent asset into a structured workspace agent or reusable agent component.

The Diarized Daily Assistant DAB is the first pilot of this pipeline.

The pipeline exists because Systems Shaper's existing prompt assets currently live mostly in Notion, conversation history, working docs, and scattered context surfaces. Those surfaces are useful for thinking and planning, but they are not ideal for versioning, testing, refactoring, or agent execution.

## Goal

```txt
Messy context -> Notion working notes -> structured markdown -> repo-backed agent asset -> manually tested workflow -> stable reusable pattern
```

## Core Alignment

Notion captures and organizes intent. GitHub stores durable agent source. Codex refactors and verifies. DDA pilots the daily operating loop. Stable patterns become reusable workspace-agent components.

## Why This Matters

This pipeline prevents three common failure modes:

- Notion-only drift: prompts stay useful but hard to version, diff, test, or reuse.
- Prompt monolith: one giant instruction block tries to do everything.
- Premature automation: workflow gets automated before behavior is proven.

## Pipeline Overview

```txt
Inventory
-> Classify
-> Extract
-> Convert to Markdown
-> Store in GitHub
-> Refactor into Agent-Ready Structure
-> Create PRD / App Flow / Skill Packets
-> Configure Apps, Files, Memory, and Approvals
-> Test Manually
-> Capture Learnings
-> Promote Stable Patterns
```

## Pipeline Rule

No asset becomes agent-ready just because it exists in Notion.

An asset becomes agent-ready only after it has been:

1. Classified
2. Extracted
3. Converted into markdown
4. Stored in the repo
5. Refactored into the right file structure
6. Tested manually
7. Reviewed for source-of-truth, privacy, and approval boundaries

## Pipeline Surface Map

| Surface | Role in Pipeline | Owns |
|---|---|---|
| Notion | Human-facing inventory, triage, synthesis, prompt compilation | Working context, planning, review surfaces |
| GitHub | Durable markdown backend | Agent source, prompt source, PRDs, app flows, skills, templates, evals |
| Codex | Build/research/refactor worker | Repo conversion, markdown cleanup, consistency checks |
| ChatGPT Agent Builder | Runtime/agent configuration target | Agent personality, instructions, connected apps, files, permissions |
| Slack | Team coordination and signal capture | Approved updates, handoff notifications |
| Linear | Optional task/issue tracking surface | Implementation tasks and workflow tickets |
| Memory | Approved durable preferences and patterns | Confirmed user/workflow memory only |

## Step 1: Inventory

Objective:

Locate and inspect the source asset in the Prompts hub, related Notion pages, working docs, or conversation-derived notes.

Capture:

- Title
- URL
- Source database row
- Related pages
- Existing prompt body
- Current status/stage
- Segment/module
- Action/intent
- Related prompts
- External links
- Templates/snippets used

Inventory output:

`inventory-record.md`

or a Notion inventory row with a GitHub migration status field.

Decision gate:

`Is this asset worth preserving, merging, refactoring, archiving, or deleting?`

## Step 2: Classify

Objective:

Classify the source asset so it goes through the right conversion path.

Asset types and likely destinations:

- Full DAB / Agent -> `agents/[agent-name]/`
- Skill -> `skills/`
- Prompt Template -> `templates/`
- Prompt Snippet -> `snippets/`
- Workflow -> `workflows/`
- Evaluation Prompt -> `evals/`
- Resource -> `references/`
- Legacy Stub -> archive or merge
- Duplicate -> merge or archive
- Version Variant -> preserve with version note
- Deprecated Asset -> deprecated status or archive

Classification output:

```md
## Asset Classification

**Primary type:** [Full DAB / Skill / Template / etc.]
**Secondary type:** [Optional]
**Recommended action:** Preserve / Merge / Refactor / Archive / Delete
**Reason:** [Short rationale]
**Repo destination:** [Path]
```

## Step 3: Extract

Objective:

Pull the useful source content out of Notion without preserving clutter.

Extract:

- Role/persona
- Task/goals
- User flow
- Inputs
- Outputs
- Examples
- Constraints
- Voice/tone rules
- Tools/apps needed
- Memory assumptions
- Automation possibilities
- Open questions

Extraction principle:

Extract meaning and structure, not raw mess.

## Step 4: Convert to Markdown

Objective:

Convert the extracted asset into structured markdown files.

Possible files:

- `README.md`
- `source.md`
- `prd.md`
- `app-flow.md`
- `agent-config.md`
- `instructions.md`
- `skills.md`
- `memory.md`
- `automation-plan.md`
- `examples.md`
- `evals.md`
- `changelog.md`

## Step 5: Store in GitHub

Objective:

Move approved markdown source into the backend repo.

Recommended pilot path:

`dda-agent-ops/agents/diarized-daily-assistant/`

Source-of-truth rule:

- Planning/status -> Notion
- Prompt/agent source files -> GitHub
- Active tasks -> Notion unless mirrored to GitHub Issues
- Version history -> GitHub
- Discussion/context -> newest reviewed artifact
- Runtime instructions -> GitHub after approved commit

## Step 6: Refactor Into Agent-Ready Structure

Objective:

Turn raw source into a workspace-agent-ready design.

Required agent components:

- Agent identity
- Instructions
- Apps/connectors
- Memory
- Files/knowledge
- Skills
- Approvals
- Reporting surfaces
- Automation candidates
- Evals

## Step 7: Create PRD / App Flow / Skill Packets

Objective:

Split the asset into product, flow, and modular execution documents.

PRD should define:

- Mission
- Users
- Use cases
- Non-goals
- Feature IDs
- User stories
- Risks
- Success metrics
- Open questions

App Flow should define:

- Phases
- Inputs
- Steps
- Outputs
- Decision points
- Failure modes
- Handoff points

Skill packets should define:

- Trigger condition
- Input
- Output
- Instructions
- Examples
- Evaluation criteria

## Step 8: Configure Apps, Files, Memory, and Approvals

Objective:

Define access and boundaries.

Approval rule:

The agent may draft.

The human approves.

Durable artifacts preserve the truth.

This step must not assume direct Notion, Slack, Gmail, Calendar, GitHub, Codex, Linear, or runtime app integrations unless those integrations are explicitly confirmed for the relevant environment.

## Step 9: Test Manually

Objective:

Run the workflow manually before adding automation.

Manual test output:

- `runs/YYYY-MM-DD/manual-test-notes.md`
- or `docs/manual-pilot-results.md`

Capture:

- What worked
- What failed
- Missing context
- Bad assumptions
- Privacy issues
- Output quality
- Skill improvements
- Prompt improvements

## Step 10: Capture Learnings

Objective:

Convert the manual test into improvement artifacts.

Route learnings into:

- PRD update
- App Flow update
- `instructions.md`
- Skill packet
- Template
- Eval
- Memory candidate
- Source-of-truth note
- Open question
- Example

## Step 11: Promote Stable Patterns

Objective:

Only promote a pattern after it proves itself manually.

Promotion requirements:

- Stable trigger
- Stable input
- Stable output
- Approval rules
- Successful manual runs
- Clear owner
- Fallback behavior

Promotion classes:

- Manual only
- Reminder only
- Draft-only automation
- Approval-gated automation
- Do-not-automate

## DDA Pilot Conversion Path

```txt
Raw DDA DAB
-> DDA source.md
-> DDA PRD
-> DDA App Flow
-> DDA Agent Config
-> DDA Instructions
-> DDA Memory Model
-> DDA Automation Plan
-> DDA Templates
-> Manual Daily Pilot
-> Improvement Notes
-> v0.2 Agent Update
```

## Conversion Quality Checklist

- [ ] Source asset inventoried
- [ ] Asset type classified
- [ ] Useful content extracted
- [ ] Markdown files created
- [ ] Frontmatter added where appropriate
- [ ] Repo path correct
- [ ] Source-of-truth rules clear
- [ ] PRD exists if asset is agent-level
- [ ] App Flow exists if asset has workflow
- [ ] Instructions exist if asset will be used at runtime
- [ ] Skills separated from monolithic prompt behavior
- [ ] Memory rules defined
- [ ] Approval rules defined
- [ ] Automation deferred until manual proof
- [ ] At least one manual test captured
- [ ] Learnings routed into improvements
- [ ] Changelog updated

## Notion Alignment Notes

This pipeline can stay in Notion as a planning/operating note, but this file is the repo-backed markdown version for `dda-agent-ops`.

## Immediate Next Actions

1. Keep this file aligned with `docs/backend-strategy.md`.
2. Add pipeline references to `README.md` in a later repo consistency pass.
3. Run a consistency pass across:
   - `docs/backend-strategy.md`
   - `docs/conversion-pipeline.md`
   - `docs/source-of-truth.md`
   - `agents/diarized-daily-assistant/prd.md`
   - `agents/diarized-daily-assistant/app-flow.md`
4. Fill DDA PRD and app flow only after the strategy docs are reviewed.

## Related Docs

- `docs/backend-strategy.md`
- `docs/source-of-truth.md`
- `docs/open-questions.md`
