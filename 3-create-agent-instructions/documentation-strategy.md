# Documentation

## Keep it minimal - consolidate when possible.

## Standard docs (usually 3 files is enough)

1. **README.md** - What this is, current status, how to run/test, implementation progress
2. **AGENTS.md** - How to work on this project (timeless guidance)
3. **TESTING.md** - Manual QA procedures for each feature

## Avoid creating

- STATUS.md (put current status in README instead)
- CHANGELOG.md (use git commits)
- Redundant architecture diagrams (one in spec is enough)
- Phase-specific temporary docs

## Write docs as you go so a fresh AI agent or person could pick up the work

- Update README.md with: what this is, current status, how to run it, how to test it
- Update AGENTS.md with: patterns used, key decisions, gotchas (keep timeless, not status)
- Update TESTING.md with: manual QA steps as features are added
- Document API keys early: what to get, where to put it, .env.example with placeholder

## Reference the spec clearly in all docs

- State where spec/plan lives (especially if outside code directory)
- Use relative paths from the code directory
- Mark it as "source of truth" for requirements

Why: "An LLM can only keep a subset of the codebase in its context at once. Being able to feed in relevant documentation lets it use APIs from other areas without reading the code first." - Simon Willison

State the working directory clearly up front and stick to it throughout.

## Keep docs in sync

- When you make changes, update all docs that reference them (README, comments)
- Keep things in sync - don't let docs drift from code

## Keep Spec/Plan in Sync with Implementation

**The Challenge:** Specs are written before implementation. Reality often reveals better approaches. If you only update code docs (README, TESTING.md), the spec/plan becomes outdated and misleads future work.

_I even aspire to be able to delete the codebase and start all over again from the new spec if needed, and have all the decisions along the way captured because so much is learned while implementing. And then I can even implement a few times just for learning before building the final version! That should be the bar for keeping the spec up to date._

**The Pattern:** Guide agents to update the spec document itself when implementation decisions differ from the original plan.

### In AGENTS.md, include guidance that:

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

- Make it explicit and unavoidable - use words like "CRITICAL" or "MUST"
- Provide a concrete example from this specific project if possible
- Keep it actionable - agents should know exactly what to do and when

