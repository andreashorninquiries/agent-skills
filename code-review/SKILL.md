---
name: code-review
description: Treat Claude's generated code as a strong first draft and review it before merge — checking requirement match, edge cases, test coverage, and maintainability. Use after implementation, especially for auth, payments, permissions, migrations, or large refactors.
user-invocable: true
---

# Code Review

Generated code should not be treated as final just because it was produced quickly or the first test passed. Claude can write useful implementations, but it can also miss edge cases, make hidden assumptions, or introduce changes that work for the narrow task but don't fit the rest of the system. The quality problem in AI-assisted coding isn't always visible immediately — a change can look clean, pass the happy-path test, and still have weak error handling, incomplete validation, or missing coverage.

This skill gives Claude a second role: not just implementer, but a structured reviewer that inspects the work before you accept it. Treat every implementation as a **strong first draft that still needs review, testing, and human ownership.**

## The four layers of review

1. **Requirement match.** Compare the implementation against the original request — Claude sometimes solves a nearby problem instead of the exact one. If the task was "add role-based access control to a protected endpoint," check the role logic is on the correct routes, unauthenticated users are still handled, and existing users aren't accidentally blocked.
2. **Correctness.** Look for edge cases, missing branches, weak assumptions, failure modes. For a new endpoint: invalid request body, missing record, no permission, external dependency fails.
3. **Test coverage.** Tests existing isn't the same as tests being meaningful. Would they catch a real regression, or only confirm the code Claude just wrote? For an auth change: successful login, invalid credentials, expired tokens, missing roles, insufficient permissions, backward compatibility.
4. **Maintainability.** Does the change fit the project's style and structure? Did Claude add a new helper when a similar abstraction exists, or put logic in a route handler when the project uses a service layer? Ask not only whether the code works, but whether it belongs in this codebase.

## Why a separate review step

When Claude writes the code and immediately says it's done, the workflow becomes too trusting. A separate review changes the prompt from "finish the task" to "find what might be wrong with this." That shift reduces confirmation bias — the model now inspects and challenges the work instead of riding the momentum of implementation.

## Match depth to risk

A lightweight review is fine for a utility function or small UI tweak. Use a deeper, stricter review for auth, authorization, payments, billing, migrations, background jobs, data deletion, and large refactors — looking for security risks, missing permission checks, unsafe defaults, and silent data corruption.

This does not remove human review. You still read the diff, run the tests, and own the merge decision. It gives you a better starting point by surfacing suspicious areas first.

Curated for The Agentic AI Cohort by Andreas Horn.
