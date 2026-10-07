# Concept Introduction Threshold

A lightweight skill for deciding when a named concept earns a place in an implementation.

## Core idea

A concept should directly represent established meaning or materially simplify the implementation.

Treat structural similarity as a signal to look for shared processing.
Establish a shared concept when the uses also share meaning or when the concept produces a clear simplification across the affected implementation.

## Responsibility

`concept-introduction-threshold` owns the threshold for introducing or retaining named abstractions and implementation concepts in affected work.

It evaluates wrappers, shared models, contexts, policies, constraints, traits, intermediate representations, and similar concepts by the meaning or simplification they provide.

## Adjacent responsibilities

`prefer-static-decisions` owns the placement of known facts and choices into static or runtime representations.

Domain-specific skills and repository sources of truth own the meanings that the implementation must preserve.

Executable behavior and detailed operational rules remain in `SKILL.md`.
