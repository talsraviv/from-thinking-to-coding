# Progress Tracking

## Track Progress in README.md

Keep README.md current with a "Current Status" section at the top:
- What phases are complete
- What works right now (brief, actionable)
- What's next (next phase number/name)
- Quick test command to try current features

Example:
```markdown
## Current Status

**Phases 0-5 Complete** — Working feature X!

**What works right now:**
- Feature A
- Feature B

**Try it:** `npm run dev` → Do X → See Y happen!

**Next:** Phase 6 — Feature Name
```

This gives new agents instant context without reading the entire codebase.

Update this section after each phase completion. Keep it concise.

## Getting Started Section for New Agents

**Remember: Each new session starts with a blank slate.**

AGENTS.md should be self-sufficient to onboard a new agent. Include a "Getting Started" section that tells new agents exactly what to read and in what order:

```markdown
## Getting Started

### For New AI Agent

**First, read these files in order:**
1. **README.md** — Current status, what's built, what's next
2. This AGENTS.md file — Map, purpose, and how to work here
3. `../path/to/spec.md` — Full spec and implementation plan
4. TESTING.md — How to test each feature

**Then:**
1. Run the app to verify everything works
2. Test the current features (see README.md)
3. Continue with the next phase from implementation plan
4. Update docs as you go (see Continuous Documentation section)
5. Commit after completing each phase
```

This provides a clear onboarding path for context window handoffs.

The key insight: agents know nothing at the start of each session. AGENTS.md is their only persistent memory. Make it count.

## Phase Completion Workflow

See `wrap-up-protocol.md` for comprehensive guidance on how agents should wrap up phases and tasks, including the memory sweep step to capture learnings.
