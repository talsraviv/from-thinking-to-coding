# Phase Wrap-Up Protocol

## Core Principle

Wrapping up properly is not optional - it ensures quality, maintains trust, and sets up success for the next phase. Apply this to phases, features, and fixes.

**Evidence before claims, always.**

## In AGENTS.md, establish that wrapping up includes:

### 1. Proactive Wrap-Up Initiation

**The agent should:**
- Recognize when work is complete and suggest wrapping up
- Don't wait for user to say "let's wrap up" - be proactive
- Use explicit language: "Let's wrap up Phase X" or "Ready to wrap up this fix"
- Signal clearly when a natural stopping point is reached

**Example phrasing to include:**
- "When you complete the phase objectives, proactively suggest: 'Phase X is complete. Let's wrap up - I'll verify everything is working and update all documentation.'"

### 2. Verification Checklist

**Before calling a phase complete, the agent must:**

Run verification commands and show output:
- Run tests: show "X/X pass" (not "tests should pass")
- Run linter: show "0 errors" (not "linter looks clean")
- Run build: show "exit 0" (not "build probably works")
- Test manually: follow TESTING.md steps, show actual results
- Code review: request review per code-review.md for major phases

Verify objectives:
- Read plan phase objectives line by line
- Check each objective off with evidence
- If any incomplete, state what remains

**Make this explicit in AGENTS.md:**
- List specific verification commands for this project
- Reference where testing procedures live (TESTING.md)
- State what "working" means (runs? compiles? passes tests?)
- Require showing command output, not claiming success

### 3. Documentation Updates

**The agent must update before completing:**
- **README.md Current Status** - what phase is complete, what works now, what's next
- **TESTING.md** - manual QA steps for new features added this phase
- **Spec/Plan** - if implementation differed from plan, update the source document
- **Code comments** - ensure new code is well-commented

**Common mistake to prevent:**
- Don't let agents say "documentation updated" without actually doing it
- Be specific about which files need updates and what sections

### 4. User Confirmation Required

**Critical rule - the agent must:**
- Walk user through testing steps clearly (not "test the feature" but "click X, you should see Y")
- Wait for explicit confirmation that tests passed
- Never proceed to next phase without user sign-off
- Offer to fix issues if user reports problems

**Red flag - agents saying:**
- "Everything should work now"
- "Phase complete, moving to Phase X"
- "Tests passed" (without showing output)

**Phrasing to include in AGENTS.md:**
"CRITICAL: Do not proceed to next phase until I confirm manual testing passed. After verification, ask: 'Please test [specific steps]. Once confirmed working, I'll commit and we can move to Phase X.'"

### 5. What to Remind the User

**The agent should prompt the user to:**
- Test the feature themselves (provide exact steps)
- Confirm everything works before moving on
- Decide if we're committing now or continuing
- Review if this is a good stopping point

**Style note:**
- Make testing steps concrete: "Try X, you should see Y"
- Offer to wait while user tests
- Ask "Is there anything else about this phase before we move on?"

### 6. Commit Readiness

**If committing at wrap-up, the agent should:**
- Suggest a clear commit message describing what was built
- Verify all changed files are included
- Check that no temporary/debug code remains
- Ensure commit message references phase number/name

**Make optional but suggested:**
- Some phases may not warrant commits
- User decides when to commit
- But always be "commit ready" at wrap-up

## Applies to All Work Levels

**Important:** This protocol isn't just for phases. Include guidance that wrap-up applies to:

- **Full phases** - comprehensive wrap-up with all steps
- **Individual features** - lighter wrap-up, still verify and document
- **Tiny fixes** - minimal but still verify it works and document if needed
- **Bug fixes** - verify the bug is fixed, update any relevant docs

**Scale the protocol to the work:**
- Big phases: full checklist
- Small tasks: abbreviated but still intentional
- Always: verify it works and signal completion clearly

## Style and Tone

**In AGENTS.MD, make this:**
- Explicit and unavoidable (use "MUST", "REQUIRED", "CRITICAL")
- Actionable with specific steps
- Friendly but firm about not skipping wrap-up
- Project-specific (reference actual file paths, testing commands)

**Example opening:**
"Before considering any phase or task complete, you MUST follow this wrap-up protocol..."

## Common Failure Modes to Prevent

Address these explicitly in AGENTS.md:

1. **Claiming success without evidence** - "tests should pass", "looks good"
   - Prevention: Require showing command output before claiming anything

2. **Rushing ahead** - jumping to next phase without wrap-up
   - Prevention: Make user confirmation required before proceeding

3. **Documentation drift** - updating code but not docs
   - Prevention: List exact files that must be updated

4. **Assumed success** - thinking it works without verification
   - Prevention: Require running/testing before calling complete

5. **Unclear completion** - user unsure if phase is done
   - Prevention: Use clear "Let's wrap up Phase X" language

6. **Partial wrap-up** - doing some steps but skipping others
   - Prevention: Provide numbered checklist in AGENTS.md

## Template Structure for AGENTS.md

Suggest organizing the wrap-up section like this:

```markdown
## Phase Wrap-Up Protocol

Every phase completion requires this protocol.

### Before saying a phase is complete:

1. **Run verification commands and show output:**
   - npm test → show "X/X pass"
   - npm run lint → show "0 errors"
   - npm run build → show "exit 0"
   - Code review → for major phases, request review (see code-review.md)

2. **Verify phase objectives:**
   - Read plan objectives line by line
   - Check each off with evidence
   - State if any incomplete

3. **Update documentation:**
   - README.md current status
   - TESTING.md if new features added
   - Spec/plan if implementation differed

4. **Proactively say: "Let's wrap up Phase X"**

5. **Walk me through testing:**
   - "Click X, you should see Y"
   - Not "test the feature"

6. **Wait for my confirmation**

7. **Offer to commit:** "[phase description]"

### Never proceed to next phase without my confirmation.

### Red flags - never say:
- "Should work now"
- "Tests passed" (without showing output)
- "Phase complete, moving to Phase X"
```

## Why This Matters

Explain in AGENTS.md why wrap-up protocol exists:
- Prevents building on broken foundations
- Maintains documentation accuracy
- Creates natural stopping points for context handoffs
- Ensures we can always return to a working state
- Makes each phase independently valuable

