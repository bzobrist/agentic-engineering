# Rules vs Skills

Both encode knowledge for your agent, but they serve different purposes.

## Rules = Preferences ("Don't do that")

Create a rule when you see the agent do something you don't like.

```markdown
# rules/coding.md

- Never use `var` in JavaScript — always `const` or `let`
- Always use named exports, never default exports
- Error messages must include the function name and input that caused them
- Never catch errors silently — always log or re-throw
```

## Skills = Recipes ("Do it like this")

Create a skill when you want something done a specific, repeatable way.

```markdown
# skills/deploy-to-prod.md

1. Run `npm run build` and verify no errors
2. Run `npm test` — all tests must pass
3. Create a git tag: `git tag -a v{version} -m "Release {version}"`
4. Push with tags: `git push origin main --tags`
5. Deploy: `./scripts/deploy.sh production`
6. Verify health check: `curl https://api.example.com/health`
7. If health check fails, rollback: `./scripts/rollback.sh`
```

## When to Create Each

| Trigger | Action |
|---------|--------|
| Agent does something wrong | Write a **rule** |
| You want a specific process followed | Write a **skill** |
| Agent asks how to do something | Write a **skill** |
| Agent keeps making the same mistake | Write a **rule** (and check existing rules for contradictions) |

## Research → Skill Pattern

Don't know how you want something done? Ask the agent to research it and write it as a skill:

```
Research how to implement database migrations for PostgreSQL with zero downtime.
Write your recommended approach as a step-by-step skill in `skills/zero-downtime-migration.md`.
```

Review the skill, correct anything, and now the approach is deterministic for future tasks.

## Maintenance

Rules and skills accumulate. Periodically:
1. Check for contradictions between rules
2. Consolidate overlapping skills
3. Remove outdated rules (agent capabilities change with model updates)
4. Ask the agent: "Review all rules and skills. Flag any contradictions or redundancies."
