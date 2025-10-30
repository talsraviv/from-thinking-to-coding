A systematic workflow for moving from product idea to working software with AI coding agents as partners.

These are general prompts I use to create specific documents and instructions unique to individual initiatives. The resulting documents guide AI agents through the complete development lifecycle.

## How to Use

Example: "I want to build a chat app with extended thinking"

1. Write your product opportunity assessment (the "why" and high-level "what")
2. Use `@1-create-a-spec/` → AI creates detailed spec
3. Use `@2-create-a-plan/` → AI adds phased implementation plan
4. Use `@3-create-agent-instructions/` → AI creates/updates AGENTS.md
5. Execute with agent using spec + AGENTS.md + plan as guides

## What's Inside

- [1-create-a-spec/](1-create-a-spec/) - Turn opportunity into detailed technical specification
- [2-create-a-plan/](2-create-a-plan/) - Convert spec into phased implementation plan
- [3-create-agent-instructions/](3-create-agent-instructions/) - Create project-specific AGENTS.md
- [self-sufficiency/](self-sufficiency/) - Reusable guidelines for agent autonomy
- [style-guide.md](style-guide.md) - Central writing style guide

## Cross-Reference Notation

When referencing shared content in your own projects, use `@` notation to attach directories or files in your AI chat.

