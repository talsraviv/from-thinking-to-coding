# Defense-in-Depth Validation

## Core Principle

When you fix a bug caused by invalid data, adding validation at one place feels sufficient. But that single check can be bypassed by different code paths, refactoring, or mocks.

**Validate at every layer data passes through. Make the bug structurally impossible.**

## Why Multiple Layers

Single validation: "We fixed the bug"
Multiple layers: "We made the bug impossible"

Different layers catch different cases:
- Entry validation catches most bugs
- Business logic catches edge cases
- Environment guards prevent context-specific dangers
- Debug logging helps when other layers fail

## The Four Layers

### Layer 1: Entry Point Validation
Reject obviously invalid input at API boundary.

```typescript
function createProject(name: string, workingDirectory: string) {
  if (!workingDirectory?.trim()) {
    throw new Error('workingDirectory cannot be empty');
  }
  if (!existsSync(workingDirectory)) {
    throw new Error(`workingDirectory does not exist: ${workingDirectory}`);
  }
  // proceed
}
```

### Layer 2: Business Logic Validation
Ensure data makes sense for this operation.

```typescript
function initializeWorkspace(projectDir: string) {
  if (!projectDir) {
    throw new Error('projectDir required for workspace initialization');
  }
  // proceed
}
```

### Layer 3: Environment Guards
Prevent dangerous operations in specific contexts.

```typescript
async function gitInit(directory: string) {
  // In tests, refuse git init outside temp directories
  if (process.env.NODE_ENV === 'test') {
    const normalized = normalize(resolve(directory));
    const tmpDir = normalize(resolve(tmpdir()));
    
    if (!normalized.startsWith(tmpDir)) {
      throw new Error(`Refusing git init outside temp dir during tests: ${directory}`);
    }
  }
  // proceed
}
```

### Layer 4: Debug Instrumentation
Capture context for forensics.

```typescript
async function gitInit(directory: string) {
  logger.debug('About to git init', {
    directory,
    cwd: process.cwd(),
    stack: new Error().stack
  });
  // proceed
}
```

## Applying the Pattern

When you find a bug:

1. **Trace the data flow** - where does bad value originate? Where used?
2. **Map all checkpoints** - list every point data passes through
3. **Add validation at each layer** - entry, business, environment, debug
4. **Test each layer** - try to bypass layer 1, verify layer 2 catches it

## Key Insight

All four layers are necessary. Each catches bugs the others miss:
- Different code paths bypass entry validation
- Mocks bypass business logic checks
- Edge cases need environment guards
- Debug logging identifies structural misuse

Don't stop at one validation point. Add checks at every layer.

