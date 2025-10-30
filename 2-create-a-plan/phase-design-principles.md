# Phase Design Principles

## Principles of a great plan

- Start by verifying what exists works and is a good foundation
- Close a working loop of value fast - "something simple working soon"
- Steps should be modular, elegant, minimal, and integrate seamlessly within the existing codebase.
- Start with isolated tasks: boilerplate, hello world, simple components before bigger functionality
- Each phase must be stoppable: I can stop the agent and run working software with that phase's changes
- Design for easy manual QA: make it very clear and fast for me to test - spell out exact steps
- Be hyper-specific about what to build, not how to build it
  - Good: "Create login API with JWT authentication, bcrypt password hashing, email/password validation"
  - Bad: "Implement authentication" or detailed code snippets
- End each phase with software fully running: restart servers, verify latest changes work, etc.
- No extra complexity or extra scope beyond what we discussed. The plan should lead to simple, elegant, minimal code that does the job perfectly.

