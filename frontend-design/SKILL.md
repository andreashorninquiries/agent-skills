---
name: frontend-design
description: Push Claude's UI output beyond the generic default — guiding it to think about hierarchy, spacing, states, responsiveness, accessibility, and the existing design system before writing the final interface. Use for dashboards, landing pages, admin panels, onboarding flows, docs pages, and demos.
user-invocable: true
---

# Frontend Design

Claude Code can generate UI components, landing pages, dashboards, settings screens, and forms. The problem is that the first version often looks functional but generic. The component structure, API calls, and state handling may be right, while the visual result still feels like a default AI interface — uniform layout, random spacing, unclear hierarchy, missing interface states.

This skill moves Claude from "generate a component" to "design a usable screen." The goal is not decoration. It's to treat frontend work as product work.

## What Claude should decide before writing the final UI

1. **Purpose of the screen.** A dashboard, a pricing page, a settings screen, and a data table do not need the same layout.
2. **Hierarchy.** What should the user notice first? Group by priority; make the most important content easy to scan.
3. **All the states**, not just the happy path: loading, empty, error, disabled, success, active.
4. **Responsiveness.** A layout that works on a wide desktop may break or feel awkward on mobile.

## Match the existing design system

In real projects you usually don't want Claude to invent a new style — you want it to match the product. The skill should guide Claude to inspect existing components, spacing tokens, color variables, typography rules, and interaction patterns before creating anything new. If the project uses Tailwind, shadcn/ui, Material UI, or a custom library, reuse it. This keeps the interface consistent with the rest of the codebase.

## Avoid the generic-page traps

Quick landing pages tend to repeat the same shape: hero, three feature cards, testimonial, pricing, CTA. Push Claude to consider the specific product, audience, and main user problem first — and to avoid vague feature cards, overly balanced sections, identical icon blocks, and buttons that compete for attention.

## The hidden failure cases

UI work breaks in states that are easy to skip: a button when disabled, a form when validation errors appear, a table with fifty rows instead of five, a card layout on mobile, a dashboard with real data instead of fake. Remind Claude to implement these, not just the happy path.

## Limits

A design skill does not replace a real designer, a product owner, or user research, and it can't infer your brand with no examples. If you want a specific style, give references, screenshots, design tokens, or component examples. The skill gives Claude a stronger process; the output still depends on the direction you provide.

Use it when the output is visual and user-facing. Skip it for a backend service, a CLI tool, or a data pipeline.

Curated for The Agentic AI Cohort by Andreas Horn.
