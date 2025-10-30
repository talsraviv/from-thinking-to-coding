# Systematic Debugging

## The Iron Law

**NO FIXES WITHOUT ROOT CAUSE INVESTIGATION FIRST**

If you haven't completed root cause investigation, you cannot propose fixes.

## When to use

Use for any technical issue: test failures, bugs, unexpected behavior, performance problems, build failures.

**Especially when:**
- Under time pressure (emergencies make guessing tempting)
- "Just one quick fix" seems obvious
- You've already tried multiple fixes
- You don't fully understand the issue

**Never skip when:**
- Issue seems simple (simple bugs have root causes)
- You're in a hurry (systematic is faster than thrashing)
- Manager wants it NOW (systematic prevents rework)

## The Four Phases

Complete each phase before proceeding.

### Phase 1: Root Cause Investigation

**Before attempting any fix:**

1. **Read error messages carefully** - they often contain the exact solution
2. **Reproduce consistently** - can you trigger it reliably? If not, gather more data
3. **Check recent changes** - git diff, new dependencies, config changes
4. **Gather evidence in multi-component systems** - add diagnostic logging at each component boundary, run once, identify which layer fails
5. **Trace data flow** - where does bad value originate? Keep tracing up until you find the source

### Phase 2: Pattern Analysis

1. **Find working examples** - locate similar working code in same codebase
2. **Compare against references** - if implementing a pattern, read reference implementation completely
3. **Identify differences** - list every difference between working and broken
4. **Understand dependencies** - what other components, settings, environment does this need?

### Phase 3: Hypothesis Testing

1. **Form single hypothesis** - "I think X is the root cause because Y"
2. **Test minimally** - smallest possible change, one variable at a time
3. **Verify before continuing** - worked? Proceed. Didn't work? New hypothesis
4. **When you don't know** - say "I don't understand X", don't pretend

### Phase 4: Implementation

1. **Create failing test case** - simplest reproduction, automated if possible
2. **Implement single fix** - address root cause, one change at a time
3. **Verify fix** - test passes, no other tests broken, issue resolved
4. **If fix doesn't work** - count attempts. If ≥ 3 failures, STOP and question the architecture

## If 3+ fixes failed: Question Architecture

Pattern indicating architectural problem:
- Each fix reveals new shared state/coupling issue
- Fixes require massive refactoring
- Each fix creates new symptoms elsewhere

**STOP and question fundamentals:**
- Is this pattern sound?
- Are we sticking with it through inertia?
- Should we refactor architecture vs. fix symptoms?

Discuss with human partner before attempting more fixes.

## Red Flags

If you catch yourself thinking:
- "Quick fix for now, investigate later"
- "Just try changing X and see if it works"
- "Skip the test, I'll manually verify"
- "It's probably X, let me fix that"
- "I don't fully understand but this might work"
- "One more fix attempt" (when already tried 2+)

**All mean: STOP. Return to Phase 1.**

## Common Rationalizations

| Excuse | Reality |
|--------|---------|
| "Issue is simple, don't need process" | Simple issues have root causes. Process is fast. |
| "Emergency, no time for process" | Systematic is faster than thrashing. |
| "I see the problem, let me fix it" | Seeing symptoms ≠ understanding root cause. |
| "One more fix attempt" (after 2+) | 3+ failures = architectural problem. |

