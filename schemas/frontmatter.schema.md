# Frontmatter Schema

Every durable markdown file should eventually include YAML frontmatter.

## Base Schema

```yaml
---
title:
asset_type:
status:
version:
owner:
related_project:
related_agent:
source_notion_url:
source_database:
github_path:
tags:
created:
updated:
---
```

## Asset Types

- prd
- app_flow
- agent_config
- instruction
- template
- skill_spec
- workflow
- daily_log
- handoff_packet
- completion_packet
- memory_model
- automation_plan
- evaluation
- reference
- changelog

## Status Values

- draft
- review
- approved
- active
- deprecated
- archived
