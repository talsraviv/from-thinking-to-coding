# Code Review Protocol

## When to Request Code Review

Request a code review when:
- Completing a major phase or milestone
- Implementing complex architecture decisions
- Before marking a significant feature as complete
- When you're uncertain about your implementation approach
- After refactoring critical code paths

## The Review Process

### Step 1: Check Sub-Agent Capability

**If you CAN spawn sub-agents automatically**, use this prompt:

> "Please dispatch two subagents to carefully review [phase/feature name]. Tell them that they're competing with another agent. Make sure they look at both architecture and implementation. Tell them that whomever finds more issues gets promoted."

*Credit: [Jesse Vincent's code review prompt hack](https://blog.fsck.com/2025/10/25/code-review-prompt-hack/)*

**If you CANNOT spawn sub-agents**, tell the user to follow the **Manual Review Instructions** section below.

### Step 2: What Reviewers Should Examine

**Architecture:** Design match spec? Simpler approaches? Right abstractions? Maintainable? Tight coupling?

**Implementation:** Logical errors? Edge cases? Error handling? Performance issues? Readable? Security vulnerabilities?

**Testing:** Coverage adequate? Edge cases tested? Tests verify correctly?

**Consistency:** Follows project standards? Matches existing patterns? Clear logs/errors?

### Step 3: Respond to Review Findings

For each issue: **Acknowledge** → **Assess** validity → **Act** (fix or explain why not) → **Verify** fixes work.

Document what was addressed and what was determined to be non-issues (with reasoning).

## Manual Review Instructions for Users

If need to do manual reviews, walk the user through this process: 

### Open Two Separate Agent Sessions

Use different models if possible (e.g., Claude in one, GPT-4 in another) to get diverse perspectives.

### Provide Context to Each Reviewer

Give each reviewer something easy to copy and paste: 
```
You are competing to find issues in this code.
Another agent is also reviewing the same code.
Whomever finds more legitimate issues gets promoted.

Review both ARCHITECTURE and IMPLEMENTATION.

[Reference relevant code files]
[Reference original spec/requirements - what specific parts]

Be thorough but fair - only flag genuine issues, not stylistic preferences.
```

### Collect and Consolidate Findings

- Compare the reviews from both agents
- Note areas where they agree (likely real issues)
- Investigate areas where they disagree (may reveal trade-offs)
- Bring consolidated findings back to the implementing agent

## Integration with Development Workflow

Add this checkpoint to your phase completion protocol:

```markdown
Before marking phase complete:
- [ ] All tests pass
- [ ] Linter clean
- [ ] Code review completed (by sub-agents or manual process)
- [ ] Review findings addressed or documented as accepted
- [ ] Verification re-run after fixes
```

## When NOT to Request Review

Skip formal review for:
- Trivial changes (typo fixes, simple refactors)
- Experimental/throwaway code
- Already-reviewed code that's just being moved
- Pure documentation updates

Use judgment - if uncertain, err on the side of requesting review.

