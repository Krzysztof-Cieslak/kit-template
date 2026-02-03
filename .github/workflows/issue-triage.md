---
description: Automatically triage incoming GitHub issues by categorizing, labeling, and providing helpful responses
on:
  issues:
    types: [opened, edited]
roles: all
permissions:
  contents: read
  issues: read
  pull-requests: read
tools:
  github:
    toolsets: [default]
safe-outputs:
  add-labels:
    allowed: [bug, enhancement, documentation, question, "help wanted", "priority: high", "priority: medium", "priority: low"]
    max: 3
  add-comment:
    max: 1
  missing-tool:
    create-issue: true
---

<!-- Edit the file linked below to modify the agent without recompilation. Feel free to move the entire markdown body to that file. -->
{{#runtime-import agentics/issue-triage.md}}
