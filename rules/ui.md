> ✅ KEEP: Shared framework — do not change when switching projects.

# UI Rules (lightweight)

Inspectable UI constraints only. Global invent / scope / inspect rules live in `AGENTS.md`.

- Before adding UI, inspect existing components/styles in the touched area and reuse them when they fit
- If a design system or component library exists in the project, use it; do not introduce a parallel one
- Follow UI notes in `project-context.md` when present
- Prefer existing product tokens (colors, spacing, typography) over new one-off values
- Each new section should have one primary heading and one primary action when an action exists
- Support readable layout at common breakpoints used by the project (at minimum: mobile and desktop)
- Use cards only as interaction containers, not as default wrappers for every block
- Add motion/effects only for hierarchy, feedback, or an existing project pattern — not decoration alone
- Meet basic accessibility for changed UI: visible focus, labeled controls, sufficient contrast for text you add
