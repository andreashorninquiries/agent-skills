---
name: skill-creator
description: Turn a repeated prompt or process into a reusable Claude Code skill. Use when you notice yourself writing the same long instructions a third or fourth time — a review checklist, a testing workflow, a documentation format, a codebase-onboarding routine.
user-invocable: true
---

# Skill Creator

The first skill worth having is the one that helps you build other skills. Most serious work with Claude Code becomes repetitive: you review similar files, follow the same conventions, apply the same testing strategy, ask for the same implementation process again and again. If you keep typing those instructions by hand, you don't have a workflow — you have a long prompt you keep repeating.

A skill is not a saved prompt. It is a reusable process that teaches Claude how a specific job should be done.

## When to build one

Build a skill when a task is **repeated, structured, and important enough that consistency matters**. A good candidate has a clear purpose, a clear trigger, and a clear output. If the task is vague, changes every time, or depends on one specific conversation, keep it as a normal prompt.

The rule of thumb: when you write the same instructions for the third or fourth time, that prompt is becoming a skill.

## What to do

1. Ask me to describe the workflow in plain English — a rough process, an internal SOP, a checklist, or a messy prompt I already use.
2. Identify the trigger (when should Claude apply this?), the inputs, the steps, and the expected output.
3. Draft a `SKILL.md`: short frontmatter (`name`, `description`) and a body that lays out the process as numbered steps.
4. Keep it tight. One job per skill. Don't pack three workflows into one file.
5. Tell me where it goes (`.claude/skills/<name>/SKILL.md`) and how to test it on a real task.

## Cautions

- Don't create skills too early or for everything — a crowded setup is harder to use than a lean one.
- Start with one workflow you already repeat. Use it in a real project, improve it after you see where it fails, then build the next.
- The goal is not more files. The goal is to make Claude follow your process reliably.

Curated for The Agentic AI Cohort by Andreas Horn.
