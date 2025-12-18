# Plan Structure

## This doc is about the order of operations

- What phases, in what order, to maximize speed and minimize frustration?
- Don't duplicate the spec - just reference it (the AI agent will read both)
- Focus on what's truly essential - ruthlessly cut everything else
- Be explicit: build on existing code or start fresh? What to preserve?
- Each phase should close a feedback loop: something working you can see/test

## No exploration steps in the plan

Do all research before creating the plan. The plan itself should contain only implementation steps.

Do not include steps like "grep for X" or "consult docs" - perform all file searches, web searches, and research required to craft a precise plan upfront.

## Expected plan structure

- Flag open questions at the TOP of the plan
- Task checklist at the top, organized by phase with checkboxes (☐/☑)
- Phase 0: Prerequisites & Setup (verify environment, install dependencies, confirm existing code works)
- Phase 1-N: Each phase builds something working and testable
- For each phase specify:
  - Affected files: list files to create/modify with a concise summary of changes per file
  - Goal: what we're building and why it matters
  - Done means: specific, observable success criteria
  - Test it: exact steps to verify it works (manual QA instructions)

## Task checklist format

At the top of the plan, include a task checklist organized by phase:

```
## Tasks

### Phase 1: [Name]
☐ Task description (concise, specific one-liner)
☐ Another task

### Phase 2: [Name]
☐ Task description
```

Mark tasks complete as you implement: ☐ → ☑

## Affected files summary

Start each phase with a summary of affected files:

```
**Affected Files:**
- `src/auth/login.ts` - add JWT validation
- `src/config/auth.ts` (new) - authentication configuration
```

## Task granularity

Describe specific changes concisely. Trust the agent to determine implementation details - no code snippets in the plan.

Each task should have:
- **Exact file paths** - not "the config file" but "src/config/database.ts"
- **Clear description of changes** - what to add, modify, or remove
- **Exact commands to run** - "Run: npm test src/auth.test.ts -v"
- **Expected output** - "Expected: PASS with 'user authenticated'"

## Design decisions

For system design quality principles, important to incorporate @engineering-principles/

For agent self-sufficiency patterns, important to incorporate @self-sufficiency/

## Remember

@engineering-principles/ (DRY, YAGNI). @self-sufficiency/ (TDD). Frequent commits.
