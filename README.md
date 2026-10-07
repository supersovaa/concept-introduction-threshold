# Concept Introduction Threshold

A lightweight skill for deciding when a new named concept earns a place in an implementation.

## Core idea

A new concept should directly represent established meaning or materially simplify the implementation.

Treat structural similarity as a signal to look for shared processing.
Establish a shared concept when the uses also share meaning or when the concept produces a clear simplification across the affected implementation.

## Responsibility

`concept-introduction-threshold` owns the threshold for introducing named abstractions and implementation concepts.

It evaluates wrappers, shared models, contexts, policies, constraints, traits, intermediate representations, and similar concepts by the meaning or simplification they provide.

## Adjacent responsibilities

`prefer-static-decisions` owns whether known facts and choices should remain static rather than becoming runtime decisions.

Domain-specific skills and repository sources of truth own the meanings that the implementation must preserve.

Executable behavior and detailed operational rules remain in `SKILL.md`.
