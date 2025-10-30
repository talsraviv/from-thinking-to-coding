# Discipline Patterns for Agents

## Core Principle

Agents are smart and will find loopholes under pressure. Documentation must explicitly close rationalizations.

## The Foundation

**Violating the letter of the rules is violating the spirit of the rules.**

This cuts off entire class of "I'm following the spirit" rationalizations.

## Pattern: Iron Laws

Frame critical rules as non-negotiable:

```
NO PRODUCTION CODE WITHOUT FAILING TEST FIRST
NO FIXES WITHOUT ROOT CAUSE INVESTIGATION FIRST
NO COMPLETION CLAIMS WITHOUT VERIFICATION EVIDENCE
```

These are absolute. Not guidelines. Not suggestions.

## Pattern: Explicit Exception Closing

Don't just state the rule - forbid specific workarounds:

**Bad:**
"Write code before test? Delete it."

**Good:**
"Write code before test? Delete it. Start over.

No exceptions:
- Don't keep it as 'reference'
- Don't 'adapt' it while writing tests
- Don't look at it
- Delete means delete"

## Pattern: Rationalization Tables

Build tables from common excuses:

| Excuse | Reality |
|--------|---------|
| "Too simple to test" | Simple code breaks. Test takes 30 seconds. |
| "I'll test after" | Tests passing immediately prove nothing. |
| "Already manually tested" | Ad-hoc ≠ systematic. No record, can't re-run. |

## Pattern: Red Flags Lists

Make it easy for agents to self-check when rationalizing:

**Red Flags - STOP:**
- Code before test
- "I already manually tested it"
- "Tests after achieve same purpose"
- "This is different because..."

**All mean: Delete code. Start over.**

## Pattern: "Why This Matters" Sections

Explain the reasoning:

**"I'll write tests after to verify it works"**
Tests written after pass immediately. Passing immediately proves nothing - might test wrong thing, might miss edge cases.

Test-first forces you to see the test fail, proving it actually tests something.

## When to Apply

Use these patterns for:
- Critical workflow rules (TDD, verification, debugging)
- Safety-critical operations (destructive commands, data loss risks)
- Common failure modes you've observed

Don't overuse - save for truly important disciplines.

