# Writing for AI Agents

## Assumptions about who's executing this plan

- Skilled developer but zero context on our codebase, toolset, or problem domain
- Document: which files to touch, what to build, how to test it, what success looks like
- Be explicit about testing approach - don't assume they know good test design

## For the AI coding agent reading this

- Don't micro-manage: tell it what to accomplish, not how to code it
- No bash commands or code snippets in the plan - the agent will determine implementation
- Trust the agent to figure out the details

## When the plan requires current documentation

- Use web search for: framework-specific APIs, installation steps, configuration options
- Include version numbers when known
- Suggest fetching docs locally if they'll be referenced heavily during execution

