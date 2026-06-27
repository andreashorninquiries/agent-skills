---
name: context-management
description: Keep long Claude Code sessions usable by compressing noisy tool output into focused summaries. Use during multi-step debugging, browser automation, repeated test runs, or multi-file work where logs and snapshots pile up.
user-invocable: true
---

# Context Management

In short sessions, context is invisible. In long ones, the window fills with information that is only partly useful — a stack trace with one useful line and hundreds that don't matter, a browser snapshot with the one button Claude needs buried in irrelevant page structure, a test run with one failing assertion lost among repeated logs and warnings.

The problem isn't only the amount of context. It's the **quality**. When raw output enters the conversation unchanged, Claude reasons inside a session that gets noisier every loop — and starts focusing on outdated errors, forgetting which files already changed, or repeating completed steps.

## What this skill does

Keep the signal, drop the noise. After each noisy step:

1. **Compress tool output into a useful summary** — what changed, what failed, what was confirmed, what the next likely cause is.
2. **Preserve the working state** — which files were changed, what decision was made, which error is still active, what needs to happen next.
3. **Make recovery easy** after the conversation gets long or is compacted.

Keep: the error message, the failing test name, the changed file, the decision made. Drop: repeated warnings, unrelated logs, stale snapshots, old outputs that no longer represent the current state.

## A worked example

Debugging a failing Playwright test, don't keep pasting full accessibility snapshots and browser states every iteration. Summarize each run into: what changed, what failed, what was confirmed, the next suspected cause. The debugging loop stays focused instead of drowning in stale snapshots.

Same for backend debugging: keep a compact record of the endpoint being tested, files changed, the latest error, the suspected cause, and the verification steps — not every log line.

## When to use it

Use it when the session has multiple loops, noisy outputs, or a real risk of losing the working state: long debugging, browser-based testing, multi-file refactors, repeated command output. Skip it for a small copy change or a single-function edit.

It doesn't make Claude smarter — it gives Claude a cleaner workspace, and makes the session easier for you to supervise.

Curated for The Agentic AI Cohort by Andreas Horn.
