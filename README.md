A systematic workflow for moving from product idea to working software with an AI coding a agents as partner.

These are general prompts I use to create specific documents and instructions unique to individual initiatives. The resulting documents guide AI agents through the complete development lifecycle.

## Getting Started

If you're already using an AI coding agent (like Cursor, Claude Code, or similar) as a [product thinking partner](https://talraviv.co/put-llms-to-work/using-cursor-plain-english/intro-to-cursor), here's how to integrate this workflow:

**Option 1: Clone into your existing setup**

Tell your AI coding agent:
```
Let's clone [insert URL of this repo above] into this directory.
```

**Option 2: Download and drag**
Download the zip file from GitHub and drag the `from thinking to coding` directory into your existing AI copilot directory. Your AI agent will then be able to reference these templates using `@from thinking to coding/`.

Once integrated, the AI can see and use these templates when you reference them with `@` mentions in your conversations.

## How to Use

Example: "I want to build a children's science museum version of ChatGPT demonstrating visibly how extended thinking works."

### 1. Write your product opportunity assessment (before using these prompts)

Draft a document covering the "why" and high-level "what" - the product opportunity, user needs, success criteria, and what you're building.

### 2. Use an AI coding agent to turn it into a detailed technical specification

```
Let's @1-create-a-spec/ for @opportunity assessment.md
```

The AI will generate a detailed technical specification as a new section inside the original document.

### 3. Create a phased implementation plan

Continue in the same thread:

```
Now let's @2-create-a-plan/
```

The AI will add a phased implementation plan to your document.

### 4. Generate AGENTS.md for your code project

Continue in the same thread:

```
Let's @3-create-agent-instructions/
```

The AI will create or update an AGENTS.md file in your code project directory with development guidelines.

### 5. Execute with your AI coding agent

Use the spec, plan, and AGENTS.md as guides while building. Reference them as needed during development.

Continue in the same thread:

```
Let's execute the plan!
```

## Acknowledgements

I got tons of inspiration from [Jesse Vincent](https://github.com/obra), especially [this blog post](https://blog.fsck.com/2025/10/05/how-im-using-coding-agents-in-september-2025/) and this [repository](https://github.com/obra/superpowers).