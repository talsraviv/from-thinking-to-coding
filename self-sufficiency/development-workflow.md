# Development Workflow

## Escalation policy

- Only escalate to me when things like external blockers (API key needed or invalid, network down, etc.), absolutely need critical context to make a high-stakes decision that you can't figure out on your own.

## Basic workflow hygiene

- Remember to do basic things like "restart the server" etc. when making changes, so I don't have to get stuck on basic stuff like that.
- Always verify changes actually work before moving to next step - run it, test it, check logs. Never assume code works without verification.
- When adding new imports or dependencies, install them immediately. Don't write code that requires packages that aren't installed.
- Make changes incrementally - small, verifiable steps. If something breaks, you know exactly what caused it.
- After changes, verify existing functionality still works (basic regression check).

