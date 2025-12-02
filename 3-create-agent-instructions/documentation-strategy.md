# Documentation

## Documentation as Memory

LLMs are stateless. Documentation is how knowledge persists across sessions.

Every session that learns something and doesn't capture it wastes that learning. The next session will rediscover it from scratch — or worse, make the same mistakes.

**The bar:** Could you delete the codebase and rebuild from the docs alone, with all decisions and learnings preserved?

See `continuous-memory.md` for the full principle.

## Keep It Minimal — Consolidate When Possible

### Standard docs (usually 3 files is enough)

1. **README.md** — What this is, current status, how to run/test, implementation progress
2. **AGENTS.md** — Map, purpose, and how to work on this project (timeless guidance)
3. **TESTING.md** — Manual QA procedures for each feature

### Avoid creating

- STATUS.md (put current status in README instead)
- CHANGELOG.md (use git commits)
- Redundant architecture diagrams (one in spec is enough)
- Phase-specific temporary docs

## Write Docs as You Go

Update in real-time, not just at wrap-up:

- **README.md**: What this is, current status, how to run it, how to test it
- **AGENTS.md**: Patterns used, key decisions, gotchas (keep timeless, not status)
- **TESTING.md**: Manual QA steps as features are added
- **API keys**: Document early — what to get, where to put it, .env.example with placeholder

A fresh AI agent or person should be able to pick up the work from these docs.

## Reference the Spec Clearly

- State where spec/plan lives (especially if outside code directory)
- Use relative paths from the code directory
- Mark it as "source of truth" for requirements

Why: "An LLM can only keep a subset of the codebase in its context at once. Being able to feed in relevant documentation lets it use APIs from other areas without reading the code first." — Simon Willison

State the working directory clearly up front and stick to it throughout.

## Keep Docs in Sync

- When you make changes, update all docs that reference them (README, comments)
- Keep things in sync — don't let docs drift from code

## Keep Spec/Plan in Sync with Implementation

**The Challenge:** Specs are written before implementation. Reality often reveals better approaches. If you only update code docs (README, TESTING.md), the spec/plan becomes outdated and misleads future work.

_The aspiration: be able to delete the codebase and start over from the spec, with all decisions captured. Implement a few times for learning before building the final version. That's the bar for keeping the spec up to date._

**The Pattern:** Update the spec document itself when implementation decisions differ from the original plan.

### In AGENTS.md, Include Guidance That:

1. **Identifies when updates are needed**
   - Architectural decisions that differ from spec
   - Core flow changes
   - Component additions/removals/changes
   - Performance considerations discovered during implementation

2. **Specifies where to update**
   - The spec document's path (relative to code directory)
   - Specific sections: Core Flow, Key Components, Architecture diagrams, Phase descriptions
   - Plan phases (especially "Done means" and "Test it" criteria)

3. **Explains the "why" behind changes**
   - Create an "Implementation Decisions Made During Development" section in the spec
   - Document reasoning, not just what changed
   - Preserves context for future agents/sessions

4. **Sets timing expectations**
   - Update immediately when making divergent decisions
   - Before committing the implementation
   - As part of phase wrap-up verification

5. **Reinforces that spec is source of truth**
   - Prevents building on outdated assumptions
   - Ensures new agents get accurate context
   - Makes the spec trustworthy for future work

### Style Notes

- Make it explicit and unavoidable — use words like "CRITICAL" or "MUST"
- Provide a concrete example from this specific project if possible
- Keep it actionable — agents should know exactly what to do and when
