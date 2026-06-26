---
title: Candidate To Canon Status Taxonomy
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
reviewer: David Abiera
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
created: 2026-06-25
approval_status: not_approved
outcome: taxonomy_candidate
runtime_claim: none
canon_claim: none
automation_claim: none
skill_claim: none
eval_file_claim: none
memory_claim: none
external_write_claim: none
github_path: runs/2026-06-25/candidate-to-canon-status-taxonomy-v0.1.md
---

# Candidate To Canon Status Taxonomy

## Review Boundary

This is a draft taxonomy for status discipline. It does not make any current artifact canon, accepted, runtime-ready, skill-ready, eval-ready, memory-ready, automation-ready, or promotion-ready.

## Why This Exists

The June 24 transcript analysis surfaced a recurring risk: complete-looking artifacts can feel like progress and still fail validation. This taxonomy keeps candidate, test-ready, accepted, superseded, blocked, reference-only, canon, and runtime-ready separate.

The June 25 source-topology framing adds a second risk: a successful handoff or repo sync can look like promotion. It is not promotion unless the correct reviewer gate and source authority are explicit.

## Status Definitions

| Status | Meaning | Allowed claim | Blocked claim | Required gate |
|---|---|---|---|---|
| Candidate | Useful proposal or draft not yet tested or accepted. | "Candidate for review." | Accepted, canon, validated, runtime-ready. | Human review. |
| Test-ready | Candidate has enough structure to run a bounded test. | "Ready for a review test." | Proven, accepted, canon. | Test owner and pass criteria. |
| Accepted | Human reviewer accepts the artifact for the scoped use. | "Accepted for this scope." | Canon beyond scope, runtime-ready. | Reviewer status and scope. |
| Superseded | Replaced by a newer reviewed artifact. | "Use newer artifact." | Current source. | Newer source path. |
| Blocked | Cannot move until missing source, owner, gate, or evidence is resolved. | "Held / blocked." | Complete, validated, ready. | Blocker owner. |
| Reference-only | Useful background, not governing status. | "Reference context." | Source of truth. | Clear non-authority label. |
| Canon | Approved governing source for a specific class of work. | "Canon for named scope." | Universal truth outside scope. | Explicit human approval and durable storage. |
| Runtime-ready | Proven live runtime behavior under accepted criteria. | "Runtime-ready for named scope." | General readiness outside tested scope. | Live evidence, reviewer acceptance, pass threshold, burden score, and approved promotion path. |

## Source Fact Vs Assumption Rules

| Type | Requirement |
|---|---|
| Source fact | Must cite repo path, branch, commit, reviewed external source, or explicit observed command result. |
| Assumption | Must be labeled as assumption with confidence. |
| Missing source | Must be labeled `Missing Source` instead of guessed. |
| External framing | Must not become canon unless approved and captured in the proper durable surface. |

## Promotion Path

```text
candidate -> test-ready -> accepted -> canon candidate -> canon
```

Runtime readiness is separate:

```text
verified structure -> validation candidate -> validated scoped runtime -> runtime-ready for named scope
```

For the June 25 source-topology experiment, use this gate order:

```text
source-topology candidate -> handoff test-ready -> accepted handoff pattern -> canon candidate
```

Do not skip from a David-side snapshot, Slack share, Drive handoff, or Git commit directly to canon.

## Pass / Hold Criteria

| Check | Pass | Hold |
|---|---|---|
| Status label present | Every artifact has one clear status. | Status is implied or ambiguous. |
| Scope named | The status applies to one lane or use case. | Status sounds global. |
| Gate named | Reviewer or approval owner is explicit. | Gate is missing. |
| Evidence named | Source path or missing source label exists. | Evidence is conversational only. |
| Blocked claims listed | Readiness/canon/promotion claims are blocked unless proven. | Artifact overclaims readiness. |
| Sync result separated | Commit/push success is treated as transport evidence only. | Commit/push is treated as acceptance or canon. |

## No-Touch Zones

This taxonomy must not be used to silently rewrite existing statuses, source-of-truth rules, memory, skills, evals, automations, Slack, Linear, Notion, Drive, commits, pushes, or PRs.

## Human Gate

David/Emmanuel approval is required before this taxonomy becomes a reusable template, canon process, skill, eval, memory update, automation rule, Linear workflow, Notion page, or Slack communication standard.
