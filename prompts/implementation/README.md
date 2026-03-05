# Precise Implementation Prompts

Vague prompts cause agents to research broadly, filling context with irrelevant alternatives and increasing hallucination risk. Be specific.

## The Problem

```
❌ "Go and build an auth system."
```

The agent now has to research auth systems, compare options, weigh pros/cons — filling its context with implementation details across many possibilities. By the time it implements, it's confused.

## The Fix

```
✅ "Implement JWT authentication with bcrypt-12 password hashing, refresh token rotation with 7-day expiry."
```

No research needed. The agent knows exactly what you want and fills its context only with relevant implementation details.

## When You Don't Know the Details

Split into two tasks with separate sessions:

### Task 1: Research (Session A)
```
Research the available options for [TOPIC]. Compare pros/cons of [Option A] vs [Option B] vs [Option C]. 
Write your recommendation with reasoning to `research-[topic].md`.
```

### Task 2: Implement (Session B — fresh context)
```
Implement the approach described in `research-[topic].md`.
```

The key insight: the implementation agent never sees the rejected alternatives. Its context is clean.
