---
description: Automatically triage new issues when they are opened

on:
  issues:
    types: [opened]

permissions:
  contents: read
  issues: read
  pull-requests: read

safe-outputs:
  add-labels:
    max: 5
  add-comment:
    max: 1

---

# Issue Triage

Automatically analyze and triage newly opened issues by categorizing them, adding appropriate labels, and providing helpful initial responses.

## Instructions

When a new issue is opened (issue #${{ github.event.issue.number }}):

1. **Read the issue** - Analyze the issue title and body to understand what the user is reporting or requesting

2. **Categorize the issue** - Determine the type of issue:
   - `bug` - Something isn't working as expected
   - `feature` - A request for new functionality
   - `question` - A question about usage or documentation
   - `documentation` - Issues related to docs improvements

3. **Assess priority** - Based on the issue content:
   - `priority: high` - Security issues, data loss, or critical functionality broken
   - `priority: medium` - Important bugs or highly requested features
   - `priority: low` - Minor issues, nice-to-haves, or cosmetic problems

4. **Add appropriate labels** - Apply the category and priority labels to the issue

5. **Add a welcoming comment** - Post a brief, friendly comment that:
   - Thanks the user for opening the issue
   - Confirms what type of issue it appears to be
   - Sets expectations about next steps
   - Asks for any additional information if the issue is unclear

## Guidelines

- Be concise and professional in comments
- If the issue is unclear or missing key information, politely ask for clarification
- Do not make assumptions about implementation details
- Focus on understanding and categorizing, not solving the issue
