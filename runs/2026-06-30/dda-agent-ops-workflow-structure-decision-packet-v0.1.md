---
title: DDA Agent Ops Workflow Structure Decision Packet
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
reviewer: David Abiera
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
created: 2026-06-30
approval_status: not_approved
outcome: workflow_structure_candidate
runtime_claim: none
canon_claim: none
automation_claim: none
skill_claim: none
eval_file_claim: none
memory_claim: none
external_write_claim: none
github_path: runs/2026-06-30/dda-agent-ops-workflow-structure-decision-packet-v0.1.md
---

# DDA Agent Ops Workflow Structure Decision Packet v0.1

## Review Boundary

This packet captures the first workflow-structure candidate for DDA Agent Ops.

It is review-only. It does not change the repo source-of-truth rules, promote DDA Agent Ops to final Context Vault, create an automation, create a skill, create an eval, save memory, update external systems, or claim runtime readiness.

Current status:

```text
candidate / test-ready
```

Not yet:

```text
accepted
canon
runtime-validated
automation-ready
skill-ready
eval-ready
```

## Source Context Used

| Source | Role | Status |
|---|---|---|
| Attached pasted text: `DDA Agent Ops Workflow Structure Decision Packet v0.1` | Primary source for this artifact | Converted into repo-local review packet |
| `AGENTS.md` | Repo operating and approval boundaries | Read |
| `docs/source-of-truth.md` | Existing source-of-truth model | Read |
| `runs/2026-06-25/dda-agent-ops-source-topology-handoff-experiment-v0.1.md` | Prior source-topology and handoff packet | Read |
| `runs/2026-06-25/candidate-to-canon-status-taxonomy-v0.1.md` | Prior status taxonomy and promotion guardrails | Read |
| `runs/2026-06-29/dda-agent-ops-transferability-test-packet-v0.1.md` | Latest transferability test packet | Read |

## 1. Purpose

This packet helps Emmanuel and David decide the first workable team workflow structure for DDA Agent Ops.

The goal is not to finalize the full Systems Shaper operating architecture yet. The goal is to decide the first structure that can help both David and Emmanuel recover state, route work, and evaluate progress without manually carrying the middle of the loop every day.

## 2. Current Workflow Problem

The main issue is not just GitHub mechanics.

The deeper problem is workflow authority.

Right now, the work can appear across many surfaces:

- Slack
- GitHub
- Codex
- ChatGPT
- Google Drive
- Notion
- Linear / Symphony
- run folders
- proof packets
- huddle transcripts
- local branches
- project repos

Each surface can contain useful context, but the team does not yet have a clear rule for what each source owns.

Because of that, David can get lost trying to answer:

- Which repo should I open?
- Which branch should I pull?
- Which run folder matters?
- Which artifact is current?
- Which source is authoritative?
- What should my agent recover?
- What should be pushed back?
- What still needs human review?

## 3. What David Is Struggling With

David's struggle is not that he does not understand the value of the work. The struggle is that the work is not yet packaged in a way his side can repeatedly recover.

The pain points are:

1. He does not always know which repo or branch contains the latest state.
2. He sees useful artifacts, but cannot always tell which ones are active, stale, candidate-only, or review-ready.
3. He does not want to manually remember which Codex conversation, branch, or source contained the last active state.
4. He wants to reduce his role in the middle of the loop.
5. He wants the agent to recover state, prepare the next step, and tell him what needs evaluation.
6. He wants repeatable workflows that can later become skills, automations, or canon processes, but not before they are tested.

## 4. What Emmanuel's Current Loop Already Does

Emmanuel's current loop already has the early shape of a daily runtime system.

Current observed loop:

1. Receive raw or messy context from Slack, ChatGPT, articles, docs, transcripts, or huddles.
2. Use ChatGPT or Codex to synthesize the context.
3. Convert messy input into handoff packets, notes, proof packets, or candidate workflows.
4. Store artifacts in GitHub run folders.
5. Push updates so David or David's agent can pull them later.
6. Send Slack updates to create visibility.
7. Use the next huddle or next Codex run to recover state and continue.

This is useful because it turns scattered context into durable artifacts.

But it is currently more reliable for Emmanuel than it is for the team.

## 5. What Breaks When the Loop Becomes Shared

The loop breaks when another person or another agent cannot recover the same state from the same source without Emmanuel explaining it live.

Current breakpoints:

- David may be on `master` while Emmanuel's latest work is on another branch.
- David may see a repo on GitHub but not have the branch locally available.
- Slack updates may explain that work happened, but not tell the agent exactly what to pull.
- Drive or Notion may contain source context, but Codex may not have full access.
- ChatGPT or Codex conversations may contain useful reasoning, but they are not durable shared state by default.
- GitHub may contain artifacts, but the team still needs rules for which folder, branch, and packet is current.
- Candidate artifacts may look complete but not yet be validated.
- The system can produce "progress-looking artifacts" before it proves live usefulness.

## 6. Core Workflow Principle

Humans should own the beginning and end of the loop.

AI should carry the middle.

Recommended structure:

```text
Human intent
-> agent state recovery
-> source routing
-> repo-local execution
-> handoff or artifact creation
-> human evaluation
-> candidate / hold / accepted decision
```

This means David and Emmanuel should not be manually carrying every context thread, branch, or source relationship.

They should decide:

- what the goal is
- what should be evaluated
- what counts as pass or hold
- what can be promoted later

Agents should help with:

- recovering latest state
- finding relevant source artifacts
- identifying missing or ambiguous context
- preparing handoff packets
- creating source-backed snapshots
- returning pass / hold / fail packets

## 7. Recommended Source Authority Ladder

Working source authority order:

1. **Human decision or explicit approval**

   Owns final acceptance, promotion, and review decisions.

2. **GitHub repo-local run folder**

   Owns durable daily runtime state and source-backed artifacts.

3. **Repo-local proof, handoff, or completion packet**

   Owns the current artifact-level evidence trail.

4. **Linear / Symphony**

   Owns project status, workstream tracking, issue boundaries, and review gates.

5. **Google Drive**

   Owns transcripts, shareable docs, source packets, and externally readable deliverables.

6. **Notion**

   Owns human-readable planning, discovery, and knowledge organization.

7. **Slack**

   Owns coordination signals, daily updates, and human alignment notes.

8. **ChatGPT / Codex conversations**

   Own reasoning and working synthesis, but should not be treated as canon unless converted into a durable artifact.

## 8. Tool Ownership Model

### GitHub

Owns:

- run folders
- source-backed artifacts
- proof packets
- handoff packets
- completion or hold packets
- repo-local workflow experiments
- candidate skill/workflow files
- versioned evidence

Does not own by default:

- final human approval
- full project management
- general team discussion
- all source docs
- all client-facing docs

### Codex

Owns:

- repo-local inspection
- artifact creation
- branch/repo work
- file edits
- proof packet drafting
- handoff packet drafting
- source-backed state recovery

Does not own by default:

- final approval
- Slack decisions
- Drive source truth
- Notion knowledge truth
- Linear/Symphony gate status
- canon promotion

### Slack

Owns:

- coordination
- daily updates
- quick alignment
- requests to David or Emmanuel
- links to artifacts

Does not own by default:

- durable source truth
- final artifact state
- canon status
- proof validation

### Google Drive

Owns:

- transcripts
- shareable Google Docs
- meeting source packets
- review docs
- artifacts intended for human reading outside the repo

Does not own by default:

- repo execution state
- branch status
- commit history
- source-backed run folders

### Linear / Symphony

Owns:

- project tracking
- ticket ownership
- review boundaries
- gate status
- project-level alignment

Does not own by default:

- raw runtime artifacts
- all source context
- all proof evidence

### Notion

Owns:

- planning
- knowledge capture
- discovery
- human-readable synthesis
- broader workspace context

Does not own by default:

- repo-local execution
- commit-level state
- transferability proof

### ChatGPT

Owns:

- reasoning
- synthesis
- packet drafting
- reflection
- decision support

Does not own by default:

- canon
- durable state
- repo proof
- approval

## 9. Workflow Structure Options

### Option A: One Master Repo for Everything

Description:
All projects, daily runs, workflow experiments, proof packets, and source notes live under one master repo.

Pros:

- Simple mental model.
- One place to pull from.
- Easy for agents to search if everything is inside one repo.
- Useful for early experimentation.

Cons:

- Can become cluttered.
- May blur project boundaries.
- May not scale well across separate client or internal workstreams.
- Could make DDA Agent Ops look like the final Context Vault too early.
- Branch structure can become confusing.

Best use:
Only as a temporary early-stage experiment.

Recommendation:
Do not adopt as the long-term structure.

### Option B: DDA Agent Ops as Runtime Launchpad

Description:
DDA Agent Ops stores daily runtime state, run folders, handoff packets, proof packets, and routing instructions. It references other project repos, Drive docs, Notion pages, Slack threads, and Linear/Symphony issues instead of absorbing everything.

Pros:

- Matches David's "launchpad" framing.
- Keeps DDA Agent Ops focused on state recovery.
- Avoids turning it into the final Context Vault too early.
- Supports transferability testing.
- Lets agents recover daily state and route to the correct next surface.
- Easier to define source authority.

Cons:

- Requires clear source ledgers.
- Requires every run folder to name related repos/docs/tickets.
- Requires discipline around what belongs in DDA Agent Ops versus what only gets referenced.

Best use:
Best first team workflow structure.

Recommendation:
Adopt this as the first working model.

### Option C: Separate Repo Per Project

Description:
Each major project has its own repo. DDA Agent Ops only contains workflow patterns and maybe shared agent instructions.

Pros:

- Clean project boundaries.
- Better for mature implementation projects.
- Easier to avoid repo clutter.
- Works well once routing is mature.

Cons:

- Harder for Codex if only one repo is active in a session.
- Requires stronger routing instructions.
- Can make state recovery harder if the launchpad is weak.
- May be too early before the team has stable source authority rules.

Best use:
Later stage, after transferability works.

Recommendation:
Hold for later.

### Option D: Hybrid Runtime Launchpad + Project Repos

Description:
DDA Agent Ops acts as the runtime launchpad. Project repos hold project-specific implementation. Linear/Symphony tracks project/gate state. Drive and Notion hold human-readable source and planning. Slack coordinates.

Pros:

- Most realistic long-term structure.
- Preserves source boundaries.
- Supports agents routing across tools.
- Keeps runtime state separate from project execution.
- Allows Candidate-to-Canon discipline.

Cons:

- Requires clear routing rules.
- Requires a source authority ladder.
- Requires consistent run-folder structure.
- Requires pull/push/commit discipline.

Best use:
Best medium-term structure.

Recommendation:
Use this as the target model, but start with Option B first.

## 10. Recommended First Team Workflow Model

Recommended first structure:

```text
DDA Agent Ops = shared runtime launchpad
GitHub run folders = daily state recovery layer
Codex = repo-local execution surface
Linear / Symphony = project and gate tracking
Drive = transcript and shareable docs layer
Notion = planning and knowledge layer
Slack = coordination signal layer
ChatGPT = reasoning and synthesis layer
Human review = final approval layer
```

This keeps the first decision practical.

DDA Agent Ops should not become the final Context Vault yet.

It should answer:

- What is active?
- Where is the latest state?
- What changed?
- What source should be trusted first?
- What is missing?
- What should David's agent pull?
- What should Emmanuel verify?
- What is pass, hold, or fail?

## 11. Proposed Run Folder Standard

Each daily run folder should make state recovery easy.

Recommended folder shape:

```text
runs/YYYY-MM-DD/
  00-gameplan.md
  01-source-ledger.md
  02-current-state-snapshot.md
  03-active-artifacts.md
  04-open-loops.md
  05-handoff-packet.md
  06-completion-or-hold-packet.md
```

Minimum viable version:

```text
runs/YYYY-MM-DD/
  gameplan.md
  source-ledger.md
  current-state-snapshot.md
  handoff-or-hold-packet.md
```

Every run folder should answer:

- What is the active workstream?
- What is the current truth?
- What changed since the last checkpoint?
- What source anchors were used?
- What is missing or ambiguous?
- What is the next handoff?
- What needs human evaluation?

## 12. Team Handoff Loop

Recommended team handoff loop:

```text
1. Human sets intent.
2. Agent pulls latest runtime state.
3. Agent identifies repo / branch / run folder.
4. Agent follows source authority ladder.
5. Agent produces source-backed snapshot.
6. Human reviews pass / hold.
7. Agent drafts handoff or completion packet.
8. Human decides candidate / hold / accepted.
9. If accepted, update workflow candidate.
10. If repeated and validated, consider skill or automation candidate.
```

## 13. David-Side Workflow

David's desired workflow should become:

```text
David opens his agent
-> asks what needs attention in DDA Agent Ops
-> agent pulls latest source-backed state
-> agent identifies relevant repo / branch / run folder
-> agent prepares current-state snapshot
-> agent names missing/ambiguous sources
-> David evaluates pass / hold
-> agent returns what Emmanuel should pull or verify
```

David should not need to manually remember:

- which Codex conversation matters
- which branch contains latest state
- which run folder was last updated
- which artifact is candidate versus accepted
- which source owns the current truth

## 14. Emmanuel-Side Workflow

Emmanuel's current loop should become more explicit:

```text
Emmanuel starts with daily gameplan
-> runs Codex/ChatGPT synthesis
-> creates source-backed artifacts
-> stores them in dated run folder
-> pushes to GitHub
-> posts Slack update with artifact link/path
-> prepares handoff packet if David needs to act
-> receives David-side pass/hold result
-> updates next run folder with verification result
```

Emmanuel should make sure every day's output has:

- source ledger
- current-state snapshot
- open loops
- handoff or hold packet
- clear review-only status

## 15. Candidate-to-Canon Rule

Do not promote workflow structures too early.

Use this ladder:

```text
working note
-> candidate
-> test-ready
-> transferability-tested
-> accepted workflow candidate
-> skill/automation candidate
-> verifier/eval passed
-> human approved
-> canon
```

Current status of this workflow:

```text
candidate / test-ready
```

Not yet:

```text
accepted
canon
runtime-validated
automation-ready
skill-ready
eval-ready
```

## 16. What Should Remain Held

Hold these decisions for now:

- whether DDA Agent Ops becomes the final Context Vault
- full repo architecture
- full Linear / Symphony / Notion / Drive relationship
- automation design
- skill promotion
- eval creation
- memory save
- accepted infrastructure claim
- all-project master repo decision
- long-term SSI operating base design

These should only move forward after the transferability loop proves that David's agent and Emmanuel's agent can recover and exchange state reliably.

## 17. Recommended Next Experiment

After David runs the transferability packet, the next experiment should be:

```text
Emmanuel Pull Verification + Workflow Structure Fit Review v0.1
```

Purpose:

Test whether Emmanuel can pull David's artifact, verify it, and use it to decide whether the workflow structure should move from candidate to test-ready.

Expected verification questions:

1. Did David's agent use the right repo?
2. Did it use the right branch?
3. Did it locate the latest run folder?
4. Did it produce a source-backed snapshot?
5. Did it flag missing or ambiguous sources?
6. Did it avoid generic summary?
7. Did it avoid prohibited promotion claims?
8. Did it give Emmanuel enough information to pull and verify?
9. Did the loop reduce reconstruction burden?
10. Does this support the runtime launchpad model?

## 18. Recommendation

Adopt this first structure as the working candidate:

```text
DDA Agent Ops = shared runtime launchpad
GitHub run folders = durable daily state
Codex = repo-local execution
Linear / Symphony = project and gate tracking
Drive = transcript and shareable source docs
Notion = planning and knowledge
Slack = coordination
ChatGPT = reasoning and synthesis
Humans = intent and evaluation
```

This structure is strong enough to test now and flexible enough to evolve later.

Do not claim it as canon yet.

Treat it as the first workflow-structure candidate for David and Emmanuel to evaluate through the transferability test.

## 19. Codex Handling Note

This file captures the attached decision packet as a repo-local draft artifact. The only implementation action taken was to place the candidate in the dated run folder so it can be reviewed with the current transferability/source-topology lane.

No external write was performed. No commit or push was performed. No approval, canon, automation, skill, eval, memory, or runtime-readiness status was changed.
