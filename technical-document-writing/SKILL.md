---
name: technical-document-writing
description: Write or refine engineering-facing technical documentation that explains how a feature works internally. Use when the user needs a technical document covering relationship to feature scope, flow overview, involved components, data and state flow, error handling, dependencies, constraints, or known risks based on plans, code, or existing implementation. Do not use for TD/PM/QA-facing feature specs, high-level product scoping, release notes, or pure architecture brainstorming.
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

## Working posture

### 1. Recover implementation context first

Before drafting, identify what is already known from:

- direct user statements;
- feature specs or prior docs;
- current code behavior;
- logs or observed runtime behavior;
- inferred system structure.

Separate clearly between:

- confirmed facts;
- inferred assumptions;
- unresolved questions.

### 2. Ask only high-value questions

Do not block the task on exhaustive discovery.

Instead:

1. recover what can be learned from available inputs and repository inspection;
2. ask a small number of targeted questions only where ambiguity materially changes the document;
3. draft early;
4. refine iteratively.

High-value question areas often include:

- what the true flow boundaries are;
- which modules own important responsibilities;
- what state changes are intentional versus incidental;
- where error handling is incomplete or ambiguous;
- which constraints or tradeoffs are deliberate.

### 3. Support two source modes

This skill should support:

- **forward-writing**: from specs, notes, and implementation plans into a technical document draft;
- **reverse-writing**: from existing code, logs, behavior, or partial docs into an engineering-facing technical document.

### 4. Stay engineering-facing

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

### Overview

Briefly explain what feature or technical area this document covers.

### Relationship

Link the document to the related feature spec, feature scope, ticket, or implementation context. If no formal feature spec exists, explain what source of truth this document is anchored to.

This section should anchor context, not restate the whole feature spec.

### Flow Overview

Describe the main end-to-end flow at a level that makes the rest of the document easier to follow.

### Components Involved

Identify the main modules, services, jobs, components, or layers involved, and briefly state their roles.

### Data and State Flow

Describe what data enters the flow, how it changes, what state transitions matter, and what dependencies influence later behavior.

### Error Handling

Describe major failure paths, propagation behavior, recovery logic, fallback behavior, and any important user-visible consequences.

### Dependencies and Integration Points

Describe external services, internal subsystems, events, storage, APIs, configuration, or permissions that materially affect the feature.

### Constraints and Tradeoffs

Describe meaningful technical limits, deliberate compromises, or design decisions that shape the implementation.

### Known Risks / Known Issues

Use this for implementation risks, maintenance risks, technical debt, behavioral gaps, or other known concerns that should not be hidden.

### Open Questions

Use this when implementation details, boundaries, ownership, or follow-up design decisions remain unresolved.

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
