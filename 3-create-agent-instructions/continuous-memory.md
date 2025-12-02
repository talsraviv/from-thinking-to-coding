# Continuous Memory: Building Institutional Knowledge

## The Problem: Agents Are Stateless

LLMs know nothing about your codebase at the start of each session. Their weights are frozen — they don't learn over time. The only thing they know is what's in the context window.

AGENTS.md is the only file automatically loaded every session. This makes it precious: **documentation isn't just instructions — it's memory.**

Every insight, every gotcha, every "aha moment" that isn't captured is lost when the session ends.

## The Principle: Leave It Smarter

Every session should leave the documentation smarter than it found it.

This creates compounding value:
- Session 1 discovers a gotcha → captures it
- Session 2 avoids that gotcha → discovers another → captures it
- Session 3 benefits from both learnings
- ...knowledge accumulates

Without this discipline, each session rediscovers the same problems. With it, knowledge compounds.

## What to Capture and Where

### AGENTS.md (Timeless How-To Knowledge)

Capture immediately when you discover:
- Framework gotchas ("hot reload doesn't work for X files")
- Patterns that work ("always do X before Y")
- Patterns that don't work ("tried X, it breaks Y")
- Architectural decisions and their rationale
- Commands that are frequently needed
- Things that would confuse a future agent

### Spec/Plan (Design Decisions)

Update when implementation reveals:
- A better approach than originally planned
- Why you diverged from the spec
- Constraints discovered during implementation
- Architectural decisions that affect the design

### README.md (Current State)

Update to reflect:
- What's actually built (not what's planned)
- What works right now
- How to verify it works

## When to Update

**Don't wait for wrap-up.** Capture learnings as they happen:

1. **Immediately** after discovering something non-obvious
2. **Before committing** any architectural decision
3. **When you notice** yourself doing something repeatedly
4. **When you think** "a future agent would need to know this"
5. **At wrap-up** as a final sweep for anything missed

## The Habit to Build

At natural pauses, ask yourself:

> "What have I learned this session that a future session needs to know?"

If the answer is anything, update the docs before moving on.

Another useful prompt:

> "What would confuse a future agent about this?"

## In AGENTS.md, Include This Guidance

```markdown
## Continuous Documentation

**As you work, actively update documentation:**

- **AGENTS.md**: When you discover gotchas, patterns, or decisions
- **Spec**: When implementation differs from plan
- **README.md**: When status or capabilities change

Don't wait for wrap-up. Capture learnings immediately.

Ask yourself: "What would confuse a future agent about this?"
```

## Why This Matters

The bar for documentation quality: **Could you delete the codebase and rebuild from the docs alone, with all the decisions and learnings preserved?**

Each session that learns something and doesn't capture it wastes that learning. The next session will rediscover it from scratch — or worse, make the same mistakes.

Your job isn't just to read AGENTS.md. It's to cultivate it.

