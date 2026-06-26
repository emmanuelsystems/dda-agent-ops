---
title: Emmanuel Side Pull Verify SOP
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
reviewer: David Abiera
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
created: 2026-06-25
approval_status: not_approved
outcome: sop_candidate
runtime_claim: none
canon_claim: none
automation_claim: none
skill_claim: none
eval_file_claim: none
memory_claim: none
external_write_claim: none
github_path: runs/2026-06-25/emmanuel-side-pull-verify-sop-v0.1.md
---

# Emmanuel Side Pull Verify SOP

## Review Boundary

This is a draft SOP for Emmanuel to verify a David-side state recovery snapshot. It does not perform a pull, update external tools, save memory, create skills/evals, commit, push, or claim readiness.

## Purpose

Define how Emmanuel should receive or pull David's snapshot and verify whether it reduced reconstruction burden.

## Required Inputs

| Input | Required value |
|---|---|
| Repo | `https://github.com/emmanuelsystems/dda-agent-ops.git` or local `F:/Codex Projects/dda-agent-ops` |
| Branch | Explicit branch name from David-side packet |
| Source folder | Exact `runs/YYYY-MM-DD/` folder |
| Source files | Exact file paths opened by David-side agent |
| Returned artifact | `runs/2026-06-25/david-side-dda-state-recovery-snapshot-v0.1.md` or explicitly named fallback path |
| Commit evidence | Commit message and hash if David-side commit/push was approved and completed; otherwise `not committed / held` |
| Reviewer status | Accepted / Held / Rework / Rejected / Not reviewed |

## Pull / Receive Verification Steps

1. Confirm the returned packet names repo, branch, folder, and files.
2. If a commit hash is provided, verify the branch and hash can be pulled or inspected locally before treating the snapshot as available.
3. Compare the returned packet to the current local branch and run folders.
4. Check whether the returned packet separates source facts from assumptions.
5. Check whether it preserves review-only hold posture.
6. Score reconstruction burden using the table below.
7. Decide whether the result is accepted, held, rework, or rejected.
8. Record missing sources and next owner.

## Reconstruction Burden Scorecard

| Score | Definition | Evidence required |
|---|---|---|
| Low | Emmanuel can continue from the returned packet with minimal source hunting. | Packet names active workflow, current truth, source paths, next route, owner, and hold gates. |
| Medium | Packet is useful but Emmanuel must still reconstruct branch, file, or gate context. | Some source paths or decisions are partial. |
| High | Packet is too broad, generic, or memory-dependent to continue execution. | Missing repo paths, missing current truth, or status overclaims. |
| Not measured | No useful burden evidence was captured. | No explicit example or reviewer status. |

## Pass Criteria

| Check | Pass condition |
|---|---|
| Branch clarity | The active branch is explicit. |
| Source clarity | Exact files and folders are named. |
| Source authority | GitHub, Notion, Slack, Drive, Linear, and chat roles are separated. |
| Proof posture | Verified, validated, candidate, accepted, canon, and runtime-ready are not collapsed. |
| Action clarity | Next action, owner, and gate are explicit. |
| Burden evidence | Low/Medium/High score includes one example. |
| Sync evidence | Commit/push status is explicit, or the output is clearly marked push-ready/held. |

## Hold Criteria

Return hold if any of these are missing:

- branch
- source folder
- exact files opened
- current truth
- owner
- reviewer status
- pass threshold
- reconstruction burden score
- commit/push status if a pull verification is requested
- human gate

## What This Proves

- Whether a David-side state recovery packet is useful enough for Emmanuel to continue execution.
- Whether source topology can be checked without relying on private memory.

## What This Does Not Prove

- It does not prove the underlying DDA runtime.
- It does not approve a canon source.
- It does not approve memory, skills, evals, automations, Slack, Notion, Linear, commits, pushes, or PRs.

## Expected Return From Emmanuel

```text
Result: Accepted / Held / Rework / Rejected
Burden score: Low / Medium / High / Not measured
Evidence example:
Missing source:
Commit/push status:
Next owner:
Next action:
Human gate:
```

## Human Gate

David/Emmanuel approval is required before using this SOP as a standard team process or promoting it into a template, skill, eval, memory, automation, Linear task, Notion page, Slack update, or canon doc.
