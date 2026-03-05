# Neutral Prompts (Anti-Sycophancy)

Agents want to please you. If you say "find bugs," they'll find bugs — even if they have to invent them. Neutral prompts avoid biasing the agent toward a specific outcome.

## Examples

### Code Review

```
❌ "Find me a bug in the database."
✅ "Search through the database code. Follow along with the logic of each component and report back all findings."
```

### Architecture Review

```
❌ "What's wrong with this architecture?"
✅ "Analyze this architecture. Describe how each component works, how they interact, and note anything that stands out."
```

### Performance

```
❌ "Find the performance bottleneck."
✅ "Trace the execution path of [request type]. Document the time complexity and resource usage of each step."
```

## Why It Works

Neutral prompts sometimes surface bugs, and sometimes just matter-of-factly describe how the code runs. But they don't bias the agent into thinking there IS a problem — which means when it does find something, it's more likely to be real.

## When to Use Biased Prompts

Sycophancy isn't always bad. When you KNOW there's an issue and want the agent to dig deep, a biased prompt can be more effective:

```
"There is a race condition in the payment processing flow. Find it and explain exactly how it occurs."
```

Use neutral prompts for discovery. Use biased prompts for targeted investigation.
