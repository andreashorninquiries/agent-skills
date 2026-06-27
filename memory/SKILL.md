---
name: memory
description: Help Claude carry project knowledge across sessions — architecture decisions, conventions, key commands, known issues, and unfinished work — so you don't re-explain the project every time. Use for work that spans days or weeks, or across multiple repos.
user-invocable: true
---

# Memory

Context management keeps Claude focused on the current session. Memory is different: it carries useful project knowledge into **future** sessions. Most real work doesn't happen in one sitting — you build a feature today, fix related bugs tomorrow, return to the repo two weeks later, or switch between several client projects.

Without memory, every new session starts with the same overhead: explain the project again, remind Claude what's done, describe the important files, reconstruct earlier decisions.

Memory is not about remembering everything. It's about preserving the knowledge that would otherwise need re-explaining every time.

## What to capture

A good memory layer holds what stays useful beyond the current interaction:

- Architectural decisions and the reasons behind them
- Project conventions (error-handling pattern, testing style, documentation format)
- Important commands (how tests run, how to deploy)
- Known fragile areas and previous bugs
- Unfinished tasks and the next step

It should **not** store every message or command. A raw dump creates the same problem as unmanaged context — too much information, not enough signal. Keep memory selective, structured, and easy to inspect.

## Treat it as a project handoff

At the end of a useful session, record: what changed, what was decided, what still fails, which files matter, what to check next. At the start of the next session, retrieve only the relevant parts of that handoff.

## Never trust memory blindly

Memory goes stale. A file gets renamed, a decision changes, a command stops working. So:

1. Keep it **inspectable** — I should be able to see, correct, and delete what Claude remembers.
2. **Verify against the current repo** before relying on it. If memory says auth lives in `middleware/auth.py`, inspect the file before editing. If it says tests run with `pytest tests/test_auth.py`, confirm that still matches the setup.

Use memory as a map, then confirm the map against the actual project.

## When to use it

Use it for projects that continue across days or weeks, repos with many conventions, parallel features, or whenever re-explaining the project becomes a noticeable cost. Skip it for a quick edit in a small script.

Curated for The Agentic AI Cohort by Andreas Horn.
