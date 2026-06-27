---
name: planning
description: Make Claude inspect the task and the codebase, then propose a plan, before it edits a single file. Use for any change with uncertainty — multiple files, core business logic, auth, billing, migrations, or a refactor that could sprawl.
user-invocable: true
---

# Planning

This is the skill that stops Claude from coding too early. Many tasks start as a rough request, a bug report, or a short instruction that hides a lot of technical decisions. When Claude starts editing right away, it can produce something that looks reasonable but doesn't match the architecture, misses an edge case, ignores an existing abstraction, or solves only the visible part of the problem.

A planning skill turns "start editing now" into "understand the task, inspect the codebase, define the plan, then implement."

## What Claude must do before editing

1. **Restate the task** in concrete terms. Many prompts are ambiguous — say back what you understood.
2. **Inspect the relevant code** instead of guessing from memory or the current file alone. Read the middleware, route handlers, models, permission checks, and tests that the change touches.
3. **List the files likely to change** and explain why.
4. **Propose an implementation plan** I can review and correct before any code is written.
5. **Define how the change will be tested.** Implementation without verification is where AI coding gets unreliable.

Then wait for confirmation before applying changes.

## When to use it

Use planning when the task has uncertainty, touches multiple files, affects core behavior, or needs tests. It's most valuable for sensitive areas — authentication, authorization, billing, permissions, database migrations, background jobs, production APIs — where a rushed change can cause security issues, broken access, or data problems.

For refactors, the plan should define scope first: what changes, what stays the same, which public interfaces must be preserved, and which tests prove behavior didn't change.

## When to skip it

Don't force a full plan on a typo, a label change, or a one-line constant. Match the planning effort to the cost of getting it wrong. The goal is not to make Claude slower — it's to make the implementation inspectable before it becomes a large diff.

Curated for The Agentic AI Cohort by Andreas Horn.
