# The Iterate Cycle

The process of building an effective agent setup is cyclical, not linear.

## The Cycle

```
1. Start barebones (just CLI, no plugins)
         ↓
2. Agent does something wrong → write a rule
         ↓
3. Want something done a specific way → write a skill
         ↓
4. Agent starts feeling like magic ✨
         ↓
5. Performance degrades (too many rules/skills contradicting)
         ↓
6. Clean up: consolidate, remove contradictions
         ↓
7. Magic again ✨
         ↓
   (repeat from 2)
```

## Phase 1: Barebones

- Install Claude Code or Codex CLI
- Create a minimal CLAUDE.md (just the directory structure)
- Start working

Don't install plugins. Don't set up memory systems. Don't read 50 blog posts about optimal setups. Just start.

## Phase 2: Build Up

As you work, you'll notice the agent doing things you don't like:
- Add a rule: "Don't do X"
- Add a skill: "Do Y like this"
- Update CLAUDE.md to point to the new files

Each addition makes the agent feel smarter and more aligned.

## Phase 3: Magic

After enough rules and skills, the agent starts doing things "the way you want." It feels like it understands you. This is the sweet spot.

## Phase 4: Decay

Eventually:
- Rules contradict each other
- Skills overlap or conflict
- Too many files to read before starting
- Context bloat makes the agent slower and less accurate

You'll notice the agent getting confused or doing weird things again.

## Phase 5: Clean Up

Tell the agent:
```
Review all files in rules/ and skills/. 
Flag any contradictions, redundancies, or outdated entries.
Suggest consolidations.
Ask me for updated preferences where things are unclear.
```

Prune aggressively. Merge overlapping files. Resolve contradictions by choosing one approach.

Then you're back to magic. Repeat forever.

## The Key Insight

This cycle is natural and expected. Don't fight it. Don't try to build the perfect setup on day one. Let it evolve through real usage.
