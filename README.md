This is how I move from using coding agents as a [product thinking partner](https://talraviv.co/put-llms-to-work/using-cursor-plain-english/intro-to-cursor) to building a "working proof of concept" (i.e. more than a shallow prototype, less than production code) with an AI coding agent.

_TLDR: These are prompts I use to create a spec, plan, and agents file, and then I just have to say "let's execute."_

## Getting Started

If you're already using an AI coding agent (like Cursor, Claude Code, or similar) as a product thinking partner, here's a [video walkthrough](https://talraviv.co/put-llms-to-work/product-thinking-to-prototyping#and-so-can-you) of how to turn your thoughts into functional prototypes. The steps are also written out below. 

<a target="_blank" href="https://talraviv.co/put-llms-to-work/product-thinking-to-prototyping#and-so-can-you"><img width="742" height="481" alt="video thumbnail" src="https://github.com/user-attachments/assets/98ee291d-b9e1-48c8-8c90-350d53123669" /></a>

_The UI library in the video is [Wired Elements](https://github.com/rough-stuff/wired-elements)._

#### Option 1: Clone into your existing setup

Tell your AI coding agent:
```
Let's clone 

https://github.com/talsraviv/from-thinking-to-coding 

into a new top-level directory in this project called "Prototyping prompts"
```

#### Option 2: Download and drag
Download the zip file from GitHub and drag the `from thinking to coding` directory into your existing AI copilot directory. Your AI agent will then be able to reference these templates using `@from thinking to coding/`.

Once integrated, the AI can see and use these templates when you reference them with `@` mentions in your conversations.

## How to Use

### 1. Write your product opportunity assessment (before using these prompts)

Draft a document covering the "why" and high-level "what" - the product opportunity, user needs, success criteria, and what you're building.

If you really wanna wing it, just dictate what you're thinking about building and why into your AI coding agent chat box.

"I want to build a children's science museum version of ChatGPT demonstrating visibly how extended thinking works."

If you want to build a learning POC, you might [start with a deep research](https://talraviv.co/from-using-to-building/how-i-built-chatgpt-from-scratch) on the topic you want to prototype.

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
