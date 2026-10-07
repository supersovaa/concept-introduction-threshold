---
name: concept-introduction-threshold
description: Evaluate new named abstractions and implementation concepts by requiring them to represent established meaning or materially simplify the implementation. Use when adding or reviewing wrappers, shared enums or structs, contexts, policies, constraints, traits, intermediate models, or similar abstractions.
---

# Concept Introduction Threshold

Use a new concept when it earns its place through meaning or simplification.

## Core rule

Any new concept introduced into the implementation must either directly represent an established meaning or materially simplify the implementation.

Treat similar code shape as a signal to examine shared processing.
Establish a shared concept when the participating uses also share meaning or when the concept produces a clear simplification across the affected implementation.

## Evaluate the concept

Before introducing a named concept:

1. State the meaning or responsibility the concept represents.
2. Identify the concrete simplification it provides.
3. Compare the affected implementation before and after the concept.
4. Keep semantic distinctions available wherever later behavior depends on them.
5. Choose the narrowest representation that provides the identified value.

A concept can justify itself through either established meaning or implementation simplification.
Either condition is sufficient.

## Measure simplification across the whole path

Count the full affected path, including callers, conversions, helper types, branches, state, configuration, and supporting APIs.

Useful simplification can include:

- removing repeated logic or repeated decisions;
- flattening nested control flow;
- reducing state or coordination;
- expressing one invariant directly instead of reconstructing it in several places;
- making callers or public APIs simpler;
- reducing the number of concepts required to understand the behavior.

Base the decision on the whole-path comparison.

## Preserve meaningful distinctions

When several concrete types or use cases share processing while retaining different meanings, keep those meanings explicit and share the mechanism.

Generics, helper functions, traits, tables, or other language-appropriate mechanisms can share processing while preserving concrete distinctions.

When a shared representation requires `kind`, flags, policies, contexts, repeated matching, or similar information to recover distinctions already carried by the original inputs, compare that representation with keeping the distinctions explicit and sharing only the common mechanism.

## Validate through actual uses

Use the real use cases as the primary evidence that a shared concept preserves the required meanings.

Add focused tests for the shared mechanism when it has an independent contract.
Keep use-case tests responsible for the meaning that belongs to each use.

## Responsibility boundary

This skill owns the threshold for introducing a new implementation concept.

Domain rules and repository sources of truth own domain meaning.
`prefer-static-decisions` owns the placement of known facts and choices into static or runtime representations.
