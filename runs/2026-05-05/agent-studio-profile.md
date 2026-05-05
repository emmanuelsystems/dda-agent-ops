# Agent Studio Profile

**Last updated from current editor configuration.**

## 1) Agent overview

- **Agent name:** DDA Agent
- **Short description:** Runs a manual daily alignment pilot with proof artifacts.
- **Icon:** brief
- **Owner:** Emmanuel Olana
- **Slack handle:** `dda-agent`
- **Live status:** Live version exists
- **Draft/live status:** Current draft matches live
- **Current editor surface:** Main editor
- **Default timezone:** Asia/Shanghai
- **Web search:** Available at runtime

## 2) System instructions summary

The agent is configured as a daily alignment and reflection agent for Systems Shaper. Its instructions emphasize:

- manual-first daily alignment
- evidence discipline and avoiding inflated claims
- producing a DDA artifact set under `runs/YYYY-MM-DD/`
- separating DDA orchestration from Codex execution
- using connected apps primarily as read-only context sources
- using Memory only for approval-gated durable operating context
- routing implementation-heavy work into structured Codex handoff packets

## 3) Starter prompts

### Start morning pull

- **Description:** Draft the morning context artifact.
- **Prompt:** Start the Morning Context Pull for today and draft the morning-context artifact.

### Classify my notes

- **Description:** Turn messy notes into intake.
- **Prompt:** Classify my top-of-mind notes into priorities, blockers, handoffs, and carryovers.

### Prepare proof pack

- **Description:** Create a meeting-ready proof package.
- **Prompt:** Prepare the pre-meeting proof package for DDA using the artifact-first format.

## 4) Configured skills

The following uploaded skills are attached to the agent.

### 1. daily-context-pull

- **Type:** Uploaded skill
- **Description:** Use when the operator needs a morning context snapshot assembled from yesterday's report, carryovers, schedule notes, project context, and other supplied daily inputs.

### 2. top-of-mind-classifier

- **Type:** Uploaded skill
- **Description:** Use when the operator shares messy notes, a transcript, or a check-in that should be classified into priorities, blockers, handoffs, carryovers, and other DDA buckets.

### 3. daily-game-plan-builder

- **Type:** Uploaded skill
- **Description:** Use when morning context and intake notes should be turned into a realistic DDA daily plan with priorities, time blocks, risks, and expected outputs.

### 4. midday-recenter

- **Type:** Uploaded skill
- **Description:** Use when the operator needs to compare the original game plan with actual progress and re-scope the rest of the day.

### 5. evening-report-builder

- **Type:** Uploaded skill
- **Description:** Use when the operator needs an end-of-day report, planned-vs-actual comparison, carryovers, and a tomorrow seed drafted from the day's artifacts.

### 6. codex-handoff-packet-builder

- **Type:** Uploaded skill
- **Description:** Use when work should be routed from DDA to Codex for repo edits, research, verification, refactoring, PRD updates, skill work, eval work, or automation planning.

### 7. codex-completion-intake

- **Type:** Uploaded skill
- **Description:** Use when a reviewed or review-pending Codex completion packet should be converted into DDA summaries, carryovers, updates, and next-step recommendations.

### 8. team-safe-slack-update-draft

- **Type:** Uploaded skill
- **Description:** Use when DDA artifacts should be converted into a concise team-safe Slack draft without exposing private reflection or unreviewed claims.

### 9. memory-candidate-review

- **Type:** Uploaded skill
- **Description:** Use when the operator wants durable preferences, decisions, constraints, or patterns surfaced as memory candidates for explicit approval.

### 10. pre-meeting-proof-packager

- **Type:** Uploaded skill
- **Description:** Use when the operator needs an artifact-first meeting proof package that states what changed, what is proven, what is not proven, and the next test.

## 5) Configured apps

## Gmail

- **Configured app:** Gmail
- **Connection mode:** Agent-owned account
- **Visible connected identity:** emmanuel@systemsshaper.com
- **Approval setting:** Never ask
- **Enabled actions:**
  - batch_read_email
  - get_profile
  - read_email
  - search_email_ids
  - search_emails
- **Observed posture:** Read-oriented

## Slack

- **Configured app:** Slack
- **Connection mode:** Agent-owned account
- **Visible connected identity:** emmanuel@systemsshaper.com
- **Approval setting:** Never ask
- **Enabled actions:**
  - slack_search_public
  - slack_search_public_and_private
  - slack_search_channels
  - slack_search_users
  - slack_read_channel
  - slack_read_thread
  - slack_read_canvas
  - slack_read_user_profile
- **Observed posture:** Read-oriented

## Notion

- **Configured app:** Notion
- **Connection mode:** Agent-owned account
- **Visible connected identity:** Notion MCP Server
- **Approval setting:** Never ask
- **Enabled actions:**
  - search
  - fetch
  - notion-get-comments
  - notion-get-teams
  - notion-get-users
  - notion-query-data-sources
  - notion-query-meeting-notes
- **Observed posture:** Read-oriented

## Google Drive

- **Configured app:** Google Drive
- **Connection mode:** Agent-owned account
- **Visible connected identity:** emmanuel@systemsshaper.com
- **Approval setting:** Never ask
- **Enabled actions:**
  - export_file
  - fetch
  - find_document_text_range
  - get_document
  - get_document_comments
  - get_document_paragraph_range
  - get_document_tables
  - get_document_text
  - get_file_metadata
  - get_presentation
  - get_presentation_comments
  - get_presentation_outline
  - get_presentation_tables
  - get_presentation_text
  - get_profile
  - get_slide
  - get_slide_thumbnail
  - get_spreadsheet_cells
  - get_spreadsheet_comments
  - get_spreadsheet_metadata
  - get_spreadsheet_range
  - list_drives
  - list_folder
  - recent_documents
  - search
  - search_spreadsheet_rows
- **Observed posture:** Read-oriented

## Linear

- **Configured app:** Linear
- **Connection mode:** Agent-owned account
- **Visible connected identity:** Linear MCP Server
- **Approval setting:** Never ask
- **Enabled actions:**
  - get_attachment
  - list_comments
  - list_cycles
  - get_document
  - list_documents
  - extract_images
  - get_issue
  - list_issues
  - list_issue_statuses
  - get_issue_status
  - list_issue_labels
  - list_projects
  - get_project
  - list_project_labels
  - list_milestones
  - get_milestone
  - list_teams
  - get_team
  - list_users
  - get_user
  - search_documentation
  - list_customers
  - list_initiatives
  - get_initiative
  - get_status_updates
  - search
  - fetch
- **Observed posture:** Read-oriented

## GitHub

- **Configured app:** GitHub
- **Connection mode:** Agent-owned account
- **Visible connected identity:** emmanuel@systemsshaper.com
- **Approval setting:** Confirmation required for consequential write actions
- **Enabled actions:** Read and write actions are enabled
- **Observed posture:** Mixed read/write
- **Notes:** The current instructions say GitHub is the only connected app that may be used as a controlled write destination, and only with explicit approval.

## 6) Connected identities summary

| App | Visible connected identity |
|---|---|
| Gmail | emmanuel@systemsshaper.com |
| Slack | emmanuel@systemsshaper.com |
| Notion | Notion MCP Server |
| Google Drive | emmanuel@systemsshaper.com |
| Linear | Linear MCP Server |
| GitHub | emmanuel@systemsshaper.com |

## 7) Memory and runtime settings

- **Memory:** Enabled
- **Instructions-level memory policy:** Approval-gated only
- **Approved memory use described in instructions:**
  - stable user preferences
  - durable workflow preferences
  - confirmed project facts
  - repeated working patterns
  - approved decisions
  - persistent operating constraints
- **Explicitly disallowed in instructions:**
  - automatic memory saving
  - raw private reflection
  - speculative assumptions
  - sensitive Slack or email content
  - unreviewed outputs

## 8) Channel and trigger configuration

## ChatGPT channel

- **Available:** Yes
- **ChatGPT schedules configured:** No

## Slack channel deployment

- **Slack deployment present:** Yes
- **Channel name:** `diarized-daily`
- **Channel ID:** `C073QL4CFC4`
- **Visibility:** private
- **Trigger mode:** mention
- **Enabled:** Yes
- **Channel-specific instructions:** None visible

## Scheduled automations

- **ChatGPT schedules:** None
- **Slack schedules:** None

## 9) Agent files

- **Agent files currently attached:** None visible
- **Current file tree state:** No attached files present before this document was created

## 10) Preview and testing status

- **Visible preview conversations:** None
- **Actual supervised runtime test output available:** No visible preview output yet

## 11) Evidence interpretation notes

This document captures the currently visible configured profile in the editor, including:

- agent identity and overview
- instructions summary
- attached skills
- connected apps and observed action posture
- visible connected identities
- memory status
- channel and trigger setup
- current lack of schedules and preview outputs

This document does **not** by itself include:

- screenshots
- a UI-export of runtime action menus
- actual preview transcript output
- proof that a live automation has already fired

## 12) Manual screenshot checklist

For a fuller evidence package, capture these manually from the editor:

1. Agent Studio main profile view
2. Skills list view
3. Apps/tools view
4. Memory settings view
5. Slack trigger/channel setup view
6. Runtime action surface during a test
7. Preview output from an actual supervised run
