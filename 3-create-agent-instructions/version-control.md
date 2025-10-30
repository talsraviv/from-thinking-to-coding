# Version Control

- After completing meaningful progress, propose a commit message and wait for user confirmation
- Show the proposed commit message in a code block for easy review
- Only commit after user approves (they may want to modify it first)
- Commit message format: `type: description` with bullet points of key changes
- Branch strategy: `feature/description` or `fix/description` - never commit directly to main
- Never commit: API keys, node_modules, built artifacts, IDE settings, agent instruction files
- Always commit: .env.example (not .env), dependency files (package.json, requirements.txt)

