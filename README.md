A systematic workflow for moving from product idea to working software with AI coding agents.

## How It Works

1. Write your product opportunity assessment (the "why" and high-level "what")
2. Use `@1-create-a-spec/` → AI creates detailed technical spec
3. Use `@2-create-a-plan/` → AI adds phased implementation plan
4. Use `@3-create-agent-instructions/` → AI creates/updates AGENTS.md
5. Execute with your AI agent using the spec + plan + AGENTS.md

## What's Inside

- [1-create-a-spec/](1-create-a-spec/) - Turn opportunity into technical specification
- [2-create-a-plan/](2-create-a-plan/) - Convert spec into phased implementation plan
- [3-create-agent-instructions/](3-create-agent-instructions/) - Create project-specific AGENTS.md
- [self-sufficiency/](self-sufficiency/) - Reusable guidelines for agent autonomy
- [style-guide.md](style-guide.md) - Writing style guide

## Usage Note

When referencing these in your AI prompts, use `@` notation: `@1-create-a-spec/`, `@self-sufficiency/`, `@style-guide.md`

