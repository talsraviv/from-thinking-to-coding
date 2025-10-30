# Verification Before Completion

## The Iron Law

**NO COMPLETION CLAIMS WITHOUT FRESH VERIFICATION EVIDENCE**

If you haven't run the verification command in this message, you cannot claim it passes.

## The Gate Function

Before claiming any status or completion:

1. **Identify** - what command proves this claim?
2. **Run** - execute the full command, fresh and complete
3. **Read** - full output, check exit code, count failures
4. **Verify** - does output confirm the claim?
   - If NO: state actual status with evidence
   - If YES: state claim with evidence
5. **Only then** - make the claim

Skip any step = lying, not verifying.

## What requires verification

| Claim | Requires | Not Sufficient |
|-------|----------|----------------|
| Tests pass | Test command output: 0 failures | Previous run, "should pass" |
| Linter clean | Linter output: 0 errors | Partial check |
| Build succeeds | Build command: exit 0 | Linter passing |
| Bug fixed | Test original symptom: passes | Code changed |
| Phase complete | All objectives verified | Tests passing |

## Red Flags

Using "should", "probably", "seems to" before verification
- Expressing satisfaction before verification ("Great!", "Done!")
- About to commit/push without verification
- Relying on partial verification
- Any wording implying success without having run verification

## Patterns

**Tests:**
```
✅ [Run test] [See: 34/34 pass] "All tests pass"
❌ "Should pass now"
```

**Build:**
```
✅ [Run build] [See: exit 0] "Build passes"
❌ "Linter passed" (linter ≠ compiler)
```

**Requirements:**
```
✅ Re-read plan → checklist → verify each → report
❌ "Tests pass, phase complete"
```

## Common Rationalizations

| Excuse | Reality |
|--------|---------|
| "Should work now" | Run the verification |
| "I'm confident" | Confidence ≠ evidence |
| "Just this once" | No exceptions |
| "Partial check is enough" | Partial proves nothing |

## The Bottom Line

Run the command. Read the output. Then claim the result.

No shortcuts. Non-negotiable.

