---
name: technical-document-writing
description: Write or backfill an engineering-facing technical document that explains how a feature works internally. Use when the user needs system flow, involved components, data and state movement, error handling, dependencies, constraints, or known risks documented for engineers and maintainers. Prefer this over feature-spec-writing when the main audience is engineering and the main job is explaining implementation behavior rather than defining product-facing scope. Do not use for PM/QA-facing feature specs or for polishing an already-correct draft.
---

# Technical Document Writing

Write an engineering-facing document that explains how a feature works internally, how its flow moves through the system, what components participate, how data and state change, how failures are handled, and what technical constraints or risks matter.

This skill is primarily for:

- engineers;
- technical leads;
- maintainers who need a clear implementation-oriented reference.

It is useful both when technical details are being clarified during implementation and when a technical document needs to be reconstructed from existing code or behavior.

## Use this skill when

Use this skill when the user wants help with any of the following:

- writing an engineering-facing technical document for a feature;
- backfilling technical documentation from existing code, flows, or partial implementation;
- explaining how a feature works internally across modules or services;
- documenting data movement, state transitions, error handling, constraints, or integration points;
- turning mixed project evidence into a structured technical document draft.

Typical requests may sound like:

- “Help me write the technical doc for this feature.”
- “Explain this flow in document form from the current code.”
- “Turn this spec and implementation into an engineering-facing doc.”
- “Document the internal flow, modules, and risks for this system.”

## Do not use this skill when

Do not use this skill when the main need is:

- TD / PM / QA-facing feature alignment;
- defining goals, non-goals, or product scope as the primary task;
- generic release notes or changelog writing;
- pure architecture brainstorming before implementation details exist;
- pure editorial cleanup of an already-correct document without technical clarification.

In those cases, another more specialized skill should own the work.

## Expected inputs

This skill should work from mixed and partial inputs.

Common inputs include:

- feature specs;
- existing technical notes;
- readable project code;
- logs or behavior observations;
- partially implemented flows;
- prior technical documents or design notes.

A feature spec is helpful but not required.

If the feature flow is unclear but the project is readable, inspect the repository to recover context before asking the user too many questions.

Use codebase inspection to recover how the system currently works, not to silently invent missing technical decisions.

## Expected outputs

The default output is a **structured draft**, not necessarily a polished final submission.

The draft should default to this structure:

```md
## Overview
## Relationship
## Flow Overview
## Components Involved
## Data and State Flow
## Error Handling
## Dependencies and Integration Points
## Constraints and Tradeoffs
## Known Risks / Known Issues
## Open Questions (Optional)
```

The output should help engineers understand internal behavior and maintenance-relevant facts, not just restate product-facing scope.

## Working approach

Before drafting, recover what is already known from user statements, feature specs, prior docs, code behavior, logs, and inferred system structure.

Separate clearly between:

- confirmed facts;
- inferred assumptions;
- unresolved questions.

Ask only a small number of targeted questions where ambiguity would materially change the document, then draft early and refine iteratively.

This skill should support both:

- **forward-writing**: from specs, notes, and implementation plans into a technical document draft;
- **reverse-writing**: from existing code, logs, behavior, or partial docs into an engineering-facing technical document.

## Stay engineering-facing

The document should emphasize:

- internal flow;
- implementation boundaries;
- component responsibilities;
- data and state movement;
- error handling behavior;
- dependencies;
- constraints and risks.

Do not let the document collapse into a product-facing feature spec or a goals/non-goals document.

When backfilling from existing implementation, do not assume the current code is the full intended design if other evidence suggests gaps, drift, or unfinished work.

## Important section guidance

- **Relationship** should anchor the document to the related feature spec, ticket, scope, or implementation context without restating the whole feature spec.
- **Flow Overview** should make the end-to-end path easy to follow before the details.
- **Data and State Flow / Error Handling** should explain how the system changes over time and how failures move through it.
- **Constraints, Known Risks, and Open Questions** should preserve meaningful limits, debt, and unresolved design issues instead of hiding them.

## Constraints and anti-patterns

- Do not write this as a feature-facing product spec.
- Do not overfit the structure to one team’s file-location convention; stay location-agnostic.
- Do not silently convert assumptions into facts.
- Do not infer full intended architecture only from the current implementation when other evidence conflicts.
- Do not replace flow explanation with a list of modules that lacks interaction details.
- Do not treat code walkthrough detail as a substitute for explaining the system flow.
- Do not hide meaningful risks, constraints, or unresolved ownership questions.

## Good result characteristics

A good result from this skill should:

- explain how the feature currently works internally;
- help engineers trace flow across relevant components;
- make data/state movement and error handling understandable;
- surface important technical constraints and risks;
- remain useful even when reconstructed partly from codebase evidence.
