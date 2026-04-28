# DDA Agent Ops

## Purpose

This repo is the markdown backend for the Diarized Daily Assistant Agent pilot.

The DDA pilot converts a Notion-based DAB into a repo-backed workspace agent structure with PRD, app flow, instructions, memory rules, templates, evals, and Codex handoff workflows.

## Core Rule

DDA owns daily alignment.  
Codex owns build/research execution.  
Automations own recurrence.  
Durable artifacts own truth.

## Current Pilot

The first pilot agent is:

`agents/diarized-daily-assistant/`

## Repo Structure

- `docs/` stores project-level strategy and operating documents.
- `agents/` stores agent-specific source files.
- `templates/` stores reusable markdown templates.
- `runs/` stores date-specific daily pilot outputs.
- `skills/` stores future modular skill specs.
- `workflows/` stores repeatable operating workflows.
- `evals/` stores behavior and quality checks.
- `schemas/` stores markdown/frontmatter expectations.
- `references/` stores stable supporting context.

## Source of Truth

- Notion owns planning, triage, human dashboards, working notes, and task status.
- GitHub owns prompt source, agent source, PRDs, app flows, instructions, skills, templates, evals, and version history.
- Codex works inside this repo but does not become the source of truth until outputs are reviewed and committed.
- Chat history is not durable truth unless converted into Notion or GitHub artifacts.

## Current Status

Status: v0.1 scaffold.

This repo is being prepared for local VS Code + Codex usage.
