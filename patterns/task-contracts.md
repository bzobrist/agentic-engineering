# Task Contracts

Agents know how to start tasks but not how to end them. Task contracts define explicit, verifiable completion criteria.

## Template

Create a `{TASK}_CONTRACT.md` for each unit of work:

```markdown
# [Task Name] Contract

## Completion Criteria
This task is NOT complete until ALL of the following pass:

### Tests (do NOT edit these)
- [ ] `npm test -- --grep "auth"` — all tests pass
- [ ] `npm test -- --grep "refresh-token"` — all tests pass
- [ ] No test files were modified

### Code Verification
- [ ] No TODO/FIXME/stub implementations remain
- [ ] All functions have proper error handling
- [ ] No hardcoded credentials or secrets

### Visual Verification (if applicable)
- [ ] Take screenshot of [page/component]
- [ ] Verify [specific visual element] appears correctly
- [ ] Verify [specific behavior] works as expected

### Constraints
- Do NOT modify any test files
- Do NOT skip or mock any test assertions
- Do NOT mark task complete if any criterion fails
```

## In CLAUDE.md

```markdown
## Task Completion
Before terminating any session, verify that the active `{TASK}_CONTRACT.md` 
is fully satisfied. You may NOT end the session until all criteria pass.
```

## Why Tests + Screenshots

- **Tests** are deterministic — pass/fail, no ambiguity
- **Screenshots** catch visual/behavioral issues tests miss
- Together they give you confidence without manual review

## For Long-Running Automation

Create multiple contracts. Use a stop-hook that prevents session termination until all contracts are fulfilled. Better yet: one session per contract with fresh context each time.
