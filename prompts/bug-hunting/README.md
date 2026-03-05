# Adversarial Bug Hunting Pipeline

A 3-agent system that exploits LLM sycophancy to find real bugs with high fidelity.

## How It Works

1. **Bug Hunter** — Aggressively finds every possible bug (over-reports by design)
2. **Skeptic** — Tries to disprove each bug (penalized 2x for dismissing real ones)
3. **Referee** — Final verdict using both inputs (told "ground truth" exists to increase care)

## Usage

**Critical:** Reset context between each agent (`/reset` in Claude Code, or use separate sessions). Feed each agent's output into the next prompt.

```
Agent 1 (Hunter) → copy output →
Agent 2 (Skeptic) → paste Hunter output + copy Skeptic output →
Agent 3 (Referee) → paste both outputs → final bug list
```

## Files

- [`01-hunter.md`](01-hunter.md) — Bug Finder agent prompt
- [`02-skeptic.md`](02-skeptic.md) — Adversarial Debunker prompt
- [`03-referee.md`](03-referee.md) — Final Arbiter prompt

## Why It Works

Each agent is exploited for what LLMs are hard-programmed to do — wanting to please:
- Hunter wants to please by finding bugs → over-reports (superset of all possible bugs)
- Skeptic wants to please by disproving → aggressively challenges (but has caution from 2x penalty)
- Referee wants to please by being accurate → careful judgment (told ground truth will check them)

Source: [@systematicls](https://x.com/systematicls/status/2028814227004395561), prompts by [@danpeguine](https://x.com/danpeguine/status/2029268229030285589)
