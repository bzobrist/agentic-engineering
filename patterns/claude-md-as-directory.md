# CLAUDE.md as a Directory

Your CLAUDE.md (or AGENTS.md) should be a lightweight router — not a 26,000-line manual. It tells the agent WHERE to find context, not what the context is.

## Template

```markdown
# CLAUDE.md

## First Thing
Read `rules/general.md` before any task.

## By Task Type

### Coding
- Before writing code: read `rules/coding.md`
- If writing tests: also read `rules/testing.md`
- If tests are failing: read `rules/test-debugging.md`

### Design / UI
- Before UI work: read `rules/design.md`
- For component patterns: read `skills/component-patterns.md`

### Deployment
- Before deploying: read `rules/deploy-checklist.md`

### Database
- Before schema changes: read `rules/database.md`
- For migrations: read `skills/migration-recipe.md`

## Project Context
- Architecture overview: `docs/architecture.md`
- API contracts: `docs/api.md`
```

## Why This Works

1. **Minimal context load** — Agent reads only what's relevant to the current task
2. **Conditional logic** — Different rules activate for different scenarios
3. **Easy to maintain** — Add/remove rules without touching the main file
4. **Nestable** — Rules can reference other rules: "If X, also read Y"

## Anti-Pattern

```markdown
# ❌ DON'T DO THIS
[14 pages of coding rules]
[8 pages of testing guidelines]
[6 pages of deployment steps]
[4 pages of design system]
[3 pages of meeting notes]
```

This forces the agent to load everything before it can write a single line of code.
