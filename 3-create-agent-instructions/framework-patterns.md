# Framework-Specific Critical Patterns

Identify and document CRITICAL workflow patterns specific to the framework/stack:
- Hot reload limitations (which files require full restart?)
- Permission requirements (what triggers OS permission prompts?)
- Build/deploy gotchas (signing, notarization, etc.)
- Development vs production differences

**Mark these as CRITICAL in the docs** - these cause the most frustration when missed.

Example for Electron:
```markdown
### Hot Reload Limitations (CRITICAL)
- Renderer (React): Hot reload works ✅
- Main process: Requires full restart ⚠️

After changing src/main/ files, immediately run:
killall Electron && sleep 2 && npm run dev
```

Make it actionable - tell agents exactly what command to run, not just "restart required."

