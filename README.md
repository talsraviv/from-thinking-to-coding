This directory contains a systematic workflow for moving from product idea to working software with AI coding agents as partners.

These are general prompts that I use to create specific documents and instructions unique to individual initiatives.

After running these prompts, the resulting documents and instructions guide AI agents through the complete development lifecycle, ensuring consistent quality, self-sufficiency, and clear documentation at each stage.

## Quick Start

**Example**: "I want to build a chat app with extended thinking"

1. Write opportunity assessment (your job - the "why" and high-level "what")
2. Use `@1-create-a-spec/` → AI creates detailed spec in your assessment doc  
3. Use `@2-create-a-plan/` → AI adds phased implementation plan
4. Use `@3-create-agent-instructions/` → AI creates/updates AGENTS.md
5. Execute with agent using spec + AGENTS.md + plan as guides

## Workflow Order

Once I have decided to execute on an initiative, I use these prompts sequentially:

0. Product discovery, strategy, research, and prioritization (I do before applying these)
1. **Product opportunity assessment** (I create this on my own - starting context for everything else)
2. **[@1-create-a-spec/](1-create-a-spec/)** - Turn opportunity into detailed technical specification
3. **[@2-create-a-plan/](2-create-a-plan/)** - Convert spec into phased implementation plan
4. **[@3-create-agent-instructions/](3-create-agent-instructions/)** - Create/update AGENTS.md for project-specific guidance

## Shared Modules

- **[@self-sufficiency/](self-sufficiency/)** - Reusable guidelines for agent autonomy (referenced by other prompts)
- **[@style-guide.md](style-guide.md)** - Central writing style guide (referenced by all prompts)

## File Structure

Each prompt is organized as a directory with:
- **README.md** - Overview, purpose, and usage context
- **Component files** - Modular content addressing specific concerns
- **Clean markdown** - Succinct, scannable, no fluff

## Cross-Reference Notation

When referencing shared content, use `@` notation:
- `@self-sufficiency/` - References all files in self-sufficiency module
- `@style-guide.md` - References the central style guide
- `@1-create-a-spec/` - References the create-a-spec prompt directory

## Usage

When starting a new initiative:
1. Start with your product opportunity assessment
2. Use `@1-create-a-spec/` to create the technical spec
3. Use `@2-create-a-plan/` to create the implementation plan
4. Use `@3-create-agent-instructions/` to create project-specific AGENTS.md
5. Execute the plan with an AI coding agent using the spec and AGENTS.md as guides


## Editing Guidelines

- Keep content **succinct and scannable**
- Use original wording when possible 
- Maintain **separation of concerns** between files
- Update cross-references if moving content between files

