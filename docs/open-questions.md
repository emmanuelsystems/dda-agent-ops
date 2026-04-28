---
title: Open Questions
asset_type: reference
status: draft
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: docs/open-questions.md
created: 2026-04-28
updated: 2026-04-28
---

# Open Questions

## Purpose

This file preserves unresolved questions from the backend strategy and conversion pipeline work. These questions should be resolved through approved Notion pages, reviewed repo commits, or explicit human decisions before the DDA pilot is treated as stable.

## Source Questions

- Which Notion DAB page is the approved source input for `agents/diarized-daily-assistant/source.md`?
- Which Notion database row or Prompts DB entry should be treated as the source inventory record?
- Which source fields must be preserved exactly during conversion?
- Which source materials are private, team-safe, or public?
- Which conversation-derived notes are approved context, and which should remain temporary chat context only?
- Should source excerpts be copied verbatim into the repo, summarized, or linked back to Notion?

## Repo Scope Questions

- Should `dda-agent-ops` remain a standalone repo long term, or later become a subfolder inside `systems-shaper-agents`?
- When should future candidate files such as `docs/project-charter.md`, `docs/asset-classification.md`, `templates/daily-log.md`, and `evals/README.md` be added?
- Should GitHub Issues be used for mirrored task tracking, or should active project tasks remain Notion-only for the pilot?
- What release or tag convention should be used after v0.1?
- Which repo files require frontmatter immediately, and which can remain lightweight README-style files during the scaffold phase?

## Source-of-Truth Questions

- What is the exact review process for converting Notion working notes into approved GitHub source files?
- What counts as an approved memory entry for this pilot?
- Where should approved agent improvement logs live after review?
- When daily logs exist in both Notion and GitHub, what is the review path before GitHub copies become durable archive?
- Who can approve a change to source-of-truth rules?

## DDA Pilot Questions

- What date should count as the first manual pilot run?
- Which output packets must DDA create each day?
- Which outputs should be reviewed before being committed?
- Which DDA outputs belong in Notion only, and which belong in `runs/YYYY-MM-DD/`?
- What minimum set of templates is required for the first manual run?
- What acceptance criteria make the v0.1 manual pilot successful?

## Conversion Pipeline Questions

- What does the first `inventory-record.md` look like, and should it live in Notion, GitHub, or both?
- What criteria decide whether a source asset should be preserved, merged, refactored, archived, or deleted?
- How should duplicate prompt variants be handled during conversion?
- What is the minimum viable PRD content before DDA can be manually tested?
- What is the minimum viable app flow before DDA can be manually tested?
- Which conversion checklist items are required for v0.1 versus deferred to v0.2?

## DDA vs Codex Boundary Questions

- What exact triggers require DDA to create a Codex handoff packet?
- What work is DDA allowed to complete directly without routing to Codex?
- What completion fields does DDA need from Codex to update Notion, Slack-safe summaries, memory candidates, or repo docs?
- How should DDA report work that Codex drafted but that has not yet been reviewed or committed?

## Integration Questions

- Which direct integrations are confirmed available for the manual pilot?
- Which direct integrations are explicitly out of scope for v0.1?
- Should Slack remain an approved-update surface only until manual pilot behavior is proven?
- Should Linear be used as an optional task surface for this repo, or deferred?
- How should ChatGPT Agent Builder consume the repo files after indexing?

## Automation Questions

- Which recurrence schedule is desired after the manual pilot?
- Which triggers should remain manual-only?
- Which workflows are candidates for reminder-only automation?
- Which workflows are candidates for draft-only automation?
- Which workflows are candidates for approval-gated automation?
- Which workflows should be marked do-not-automate?
- What fallback behavior is required if a scheduled check fails?
- Which actions require explicit human approval every time?
