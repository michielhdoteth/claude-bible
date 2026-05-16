---
name: acceptance-traceability
description: Map PRD requirements to tasks, tests, and evidence so plan/build handoffs stay tight and verifiable.
compatibility: opencode
---

# Acceptance Traceability

## Purpose

Turn vague progress into verifiable delivery by tracing:

- PRD requirement
- plan task
- implementation change
- test evidence
- final acceptance outcome

## Use when

- converting PRD items into buildable tasks
- reviewing whether a task is truly done
- preparing release or client evidence

## Workflow

1. Extract each concrete requirement
2. Map it to one or more task IDs
3. Map each task to specific tests or validation steps
4. Record evidence paths
5. Mark each requirement as unmet, partial, or satisfied

## Output format

```markdown
| Requirement | Task | Evidence | Status |
|---|---|---|---|
| Users can reset password | TASK-012 | tests/auth/reset.test.ts, PR link | satisfied |
```

## Rules

- do not mark satisfied without evidence
- prefer concrete test files or commands over narrative claims
- if evidence is missing, status stays partial or unmet
