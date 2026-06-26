---
title: Codex Return Packet Template
asset_type: run_artifact
status: draft_review_only
version: v0.1
owner: Emmanuel Olana
reviewer: David Abiera
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
created: 2026-06-25
approval_status: not_approved
outcome: template_candidate
runtime_claim: none
canon_claim: none
automation_claim: none
skill_claim: none
eval_file_claim: none
memory_claim: none
external_write_claim: none
github_path: runs/2026-06-25/codex-return-packet-template-v0.1.md
---

# Codex Return Packet Template

## Review Boundary

This is a candidate return-packet template for source-topology or state-recovery experiments. It is not a canon template and does not replace `templates/codex-to-dda-completion.md`.

## Required Return Shape

```markdown
# Codex -> DDA Completion Packet

## 1. Completed Work

- What was completed:
- What artifact changed:
- Where it lives:
- Branch:
- Commit message:
- Commit hash, if available:

## 2. Evidence

- Files/docs reviewed:
- Outputs generated:
- Checks performed:
- Limits of evidence:

## 3. Unresolved Questions

- Question:
- Why unresolved:
- Suggested owner:

## 4. Blockers

- Blocker:
- Impact:
- Recommended next action:

## 5. DDA / Project Carryovers

- What should be carried forward:
- What should appear in the next plan:
- What should be reported:

## 6. Suggested Memory or Process Updates

- Candidate:
- Reason:
- Confidence:
```

## Source-Topology Addendum

For source-topology and state-recovery experiments, add:

| Field | Required entry |
|---|---|
| Repo | Local path and remote URL. |
| Branch | Current branch and whether command support was partial. |
| Git status | Clean, dirty, untracked, or conflicted. |
| Run folder | Exact `runs/YYYY-MM-DD/` folder used. |
| Files inspected | Every repo file inspected. |
| Missing sources | Explicit `Missing Source` rows. |
| Source facts | Repo paths, commit refs, command outputs, or reviewed external anchors. |
| Assumptions | Clearly labeled with confidence. |
| Proof posture | Verified / validated / candidate / accepted / canon / runtime-ready separated. |
| Human gate | Owner and required approval before promotion. |

## David-Side Snapshot Addendum

For the June 25 David-side state recovery experiment, include:

| Field | Required entry |
|---|---|
| Snapshot path | `runs/2026-06-25/david-side-dda-state-recovery-snapshot-v0.1.md` or fallback path. |
| Current truth | Active workstream, current status, and confidence. |
| Changes since last checkpoint | What changed after the last durable packet. |
| Open loops | Owner, evidence, and next action. |
| Missing/stale/ambiguous sources | Source, classification, impact, and suggested owner. |
| Source topology observations | What GitHub, Linear, Drive, Notion, Slack, ChatGPT, Codex, and DDA Agent Ops own and do not own. |
| Pass / hold verdict | Whether the state recovery reduced reconstruction burden, with evidence. |
| Commit/push status | Commit message and hash if approved and completed; otherwise held / not performed. |
| Pull verification request | What Emmanuel should pull and verify next. |

## What This Template Proves

- Codex can return an evidence-backed packet instead of a broad summary.
- The packet can separate outputs, checks, limits, blockers, and carryovers.

## What This Template Does Not Prove

- It does not prove any returned artifact is accepted.
- It does not approve committing, pushing, PR creation, Slack posting, Notion/Linear updates, memory updates, skill creation, eval creation, automation, canon, or runtime readiness.

## Pass / Hold Criteria

| Check | Pass | Hold |
|---|---|---|
| Completed work is specific | Named files and outputs. | Generic summary only. |
| Evidence is anchored | Files, folders, branch, checks, and limits are named. | No source anchors. |
| Questions and blockers are explicit | Owner and next action are named. | Unclear follow-up. |
| Proof posture is conservative | No readiness or canon overclaim. | Status is upgraded without gate. |
| Memory/process updates are candidate-only | Suggested but not saved. | Treats suggestion as saved learning. |
| Snapshot transport is separated from approval | Commit/push status is not treated as validation, canon, or acceptance. | Repo sync becomes a promotion claim. |

## Human Gate

David/Emmanuel approval is required before this candidate template replaces or updates any existing repo template, skill, eval, memory, automation, Slack process, Notion process, Linear process, or canon workflow.
