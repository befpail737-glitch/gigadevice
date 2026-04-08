---
name: "memory-management"
description: "Manages project memory with HOT/WARM/COLD tiers for SEO and marketing projects. Invoke when user needs to initialize, update, or retrieve project memory state, context, or cross-session data persistence."
---

# Memory Management Skill

## Overview

This skill provides a structured memory system for managing project context across sessions using a three-tier architecture:

- **HOT**: Active working memory - current session context, immediate priorities
- **WARM**: Recent project state - ongoing work, recent decisions, key findings  
- **COLD**: Long-term archive - completed work, historical data, reference materials

## Memory Structure

```
.trae/memory/
├── HOT.json          # Active session context
├── WARM.json         # Recent project state
├── COLD/             # Long-term archives
│   ├── archives/     # Historical snapshots
│   └── references/   # Reference materials
└── index.json        # Memory index and metadata
```

## When to Invoke

- Initialize memory for a new project
- Store important findings or decisions during work
- Update project context between sessions
- Retrieve previous session context
- Archive completed work

## Commands

### Initialize Memory
```bash
# Creates HOT/WARM/COLD structure
memory-init --project <name> --type <seo|marketing|dev>
```

### Update Memory
```bash
# Updates specific tier
memory-update --tier <hot|warm|cold> --data <json>
```

### Retrieve Memory
```bash
# Gets memory from specific tier
memory-get --tier <hot|warm|cold> --key <key>
```

### Archive Memory
```bash
# Moves WARM to COLD archive
memory-archive --from warm --to cold --tag <tag>
```

## Data Schema

### HOT Memory
```json
{
  "session_id": "uuid",
  "timestamp": "ISO8601",
  "active_tasks": [],
  "current_context": {},
  "priority_keywords": [],
  "target_countries": [],
  "business_advantages": []
}
```

### WARM Memory
```json
{
  "project_summary": "",
  "topic_clusters": [],
  "priority_keywords": [],
  "competitor_insights": [],
  "recent_decisions": [],
  "pending_items": []
}
```

### COLD Memory
```json
{
  "archives": [
    {
      "date": "ISO8601",
      "type": "report|analysis|deliverable",
      "summary": "",
      "key_findings": []
    }
  ]
}
```
