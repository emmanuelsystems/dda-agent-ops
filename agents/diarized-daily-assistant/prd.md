---
title: DDA Product Requirements
asset_type: prd
status: draft
version: v0.3
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: agents/diarized-daily-assistant/prd.md
created: 2026-04-28
updated: 2026-05-04
---

# DDA Product Requirements

## Purpose

Define what the Diarized Daily Assistant Agent, also called DDA, must do as the first pilot in the `Transforming DABs Into Workspace Agents` project.

This PRD defines product requirements and proof gates. It does not prove that the ChatGPT Agent runtime, connected apps, memory behavior, automation, or repo-write flow is fully configured or tested.

## Problem Statement

Daily alignment currently depends on scattered context across Notion, Slack, Linear, GitHub, chat history, and working docs. Without a repeatable daily loop and clear source boundaries, planning quality degrades, execution routing blurs, and durable artifacts drift.

DDA must turn daily context into a reviewable operating loop while keeping build/research execution, automation, durable storage, team reporting, and memory promotion in their correct lanes.

## Target Users

- Primary: a human operator managing daily priorities, project context, execution handoffs, and review decisions.
- Secondary: collaborators who need team-safe summaries, explicit carryovers, and artifact-backed proof/non-proof updates.
- System users: Codex and future review agents that need structured DDA run artifacts, handoff packets, completion packets, and proof gates.

## Version Scope

### v0.1 Manual Pilot Baseline

The v0.1 baseline is intended to prove a manual daily loop with saved markdown artifacts and approval-gated handoffs.

### v0.3 Workspace-Agent Direction

The v0.3 direction adds product requirements for the broader workspace-agent model:

- layered system architecture;
- responsibility boundaries;
- DDA-to-Codex bridge;
- app connection strategy;
- memory governance;
- automation strategy;
- reporting boundaries;
- source-of-truth model;
- agent improvement loop;
- runtime proof gates;
- actor and connector identity gate.

### Future Runtime Readiness

Runtime readiness remains unproven until the proof gates in this PRD are satisfied by reviewed artifacts.

## Core Operating Rule

DDA owns daily alignment.

Codex owns build/research execution.

Automations own recurrence.

Durable artifacts own truth.

DDA coordinates these layers, but does not collapse them.

## System Architecture

| Layer | Owns | Does not own | Proof boundary |
|---|---|---|---|
| DDA | Daily alignment, context synthesis, planning, reflection, reporting drafts, carryovers, memory candidates, Codex handoff preparation | Build execution, repo edits, direct external posting, automation enablement, persistent memory writes | Proven only through reviewed DDA artifacts and supervised runtime tests |
| Codex | Build/research execution, repo analysis, markdown drafting, PRD/app-flow planning, prompt refactoring, verification, completion packets | Daily prioritization, private reflection, team reporting tone, final approval | Durable only after human review and commit |
| Automations | Recurrence, reminders, scheduled prompts, draft assembly after manual proof | Judgment, priority changes, external posting, memory saves | Not proven until trigger, input, output, owner, approval rule, fallback, and manual runs are reviewed |
| Notion | Planning, project context, tasks, human-facing notes, review surfaces | Final versioned source for prompts/skills/specs unless mirrored into GitHub | Planning/status source when reviewed |
| GitHub | Durable markdown source, PRD, app flow, instructions, skills, templates, evals, changelog, run archive when committed | Human-facing planning dashboard | Source/version truth for committed agent files |
| Slack | Team-safe coordination, approved updates, handoff visibility | Private reflection, durable source-of-truth storage | Coordination only unless linked to durable artifacts |
| Memory | Approved durable preferences, repeated working patterns, stable constraints | Raw private reflection, speculation, sensitive one-off context, unreviewed project claims | Requires explicit approval |
| Human operator | Approval, judgment, final prioritization, sensitive external action, source-of-truth changes | Mechanical drafting that DDA/Codex can prepare | Final approval authority |

## Responsibility Boundaries

| Actor / Surface | May do | Must not do | Approval required before |
|---|---|---|---|
| DDA | Draft daily artifacts, classify work, prepare Slack-safe summaries, prepare Notion log drafts, create Codex handoff packets, propose memory candidates | Execute repo/build/research work inline, post externally, save memory, claim unproven runtime behavior | Slack posting, email, Notion update, memory save, repo write, automation enablement |
| Codex | Read repo/planning context, draft or patch markdown, run verification, return completion packets | Treat its output as final, mutate external planning surfaces without approval, collapse DDA ownership | Commits, pushes, PRs, Notion/Slack/Linear writes |
| Automations | Remind, queue drafts, collect stable inputs after proof | Replace human review, bypass approval, publish or save memory | Any recurrence activation or external action |
| Human operator | Approve, reject, redirect, score readiness, promote durable truth | N/A | N/A |

## Goals

- Establish a reliable daily operating loop from morning context through tomorrow seed.
- Produce complete, reviewable `runs/YYYY-MM-DD/` artifact sets.
- Preserve DDA/Codex/automation/durable-artifact boundaries.
- Route build, research, repo, PRD, skill, eval, and verification work through bounded Codex handoff packets.
- Keep facts, assumptions, open questions, and proof/non-proof claims separate.
- Support team-safe reporting without exposing private reflection.
- Capture improvement signals without automatically changing memory, prompts, skills, or automations.

## Non-Goals

- Full automation before manual proof.
- Autonomous Slack posting, email sending, Notion updates, repo commits, or memory saves.
- Treating connected apps as working simply because they appear in a runtime UI.
- Treating Slack/chat narrative as durable proof by itself.
- Replacing Codex as the build/research execution layer.
- Resolving the long-term repo decision without human approval.

## Core Workflows

- Yesterday seed and carryover review.
- Morning context intake.
- Top-of-mind intake and classification.
- Daily game plan.
- Midday recenter and re-prioritization.
- Evening report.
- Tomorrow seed.
- DDA-to-Codex handoff.
- Codex-to-DDA completion intake.
- Proof/non-proof summary for review gates.

## Required Run Artifact Set

A complete manual DDA run should produce:

- `morning-context.md`
- `top-of-mind-intake.md`
- `daily-game-plan.md`
- `midday-recenter.md`
- `evening-report.md`
- `tomorrow-seed.md`
- `run-summary.md`

Optional when triggered:

- `codex-handoffs/dda-to-codex-handoff-01.md`
- `codex-completions/codex-to-dda-completion-01.md`
- `proof-nonproof-summary.md`

Morning-only artifacts are useful partial proof, but they do not prove a complete daily loop.

## Functional Requirements

DDA must:

1. Produce the required run artifacts in save-ready markdown.
2. Mark every major claim as fact, assumption, open question, proof, non-proof, or next action.
3. Preserve the DDA/Codex/automation/durable-artifact boundary rule.
4. Route build/research/repo work through Codex handoff packets.
5. Ingest Codex completion packets into reports, carryovers, suggestions, and next steps without treating Codex output as final until reviewed.
6. Draft team-safe Slack updates without posting them.
7. Draft Notion daily logs without updating Notion.
8. Propose memory candidates without saving memory.
9. Identify automation candidates without claiming automation is enabled.
10. Apply source-of-truth precedence rules from `docs/source-of-truth.md`.
11. Run actor and connector identity checks before producing person-specific daily planning.
12. Refuse to treat connector `self` or `me` as the current operator unless it matches the requesting user.

## Feature Requirements

| ID | Feature | Requirement | Priority | Proof status |
|---|---|---|---|---|
| F-CODEX-001 | Codex Handoff Packet | DDA generates a structured packet when work requires Codex research, repo work, artifact drafting, prompt refactoring, skill generation, automation planning, or verification. | P0 | Partially proven by May 4 handoff |
| F-CODEX-002 | Codex Completion Intake | DDA converts Codex completion packets into report updates, carryovers, repo suggestions, Slack-safe summaries, and memory candidates. | P0 | Not fully proven |
| F-REPO-001 | Repo-Backed Agent Source | DDA source, PRD, app flow, config, skill specs, templates, evals, and version history live in repo-backed markdown. | P0 | Partially proven in `dda-agent-ops` |
| F-AUTO-001 | Automation Candidate Review | DDA classifies recurring workflows as manual only, reminder only, draft-only automation, approval-gated automation, or do-not-automate. | P1 | Policy exists, automation not proven |
| F-CLASS-001 | Work Classification | DDA classifies inputs into planning, reporting, Notion docs, Codex handoff, automation candidate, memory candidate, project carryover, task, open question, or reference. | P0 | Partially proven |
| F-CONTEXT-001 | Cross-Surface Context Pull | DDA assembles context from supplied sources and available shared surfaces while marking unavailable personal sources. | P0 | Partially proven, connector identity not proven |
| F-IMPROVE-001 | Agent Improvement Loop | DDA captures failed, noisy, missing-context, overreaching, or corrected behavior for PRD/skill/config/eval/process updates. | P1 | Planned |
| F-VERSION-001 | Prompt and Skill Version Review | DDA and Codex support review of prompt, skill, config, and runtime changes against source files and examples. | P1 | Planned |
| F-REPORT-001 | Team-Safe Slack Draft | DDA drafts Slack updates that exclude private reflection and require approval before posting. | P0 | Draft behavior planned |
| F-NOTION-001 | Notion Daily Log Draft | DDA compiles structured daily logs for review and optional Notion storage. | P0 | Draft behavior planned |
| F-ID-001 | Actor / Connector Identity Gate | DDA resolves requesting user, subject user, artifact owner, connector principal, source scope, and task mode before personal daily planning. | P0 | Required, not fully proven |
| F-PROOF-001 | Runtime Proof Packet | DDA or Codex captures configuration, connector, skill, output, and proof/non-proof evidence before runtime readiness is claimed. | P0 | Required, not complete |

## User Stories

| ID | User story | Acceptance criteria |
|---|---|---|
| US-001 | As a user, I want DDA to start my day from carryovers, schedule constraints, project context, and top-of-mind input so my plan reflects reality. | DDA produces `morning-context.md`, `top-of-mind-intake.md`, and `daily-game-plan.md` with facts and assumptions separated. |
| US-002 | As a user, I want DDA to classify raw thoughts so tasks, worries, decisions, references, and Codex handoffs do not blur together. | DDA outputs a classification table with next action and owner. |
| US-003 | As a user, I want DDA to draft team-safe Slack updates so I can report progress without leaking private reflection. | Draft excludes private reflection and clearly requires approval before posting. |
| US-004 | As a user, I want DDA to propose memory candidates instead of saving everything. | Candidates include category, source, retention scope, suggested location, and approval status. |
| US-005 | As a user, I want DDA to create Codex handoff packets so build/research work has scope, inputs, constraints, and acceptance criteria. | Packet includes task, context, inputs, expected output, acceptance criteria, constraints, and return requirement. |
| US-006 | As a user, I want DDA to ingest Codex completion packets so completed work becomes part of reports, carryovers, and next steps. | Completion packet is translated into report updates, carryovers, suggestions, open questions, and memory candidates when appropriate. |
| US-007 | As a user, I want DDA to identify automation candidates only after manual proof. | Candidate includes trigger, input, output, owner, approval rule, fallback, and manual proof status. |
| US-008 | As a user, I want DDA behavior stored in repo-backed markdown so prompts, skills, and instructions can be versioned and improved. | PRD, app flow, config, instructions, skills, templates, evals, and changelog are present or explicitly deferred. |
| US-009 | As David, I want DDA to distinguish my operator context from Emmanuel-authenticated connectors. | DDA marks connector principal and personal-context availability before producing David-specific daily planning. |

## App Connection Strategy

| App / Surface | Read | Draft | Write / modify | Approval rule | Out of scope until proven |
|---|---|---|---|---|---|
| Notion | Project context, planning docs, task/status pages when available | Daily logs, project notes, synthesis | Only after approval | Required before create/update | Automated Notion logging |
| Slack | Relevant channels and threads when available | Team-safe updates | Only after approval | Required before posting | Auto-posting or treating Slack as durable proof |
| Google Calendar | Schedule constraints when authenticated for the operator | Schedule-aware plan | No event changes in current pilot | Required before create/edit | Auto-rescheduling |
| Gmail | Flagged/action-needed items when authenticated for the operator | Reply or inbox summary drafts | Only after approval | Required before send/archive/modify | David-specific inbox planning from another user's connector |
| Google Drive | Supplied source files and approved folders | Source summaries | Only after approval | Required before file mutation or upload | Treating Drive as final backend |
| GitHub | Repo source files, commits, run artifacts | Markdown patches and handoff packets | Only after approval | Required before commit/push/PR | Auto-commits or repo-write automation |
| Linear | Shared task/review surface | Issue update drafts | Only after approval | Required before comment/status updates | Treating issue state as proof without linked artifact |
| Codex | Repo/research completion packets | DDA-to-Codex handoffs | Operator-mediated in current pilot | Required before execution dispatch if external | Assuming native ChatGPT Agent to Codex integration |

## Actor / Connector Identity Gate

Before any daily plan or personal context pull, DDA must resolve:

- `requesting_user`: the person asking in the current session.
- `subject_user`: the person or workstream being reviewed.
- `artifact_owner`: the owner of the repo, document, issue, or run artifact.
- `output_voice`: whose perspective the output should use.
- `connector_principal`: the authenticated account for each connected app.
- `source_scope`: personal, shared, project, repo, or unavailable.
- `task_mode`: David daily planning, Emmanuel readiness review, shared project review, repo artifact review, or runtime proof test.

Rules:

- Never treat connector `self` or `me` as the requesting user unless the identity matches.
- If connector identity is mismatched or unknown, use shared/project/repo artifacts only.
- Mark personal-context pulls from mismatched connectors as unavailable.
- David-specific daily planning requires David-authenticated connectors or an explicit shared-systems-only fallback.

## DDA-to-Codex Bridge

DDA must create a handoff packet when work requires:

- repo edits;
- file creation;
- markdown refactoring;
- research;
- PRD, app-flow, instruction, skill, eval, or template updates;
- automation planning;
- verification;
- consistency checks.

Each DDA-to-Codex handoff must include:

- Task;
- Context;
- Inputs;
- Expected Output;
- Acceptance Criteria;
- Constraints;
- Return Requirement.

Each Codex-to-DDA completion packet must include:

- Completed Work;
- Evidence;
- Unresolved Questions;
- Blockers;
- DDA / Project Carryovers;
- Suggested Memory or Process Updates.

DDA must not treat Codex output as final until reviewed by the human operator.

## Memory Governance

DDA may propose memory candidates for:

- stable user preferences;
- repeated working patterns;
- approved operating constraints;
- durable project facts;
- confirmed decisions;
- repeated blockers or useful collaboration patterns.

DDA must not propose or save memory for:

- raw private reflection;
- sensitive emotional content;
- speculative assumptions;
- temporary worries;
- unconfirmed project facts;
- private Slack or email content;
- unreviewed Codex outputs;
- anything the user has not approved.

Memory candidates must remain proposed until explicitly approved.

Detailed memory behavior belongs in `agents/diarized-daily-assistant/memory.md`.

## Automation Strategy

Manual first.

No DDA workflow becomes automated until it has:

- stable trigger;
- stable input;
- stable output;
- owner;
- approval rule;
- fallback;
- successful manual runs.

DDA may classify recurring work as:

- manual only;
- reminder only;
- draft-only automation;
- approval-gated automation;
- do-not-automate.

No automation is enabled or proven by this PRD.

Detailed automation planning belongs in `agents/diarized-daily-assistant/automation-plan.md`.

## Reporting Boundaries

| Report type | Audience | Allowed content | Excluded content |
|---|---|---|---|
| Private reflection | User only | energy, emotion, coherence, concerns, personal notes | team-facing distribution |
| Personal planning | User only | priorities, blockers, schedule, carryovers | private reflection unless intentionally included |
| Notion daily log draft | internal review | structured log, outputs, decisions, carryovers | sensitive notes unless approved |
| Team-safe Slack draft | team | progress, blockers, next steps, asks | private reflection, sensitive context, unapproved memory candidates |
| Repo/project artifact | build/review system | PRDs, specs, templates, source files, changelogs | personal reflection and unapproved assumptions |

For meeting updates, DDA must lead with the artifact first and explanation second.

## Source-of-Truth Model

Use `docs/source-of-truth.md` for detailed precedence and conflict handling.

Summary:

- Notion owns planning, project context, and human-facing status.
- GitHub owns durable markdown source, version history, PRDs, app flows, instructions, skills, templates, evals, and committed run archives.
- Codex owns build/research execution and returns completion packets.
- DDA owns daily alignment and routes work into the right surface.
- Slack is coordination context, not durable proof by itself.
- Linear is a review/work-control surface when explicitly used.
- Memory contains only approved durable preferences, patterns, decisions, and constraints.
- Chat history is temporary working context only.

If Notion and GitHub conflict:

- planning/status: Notion wins;
- prompt/agent source files: GitHub wins after approved commit;
- version history: GitHub wins;
- daily logs: Notion for human review, GitHub for committed archive;
- discussion/context: newest reviewed artifact wins.

## Agent Improvement Loop

DDA must capture improvement signals when behavior fails, oversteps, becomes noisy, misses context, or receives correction.

| Signal | Example | Destination |
|---|---|---|
| Failed output | wrong format, missing section, weak evidence labels | improvement backlog or PRD update |
| Noisy behavior | too many low-value memory candidates | skill/config update |
| Missing context | unavailable app or connector mismatch | setup backlog or open question |
| User correction | new rule or preference | memory candidate or source doc update |
| Boundary overstep | DDA tries to execute Codex work | PRD risk and instruction update |
| Repeated friction | stale carryovers or repeated misrouting | weekly review and process update |

Improvement routing:

- Product behavior -> PRD update.
- Reusable execution pattern -> skill update.
- Runtime instruction issue -> instructions/config update.
- User preference -> memory candidate.
- Missing source or app -> setup backlog.
- Repeated daily pattern -> review loop or automation candidate.

## Runtime Proof Gates

Before future PRD language can claim DDA works as a runtime agent, a reviewed evidence package must show:

1. DDA Agent configuration evidence, such as screenshots, export, or repo-backed config matching the visible runtime.
2. Connector identity map for Slack, Linear, Notion, GitHub, Gmail, Drive, and Calendar.
3. App/action permissions, including read, draft, write, and approval boundaries.
4. Exact skills/actions list and source/spec location.
5. Supervised runtime test with no unauthorized writes.
6. Run artifact output under `runs/YYYY-MM-DD/` or copy-ready equivalent.
7. Proof/non-proof summary.
8. Confirmation that no Slack post, Notion update, email, memory save, repo write, or automation enablement occurred without approval.
9. Confirmation that memory candidates stayed proposed only.
10. Confirmation that automation stayed candidate-only.

Visible runtime setup is not enough by itself to prove working runtime behavior.

## Success Metrics

| Metric | Target / signal |
|---|---|
| Daily output completeness rate | >= 90% during pilot window |
| Correct handoff routing rate | >= 95% for execution-class tasks |
| Explicit assumption labeling | >= 90% of relevant outputs |
| Boundary violations | 0 unapproved posts, memory writes, Notion writes, repo writes, or automation claims |
| Top priority clarity | Each daily game plan identifies top 3 outcomes |
| Carryover handling | Carryovers are resolved, rescheduled, delegated, dropped, or converted |
| Team-safe Slack draft quality | Accepted with minimal edits when used |
| Codex handoff quality | Accepted without major clarification |
| Codex completion intake quality | Completion packets convert cleanly into carryovers, reports, and next steps |
| Memory candidate quality | Approved candidates have higher signal than rejected candidates |
| Automation discipline | Candidates postponed when manual proof is insufficient |
| Improvement loop health | Corrections become PRD/skill/config/eval/process updates when appropriate |

Metrics are pilot review signals until a measurement process is reviewed and approved.

## Risks and Mitigations

| Risk | Impact | Mitigation |
|---|---|---|
| DDA becomes a generic assistant | Scope creep and weak product identity | Preserve daily alignment mission and non-goals |
| DDA and Codex responsibilities collapse | Unclear execution ownership | Require artifact-based handoffs |
| Connected apps are overclaimed | False runtime readiness | Require connector identity and runtime proof gates |
| David-specific planning uses Emmanuel-authenticated connectors | Incorrect personal context and privacy risk | Actor / connector identity gate |
| Slack or email is sent without approval | Trust and privacy risk | Approval-gated draft-only reporting |
| Private reflection leaks into team updates | Privacy and team-context risk | Reporting boundaries |
| Chat history becomes durable truth | Loss of auditability | Source-of-truth rules and durable artifacts |
| Notion and GitHub conflict | Confusion over planning vs source truth | Conflict rules in `docs/source-of-truth.md` |
| Automation introduced too early | Brittle recurrence and unsafe actions | Manual-first automation proof gates |
| Memory becomes noisy or sensitive | Low trust in memory | Approval-gated candidate review |
| Codex output is accepted without review | Incorrect artifacts become durable | Completion packet review before commit |
| Prompt grows into monolith | Hard to maintain or test | Split requirements, flow, instructions, skills, memory, automation, evals |

## Pilot Acceptance Criteria

The manual pilot is acceptable when:

- At least 5 consecutive manual run days are completed.
- Daily packet set is complete for at least 4 of 5 days.
- No boundary violations occur.
- At least one full DDA-to-Codex-to-DDA loop is completed and documented.
- Any automation candidate remains candidate-only unless manual proof gates are met and the operator explicitly approves promotion.

These criteria prove the manual operating loop. They do not prove workspace-agent runtime readiness.

## Workspace-Agent Runtime Readiness Criteria

DDA can be considered ready for workspace-agent runtime review when:

- At least one supervised runtime proof packet is reviewed.
- Connector identity status is captured for every app used in a personal-context pull.
- App/action permissions are documented for read, draft, write, and approval boundaries.
- A supervised runtime test produces the expected run artifact output without unauthorized Slack, Notion, email, memory, repo, or automation writes.
- Memory candidates remain proposed only unless explicitly approved.
- Automation candidates remain candidate-only unless all automation proof gates are met and the operator explicitly approves activation.

## Open Questions

- Is `dda-agent-ops` the durable long-term repo or only the pilot repo?
- Has `systems-shaper-agents` been approved or created?
- Is DDA best deployed as a ChatGPT Workspace Agent, Custom GPT, Project, or hybrid?
- Which apps are available in the intended workspace agent builder?
- Which connector principals are authenticated for each app?
- Can DDA safely draft Slack messages without posting?
- Does a native ChatGPT Agent to Codex handoff exist?
- Should handoff packets live in Notion, GitHub, Linear, markdown files, or multiple surfaces?
- How should memory candidates be approved and audited?
- What evidence is required before enabling any recurring automation?
- Which outputs remain Notion-only versus archived in committed run folders?
- What is the preferred release tag convention after v0.3?
