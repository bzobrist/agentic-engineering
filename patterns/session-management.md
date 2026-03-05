# Session Management

Long-running sessions accumulate context from unrelated tasks and drift. Fresh sessions with focused context perform better.

## The Problem with Long Sessions

A 24-hour session handling multiple tasks:
- Context bloat from earlier, unrelated work
- Compaction loses important details
- Agent starts making assumptions based on stale context
- Performance degrades over time

## Better: One Session Per Contract

```
Orchestration Layer
├── Contract A → Session 1 (fresh context) → complete → done
├── Contract B → Session 2 (fresh context) → complete → done
├── Contract C → Session 3 (fresh context) → complete → done
└── ...
```

Each session starts clean with only the context it needs:
- The task contract
- Relevant rules/skills
- The specific files to work on

## Context Hygiene After Compaction

Add this to your CLAUDE.md:

```markdown
## After Compaction / Context Reset
1. Re-read the current task plan
2. Re-read the relevant files for the current task
3. Do NOT make assumptions about code you haven't re-read
4. If uncertain about anything, read the file — don't guess
```

This prevents the biggest source of agent errors: filling in gaps with assumptions after compaction drops context.

## When Long Sessions Are Okay

- Interactive pairing sessions where you're actively guiding
- Exploratory research where context accumulates meaningfully
- Debugging sessions where prior attempts inform next steps

Even then, consider resetting if the agent starts acting confused.
