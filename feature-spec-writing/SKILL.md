---
name: feature-spec-writing
description: Write or refine feature-facing documentation for TD, PM, and QA alignment. Use when the user needs a feature spec that defines goals, non-goals, usage context, expected behavior, failure scenarios, known issues, or open questions for a feature being built, clarified, or backfilled from existing work. Do not use for internal technical flow documentation, architecture-only design, generic release notes, or pure editorial cleanup.
---

# Feature Spec Writing

Write a feature-facing document that clarifies what a feature is meant to do, what it intentionally does not do, how it is expected to be used, what behavior should happen, what failures matter, and what is still unresolved.

This skill is primarily for alignment across:

- TD
- PM
- QA

It is appropriate both when a feature is still being clarified during development and when documentation needs to be backfilled after implementation work already exists.

## Use this skill when

Use this skill when the user wants help with any of the following:

- writing a feature spec for an in-progress feature;
- backfilling a feature-facing document from existing notes, tickets, docs, or code;
- defining or refining feature boundaries;
- clarifying goals and non-goals for review or handoff;
- documenting expected behavior and failure scenarios for TD / PM / QA alignment;
- turning mixed project inputs into a structured feature document draft.

Typical requests may sound like:

- “Help me write the feature spec for this.”
- “Turn this ticket and current implementation into a spec.”
- “Document what this feature does and does not do.”
- “Write the QA/PM-facing feature doc for this flow.”

## Do not use this skill when

Do not use this skill when the main need is:

- internal implementation-flow explanation;
- module/component responsibility mapping for engineers;
- architecture-only discussion;
- generic release notes or changelog writing;
- pure editorial cleanup of an already-correct document without substantive feature clarification.

In those cases, another more specialized skill should own the work.

## Expected inputs

This skill should work from mixed and partial inputs.

Common inputs include:

- user notes;
- ticket or issue text;
- screenshots or mock descriptions;
- existing documentation;
- partially implemented behavior;
- readable project code used to recover context.

No single input source is required.

If information is incomplete but the project is readable, inspect the repository to recover missing context before asking the user too many questions.

Use codebase inspection to recover context, not to silently replace missing product decisions.

## Expected outputs

The default output is a **structured draft**, not necessarily a polished final submission.

The draft should default to this structure:

```md
## Overview
## Goals
## Non-Goals
## Usage Context
## Expected Behavior
## Error Scenarios
## Edge Cases (Optional)
## Known Issues (Optional)
## Open Questions (Optional)
```

The output should make it easy to review the feature from a product and validation perspective, not only from an engineering perspective.

## Working posture

### 1. Recover context first

Before drafting, identify what is already known from:

- direct user statements;
- existing docs or tickets;
- current code behavior;
- inferred project context.

Separate clearly between:

- confirmed facts;
- inferred assumptions;
- unresolved questions.

### 2. Ask only high-value questions

Do not stall the whole task by interrogating the user for every missing detail.

Instead:

1. recover what can be learned from available inputs;
2. ask a small number of targeted questions only where ambiguity materially changes the document;
3. draft early;
4. refine iteratively.

High-value question areas often include:

- what outcome the feature is meant to achieve;
- what is explicitly out of scope;
- who uses the feature or in what situation it appears;
- where expected behavior is still ambiguous;
- which failures matter enough to call out.

### 3. Support two source modes

This skill should support:

- **forward-writing**: from requirements, notes, or tickets into a fresh feature spec draft;
- **reverse-writing**: from existing code, docs, or implemented behavior into a feature-facing document.

### 4. Stay feature-facing

The document should emphasize:

- intent;
- boundaries;
- user-visible behavior;
- failure scenarios;
- known limitations;
- unresolved decisions.

Do not let the document collapse into a technical design note unless implementation detail is necessary to explain externally visible behavior.

When backfilling from existing implementation, do not assume the current code fully represents intended scope if other inputs disagree.

## Important section guidance

### Overview

Briefly explain what the feature is, why it exists, and what larger context matters.

### Goals

State what the feature is trying to achieve in this iteration.

### Non-Goals

State what this feature intentionally does not solve, cover, or change.

### Usage Context

Describe when the feature is encountered, who uses it, and what surrounding workflow matters.

### Expected Behavior

Describe what should happen in normal usage. Favor concrete behavior over abstract promises.

### Error Scenarios

Describe meaningful failure conditions, invalid states, rejection paths, or user-visible error outcomes.

### Edge Cases

Use this only when special-case behavior matters enough to call out separately.

### Known Issues

Use this when there are current limitations, acknowledged gaps, or behavior caveats that reviewers should know.

### Open Questions

Use this when decisions remain unresolved and would materially affect scope, behavior, or follow-up work.

## Acceptance-criteria rule

Do not invent formal acceptance criteria by default.

If explicit acceptance criteria already exist in user input, PM notes, TD guidance, QA materials, or project docs, include them where appropriate.

Otherwise, rely on clear expected-behavior language instead of pretending formal acceptance criteria were provided.

## Constraints and anti-patterns

- Do not write this as an internal engineering design doc.
- Do not overfit the structure to one team’s file-location convention; stay location-agnostic.
- Do not silently convert assumptions into facts.
- Do not infer product intent only from current implementation when other evidence is available.
- Do not hide unresolved product or scope ambiguity.
- Do not replace non-goals with vague wording; make exclusions explicit when they matter.
- Do not over-explain implementation internals unless they change feature-facing understanding.

## Good result characteristics

A good result from this skill should:

- give TD / PM / QA a shared understanding of the feature;
- make feature boundaries explicit;
- clarify expected and failure behavior;
- expose missing decisions rather than burying them;
- remain understandable even when built partly from codebase evidence.
