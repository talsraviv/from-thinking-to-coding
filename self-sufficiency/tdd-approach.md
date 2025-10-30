# TDD Approach

Use TDD because it's ideal for AI coding agents to check their own work quickly without manual human feedback.

## The Iron Law

**NO PRODUCTION CODE WITHOUT A FAILING TEST FIRST**

Write code before the test? Delete it. Start over.

**No exceptions:**
- Don't keep it as "reference"
- Don't "adapt" it while writing tests
- Delete means delete

Violating the letter of this rule is violating the spirit.

## Red-Green-Refactor

**RED - Write Failing Test**
- Write one minimal test showing what should happen
- One behavior, clear name, real code (no mocks unless unavoidable)

**Verify RED - Watch It Fail**
- MANDATORY. Never skip.
- Run the test, confirm it fails (not errors)
- Test passes? You're testing existing behavior. Fix test.

**GREEN - Minimal Code**
- Write simplest code to pass the test
- Just enough to pass, no extra features

**Verify GREEN - Watch It Pass**
- MANDATORY. Run test, confirm it passes
- Confirm other tests still pass
- Test fails? Fix code, not test.

**REFACTOR - Clean Up**
- Only after green: remove duplication, improve names
- Keep tests green, don't add behavior

## Why Order Matters

**"I'll write tests after to verify it works"**
Tests written after pass immediately. Passing immediately proves nothing - might test wrong thing, might miss edge cases, you never saw it catch the bug.

Test-first forces you to see the test fail, proving it actually tests something.

**"Tests after achieve same goals"**
No. Tests-after answer "What does this do?" Tests-first answer "What should this do?"

Tests-after are biased by your implementation. You test what you built, not what's required.

**"Deleting X hours of work is wasteful"**
Sunk cost fallacy. The time is gone. Your choice: delete and rewrite with TDD (high confidence) or keep it and add tests after (low confidence, likely bugs).

The waste is keeping code you can't trust.

## Best Practices for AI Agents

- Do not delete or modify tests to make them "pass" - tests define the contract, implementation must change
- Commit tests separately before implementation as a safeguard
- Each test must be completely independent
- Do not use fixed timeouts - use proper awaits
- Make everything testable directly by you as an agent

## Why TDD Works for Agents

As Simon Willison writes: "If your project has a robust, comprehensive and stable test suite agentic coding tools can fly with it. Without tests? Your agent might claim something works without having actually tested it at all, plus any new change could break an unrelated feature without you realizing it. Test-first development is particularly effective with agents that can iterate in a loop."

## Red Flags

- Code before test
- Test after implementation
- Test passes immediately
- "I already manually tested it"
- "Tests after achieve the same purpose"
- "This is different because..."

**All mean: Delete code. Start over with TDD.**

## Common Rationalizations

| Excuse | Reality |
|--------|---------|
| "Too simple to test" | Simple code breaks. Test takes 30 seconds. |
| "I'll test after" | Tests passing immediately prove nothing. |
| "Already manually tested" | Ad-hoc ≠ systematic. No record, can't re-run. |
| "Deleting X hours is wasteful" | Sunk cost fallacy. Keeping unverified code is debt. |
| "TDD will slow me down" | TDD faster than debugging later. |

