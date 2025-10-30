# Plan Structure

## This doc is about the order of operations

- What phases, in what order, to maximize speed and minimize frustration?
- Don't duplicate the spec - just reference it (the AI agent will read both)
- Focus on what's truly essential - ruthlessly cut everything else
- Be explicit: build on existing code or start fresh? What to preserve?
- Each phase should close a feedback loop: something working you can see/test

## Expected plan structure

- Phase 0: Prerequisites & Setup (verify environment, install dependencies, confirm existing code works)
- Phase 1-N: Each phase builds something working and testable
- For each phase specify:
  - Goal: what we're building and why it matters
  - Files: which files to create/modify (exact paths)
  - Done means: specific, observable success criteria
  - Test it: exact steps to verify it works (manual QA instructions)

## Task Granularity

Break phases into bite-sized tasks (2-5 minutes each):
- "Write the failing test" - one task
- "Run it to make sure it fails" - one task
- "Implement minimal code to pass" - one task
- "Run tests and verify they pass" - one task
- "Commit" - one task

Each task should have:
- **Exact file paths** - not "the config file" but "src/config/database.ts"
- **Complete code examples** - not "add validation" but the actual validation code
- **Exact commands** - "Run: npm test src/auth.test.ts -v"
- **Expected output** - "Expected: PASS with 'user authenticated'"

## Remember

DRY. YAGNI. TDD. Frequent commits.

