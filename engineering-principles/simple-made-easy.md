# Simple Made Easy

Adapted from Rich Hickey's "Simple Made Easy" principles, as originally summarized in https://www.zo.computer/prompts/plan-code-changes

## Core Principle

Choose SIMPLE over EASY. Strive for un-braided, composable designs that minimize incidental complexity.

## The Seven Principles

### 1. Detect Complecting

Whenever you join concerns (state & time, data & behavior, configuration & code) pause and seek an alternative that keeps them independent.

Favor composition (placing things side-by-side) over interleaving.

### 2. Prefer Values, Resist State

Immutable data is the default.

Mutable state must be narrowly scoped, well-named, and justified.

### 3. Assess Constructs by Their Artifacts

Judge a tool, abstraction, or pattern by the long-term properties of the running system it produces: clarity, changeability, and robustness.

"Easy to start" is not sufficient.

### 4. Declarative over Imperative

Describe WHAT, not HOW.

Lean on data, configuration, queries, and rule systems where possible.

### 5. Polymorphism à la Carte

Separate data definitions, behavior specifications, and their connections.

Avoid inheritance hierarchies that entangle unrelated facets.

### 6. Guard-rails Are Not Simplicity

Tests, static checks, and refactors are valuable, but cannot compensate for a complex design.

Seek to remove complexity first.

### 7. Vigilance and Sensibility

Continuously ask: "Is this simple? Could these parts remain independent?"

Be willing to trade immediate ease for lasting simplicity.

## Success Criteria

A reader unfamiliar with the code should be able to locate, understand, and replace a part without untangling others.

## Decision Metric

Measure decisions by how much braid they remove, not how quickly they compile.

