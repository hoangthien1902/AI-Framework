# Plan

Follow `AGENTS.md` for global rules. `rules/workflow.md` decides **when** to plan; this file defines **how**.

## Purpose

Produce an **implementation plan** (what to change and in what order) — not a deep architecture study.
Do not implement until the plan is approved (unless the user explicitly overrides per `AGENTS.md`).

## When architect is needed

Use `agents/architect.md` **only** when the task has a meaningful architectural decision
(new boundaries, data model shape, major dependency, cross-cutting redesign).

Architect may be invoked **as part of planning**. It does **not** replace this plan approval gate.

## Workflow

1. Read `project-context.md` and inspect relevant files/patterns (inspect before asking).
2. Understand requirements and constraints.
3. Identify affected components and the implementation flow.
4. If an architectural decision is needed, run architect analysis and fold results into the plan.
5. Present the plan to the user and wait for approval.
6. Do not implement until approved (or explicit skip-plan override).

## Output

- Goal
- Changes
- Implementation flow
- Testing
- Risks
- (Optional) Architecture notes / link to architect output when used

## Rules

- Reuse existing patterns.
- Keep the plan simple and practical.
- Ask only when missing info still materially affects the solution after inspect.
- Invoking this command requires approval before implementation, unless explicitly overridden.
