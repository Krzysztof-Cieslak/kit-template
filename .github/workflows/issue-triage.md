---
description: Automatically triage incoming GitHub issues by categorizing them, assigning labels, and identifying relevant team members
on:
  issues:
    types: [opened]
roles: all
permissions:
  contents: read
  issues: read
  pull-requests: read
tools:
  github:
    toolsets: [default]
safe-outputs:
  add-comment:
    max: 1
  add-labels:
    allowed: [bug, feature, question, documentation, security, performance, priority:high, priority:medium, priority:low, area:frontend, area:backend, area:infrastructure, area:testing, needs-triage, duplicate]
    max: 5
  assign-to-user:
    max: 1
  missing-tool:
    create-issue: true
---

<!-- Edit the file linked below to modify the agent without recompilation. -->
{{#runtime-import agentics/issue-triage.md}}
