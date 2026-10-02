> ✅ KEEP: Shared framework — do not change when switching projects.

# Quality Rules

Code-quality specifics only. Scope control and self-check live in `AGENTS.md`.

- Keep code simple and readable
- Follow existing project conventions first
- Prefer clear code over clever code
- Avoid unnecessary abstractions and dependencies
- Keep functions/modules focused on one responsibility
- Handle errors explicitly; do not swallow them silently
- Comment only when intent is non-obvious; prefer “why” over “what”
- Avoid over-engineering for hypothetical future needs
- Preserve backward compatibility when existing APIs/clients depend on it — unless the user accepts a breaking change
- Remove dead or duplicated code only inside the touched scope and when safe
