# What AGENTS.md IS

## First Principle: Agents Are Stateless

LLMs know nothing about your codebase at the start of each session. AGENTS.md is the only file automatically loaded every conversation — this makes it persistent memory across sessions.

**Your job isn't just to read AGENTS.md. It's to cultivate it.**

Update it whenever you learn something a future agent needs to know.

## AGENTS.md Should Cover: WHAT, WHY, HOW

### WHAT: Give agents a map of the codebase

- Project structure — what's where
- Purpose of each major directory
- Key files and entry points
- For monorepos: what each app does, what shared packages provide

See `codebase-map.md` for detailed guidance.

### WHY: Explain the purpose

- What this project does
- What each major component is for
- Key architectural decisions and their rationale

### HOW: Timeless guidance on working here

- Framework-specific gotchas and patterns
- Development workflow and conventions
- Commands to run, verify, test
- Key lessons learned (technical insights that apply going forward)

## What AGENTS.md is NOT

- **Current project status** — that goes in README.md
- **Product and implementation plan** — that lives in the spec and plan
- **Detailed testing procedures** — that goes in TESTING.md
- **Exhaustive command references** — too much bloat leads to sub-optimal results

Keep it focused. AGENTS.md is loaded every session — make it count.

## Keep Docs Minimal

Consolidate when possible. Three files usually suffice:
1. README.md — status and how to run
2. AGENTS.md — map, purpose, and how to work
3. TESTING.md — manual QA procedures

Avoid creating redundant status-tracking files.
