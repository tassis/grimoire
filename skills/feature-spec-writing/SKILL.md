---
name: feature-spec-writing
description: Write or backfill a feature-facing specification for TD, PM, and QA alignment. Use when the user needs a document that defines feature goals, non-goals, usage context, expected behavior, error scenarios, known issues, or open questions. Prefer this over technical-document-writing when the main audience is PM/QA/TD and the main job is defining feature boundaries and externally visible behavior. Do not use for internal technical-flow documentation or for polishing an already-correct draft.
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

## Working approach

Before drafting, recover what is already known from user statements, docs, tickets, code behavior, and project context.

Separate clearly between:

- confirmed facts;
- inferred assumptions;
- unresolved questions.

Ask only a small number of targeted questions where ambiguity would materially change the document, then draft early and refine iteratively.

This skill should support both:

- **forward-writing**: from requirements, notes, or tickets into a fresh feature spec draft;
- **reverse-writing**: from existing code, docs, or implemented behavior into a feature-facing document.

## Stay feature-facing

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

- **Overview / Goals / Non-Goals** should make the feature intent and explicit boundary easy to review.
- **Usage Context** should explain where the feature appears and who encounters it.
- **Expected Behavior / Error Scenarios** should favor concrete behavior and meaningful failure outcomes over abstract promises.
- **Known Issues / Open Questions** should preserve current limits and unresolved decisions instead of smoothing them away.

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
