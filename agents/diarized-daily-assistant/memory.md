---
title: DDA Memory Model
asset_type: memory_model
status: draft
version: v0.2
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: agents/diarized-daily-assistant/memory.md
created: 2026-04-28
updated: 2026-04-29
---

# DDA Memory Model

## Purpose

Define what DDA may propose as memory and what requires approval.

This file defines candidate memory behavior. It does not authorize DDA, Codex, or automations to save persistent memory without explicit human approval.

## Memory Candidate Criteria

DDA may propose a memory candidate when the information is:

- Repeated across multiple reviewed runs.
- Useful for future daily alignment.
- Stable enough to reuse.
- Safe to store outside the immediate chat.
- Not already better represented by a committed repo file or approved Notion record.

Examples:

- Preferred daily update format.
- Recurring approval boundary.
- Stable source-of-truth rule.
- Repeated carryover handling preference.
- Confirmed meeting prep pattern.

## Do Not Store as Memory

DDA must not propose persistent memory for:

- Private reflection not intended for team-facing work.
- Raw transcript content.
- Credentials, tokens, secrets, or private identifiers.
- Unreviewed speculation.
- Temporary stress, mood, or one-off context.
- Source-of-truth claims that belong in GitHub or Notion.

## Private vs Team-Safe Distinction

Private working context:

- May help the current run.
- Should stay in the run artifact only if needed.
- Must not be promoted to team-facing docs without review.

Team-safe operating context:

- Can be included in repo docs, Notion notes, or Slack-safe drafts after review.
- Should avoid private reasoning and unverified assumptions.

## Approval Requirements

Human approval is required before:

- Saving persistent memory.
- Treating a memory candidate as durable.
- Sharing a memory-derived preference externally.
- Resolving a conflict by changing source-of-truth behavior.

## Conflict Behavior

If memory conflicts with committed repo files, committed repo files win.

If memory conflicts with approved Notion planning/status, Notion wins for planning/status.

If memory conflicts with a reviewed Linear issue used as the active task surface, the issue wins for that task until it is superseded.

If memory conflicts with raw chat, memory only wins if it was approved and the chat was not converted into a reviewed artifact.

## Candidate Review Format

Use this structure when proposing memory:

```md
## Memory Candidate

Statement:

Why it matters:

Evidence:

Scope:

Risk if stale:

Approval needed:
```
