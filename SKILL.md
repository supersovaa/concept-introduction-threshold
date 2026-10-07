---
name: concept-introduction-threshold
description: Evaluate named abstractions and implementation concepts by requiring them to represent established meaning or materially simplify the implementation. Use during refactoring and when adding or reviewing wrappers, shared enums or structs, contexts, policies, constraints, traits, intermediate models, or similar abstractions.
---

# Concept Introduction Threshold

Use a concept when it earns its place through meaning or simplification.

## Core rule

Every named concept in the affected implementation must either directly represent an established meaning or materially simplify the implementation.

Treat similar code shape as a signal to examine shared processing.
Establish a shared concept when the participating uses also share meaning or when the concept produces a clear simplification across the affected implementation.

Established meaning exists independently of the implementation concept.
Ground it in domain rules, requirements, design sources, public API meaning, or actual use cases that already distinguish it.

## Evaluate the concept

During refactoring, evaluate the named concepts in the affected implementation path, including concepts that remain in place.

For each concept:

1. Identify the independent source of established meaning it represents.
2. Identify the concrete simplification it provides.
3. Compare the whole affected path using the concept with the most direct concrete alternative.
4. Compare wrappers, shared representations, and intermediate models with an alternative that keeps the original concrete distinctions and shares only the common mechanism.
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

When a shared representation requires `kind`, flags, policies, contexts, repeated matching, or similar information to recover distinctions already carried by the original inputs, use the original concrete distinctions as the comparison baseline and evaluate sharing only the common mechanism.

## Evaluate through actual uses

Use the real use cases as the primary evidence that a shared concept preserves the required meanings.

Judge the concept by whether the affected uses remain direct to express and understand after the shared mechanism is introduced.
Let the repository's testing workflow own test selection and implementation.

## Complete the evaluation

Complete this skill after the named implementation concepts in the affected path have been evaluated against the threshold.

## Responsibility boundary

This skill owns the threshold for introducing or retaining a named implementation concept in affected work.

Domain rules and repository sources of truth own domain meaning.
`prefer-static-decisions` owns the placement of known facts and choices into static or runtime representations.
