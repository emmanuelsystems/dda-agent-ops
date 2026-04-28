---
title: Source of Truth Model
asset_type: reference
status: draft
version: v0.1
owner: Emmanuel Olana
related_project: DDA Agent Ops Pilot
related_agent: diarized-daily-assistant
github_path: docs/source-of-truth.md
created: 2026-04-28
updated: 2026-04-28
---

# Source of Truth Model

## Core Rule

Notion is the planning and operating surface.  
GitHub is the durable markdown backend.  
Codex is the build and research execution layer.  
DDA is the daily alignment layer.  
Automations own recurrence.  
Durable artifacts own truth.

## Ownership

| Surface | Owns |
|---|---|
| Notion | Planning, triage, dashboards, working notes, active task status |
| GitHub | Prompt source, agent source, PRDs, app flows, instructions, skills, templates, evals, changelogs |
| Codex | Repo work, research, refactoring, markdown generation, verification |
| Slack | Approved team-safe updates |
| Memory | Approved durable preferences, patterns, decisions, and constraints |
| Chat history | Temporary working context only |

## Conflict Rules

| Conflict | Winner |
|---|---|
| Planning/status conflict | Notion |
| Prompt/agent source conflict | GitHub |
| Version history conflict | GitHub |
| Active task conflict | Notion unless mirrored to GitHub issues |
| Memory vs repo conflict | Repo |
| Chat history vs artifact conflict | Reviewed artifact |

## Durable Truth Rule

An instruction, decision, prompt, or workflow becomes durable only after it is stored in:

- GitHub markdown
- Approved Notion page
- Approved memory
- Reviewed issue/task
- Changelog entry
