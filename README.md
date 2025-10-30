A systematic workflow for moving from product idea to working software with AI coding agents as partners.

These are general prompts I use to create specific documents and instructions unique to individual initiatives. The resulting documents guide AI agents through the complete development lifecycle.

## How to Use

Example: "I want to build a chat app with extended thinking"

1. Write your product opportunity assessment (the "why" and high-level "what")
2. Use `@1-create-a-spec/` → AI creates detailed spec
3. Use `@2-create-a-plan/` → AI adds phased implementation plan
4. Use `@3-create-agent-instructions/` → AI creates/updates AGENTS.md
5. Execute with agent using spec + AGENTS.md + plan as guides

## Acknowledgements

I got tons of inspiration from [Jesse Vincent](https://github.com/obra), especially [this blog post](https://blog.fsck.com/2025/10/05/how-im-using-coding-agents-in-september-2025/) and this [repository](https://github.com/obra/superpowers).