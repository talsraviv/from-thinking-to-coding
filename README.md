This is how I move from using coding agents as a [product thinking partner](https://talraviv.co/put-llms-to-work/using-cursor-plain-english/intro-to-cursor) to building a "working proof of concept" (i.e. more than a shallow prototype, less than production code) with an AI coding agent.

_TLDR: These are prompts I use to create a spec, plan, and agents file, and then I just have to say "let's execute."_

## Getting Started

If you're already using an AI coding agent (like Cursor, Claude Code, or similar) as a product thinking partner, here's a [video walkthrough](https://talraviv.co/put-llms-to-work/product-thinking-to-prototyping#and-so-can-you) of how to turn your thoughts into functional prototypes. The steps are also written out below. 

<a target="_blank" href="https://talraviv.co/put-llms-to-work/product-thinking-to-prototyping#and-so-can-you"><img width="742" height="481" alt="video thumbnail" src="https://github.com/user-attachments/assets/98ee291d-b9e1-48c8-8c90-350d53123669" /></a>

_The UI library in the video is [Wired Elements](https://github.com/rough-stuff/wired-elements) and the font is [Gloria Hallelujah](https://fonts.google.com/specimen/Gloria+Hallelujah)._

#### Option 1: Have your AI coding agent copy these prompts into your project directory

Create a fresh new directory for your prototype, and open it in your AI coding agent (or change into it).

Tell your AI coding agent:
```
Let's clone 

https://github.com/talsraviv/from-thinking-to-coding 

into a new top-level directory in this project called "from thinking to coding/"
```

#### Option 2: Download the prompts as a ZIP and drag it into your project directory

Download the zip file from GitHub and drag the `from thinking to coding` directory into your existing AI copilot directory. Your AI agent will then be able to reference these templates using `@from thinking to coding/`.

Once integrated, the AI can see and use these templates when you reference them with `@` mentions in your conversations.

## How to Use

### 1. Write your product opportunity assessment (before using these prompts)

Draft a document covering the "why" and high-level "what" - the product opportunity, user needs, success criteria, and what you're building.

I love having my AI coding agent guide me conversationally, pulling the context out of me. I'll create a new file called `opportunity assessment.md` and copy my personal favorite headings in there:

```
# Objective

# Target customer

# Success

# What I believe

# What I need to research

# Solution directions

# Risks to validate + how to validate them cheaply/quickly
```

Then I'll ask the AI coding agent to interview me:

```
I want your help in filling out `@opportunity assessment.md` I want you to converse with me and ask me questions one by one to help fill this out. Let's keep those sections as is and fit into them. 

Think about what's missing, interview me, and pull insights and ideas out of me, and brainstorm with me. 

Let's converse just enough to make a great lightweight doc from our collaboration. Wait on writing the doc until our conversation is done. 

To write the doc, keep it succinct and readable (no filler) but make sure to capture all the gold. Use our original conversation words for the vivid/evocative stuff.
```

If you really wanna wing it, just dictate what you're thinking about building and why into your AI coding agent chat box, e.g.
`I want to build a children's science museum version of ChatGPT demonstrating visibly how extended thinking works.`

> Pro tip: If you want to build a learning POC, you might [start with a deep research](https://talraviv.co/from-using-to-building/how-i-built-chatgpt-from-scratch) on the topic you want to prototype and include it at the start of the conversation.

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

- I got tons of inspiration from [Jesse Vincent](https://github.com/obra), especially [this blog post on using coding agents in general](https://blog.fsck.com/2025/10/05/how-im-using-coding-agents-in-september-2025/) this [blog post on self-sufficiency](https://blog.fsck.com/2025/12/02/helping-agents-debug-webapps/) and this [repository](https://github.com/obra/superpowers).
- I absolutely loved [humanlayer's "Writing a good Claude.md" post](https://www.humanlayer.dev/blog/writing-a-good-claude-md) and incorporated insights into this repo.
- It was very cool to see these insights cohere with [Anthropic's experience applying the Claude Agent SDK](https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents)
- Ben Guo from [Zo Computer](https://www.zo.computer) for the ["Plan code changes" prompt](https://www.zo.computer/prompts/plan-code-changes) and his [Velocity Coding lightning lesson](https://maven.com/p/e6c660/velocity-coding-building-at-the-speed-of-thought) on Maven.
