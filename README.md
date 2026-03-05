# Agentic Engineering

A collection of prompts, patterns, and techniques for getting the most out of AI coding agents (Claude Code, Codex CLI, etc).

## What's Here

```
prompts/
  bug-hunting/          # 3-agent adversarial bug detection pipeline
  implementation/       # Precise implementation prompts
  neutral-prompts/      # Anti-sycophancy prompt patterns
patterns/
  claude-md-as-directory.md   # CLAUDE.md as if-else router
  task-contracts.md           # Teaching agents when to END
  rules-vs-skills.md          # When to use each
  session-management.md       # Fresh sessions > long-running
  iterate-cycle.md            # The add → magic → bloat → cleanup loop
```

## Quick Start

1. Start with the base CLI (Claude Code or Codex) — no plugins needed
2. Read [`patterns/claude-md-as-directory.md`](patterns/claude-md-as-directory.md) to structure your CLAUDE.md
3. Use [`prompts/implementation/`](prompts/implementation/) to write precise task prompts
4. Try [`prompts/bug-hunting/`](prompts/bug-hunting/) for adversarial code review

## Sources

- [@systematicls — "How To Be A World-Class Agentic Engineer"](https://x.com/systematicls/status/2028814227004395561) (Mar 3, 2026)
- [@danpeguine — Bug hunting prompts](https://x.com/danpeguine/status/2029268229030285589) (Mar 4, 2026)

## Philosophy

> "You don't need the latest agentic harnesses, you don't need to install a million packages. In fact, your enthusiasm is likely doing more harm than good."

The key insight: if a technique is truly useful, the foundation companies (Anthropic, OpenAI) will incorporate it into their base products. Focus on fundamentals over tooling.

## Contributing

Found a useful agentic pattern? Open a PR.

## License

MIT
