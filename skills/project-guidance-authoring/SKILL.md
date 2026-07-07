---
name: project-guidance-authoring
description: Author or update repo-wide guidance documents by inspecting the repository, recovering current conventions, and writing audience-appropriate guidance for developers, agents, or both. Use when the user wants durable project guidance such as development guides, API conventions, database layering guides, recurring implementation-conventions guides, or repo-level agent guidance like AGENTS.md. Prefer this for repository-wide conventions and guidance artifacts, not for one feature’s behavior or internals. Do not use for single-feature specs, single-feature technical docs, pure polishing of an existing draft, or workflow orchestration.
---

# Project Guidance Authoring

Author project-level guidance.

This skill is for writing or updating documents that explain **how a project should be developed over time**, not how one specific feature works.

Typical outputs include:

- developer-facing guides under locations such as `docs/`;
- repo-level agent guidance such as `AGENTS.md`;
- project conventions covering API design, database layering, service boundaries, implementation patterns, or repository structure.

## Use this skill when

Use this skill when the user wants help with any of the following:

- writing or updating developer docs for a project;
- documenting how APIs should be structured in this repository;
- documenting how database and service layers should be separated;
- writing onboarding or implementation guidance for future contributors;
- writing or updating agent-facing project guidance such as `AGENTS.md`;
- turning current repository patterns into durable project-level conventions.

Typical requests may sound like:

- “Write a development guide for this repo.”
- “Document how new APIs should be added here.”
- “Write docs for developers about DB layering and service boundaries.”
- “Help me write AGENTS.md based on this project’s structure and conventions.”

## Do not use this skill when

Do not use this skill when the main need is:

- writing a feature-facing spec for one feature;
- writing a technical document for one feature or flow;
- polishing an already-correct draft without changing structure or content design;
- broad architecture exploration before conventions are ready to be documented;
- workflow planning, execution sequencing, or orchestration.

In those cases, a more specialized feature-doc, technical-doc, polishing, or workflow skill should own the work.

## Expected inputs

This skill is most useful when at least one of these exists:

- a repository with readable structure and code;
- existing docs or conventions notes;
- an existing `AGENTS.md` or similar guidance file;
- user-stated development preferences or layering rules;
- examples of how the project currently handles API, DB, service, or feature implementation work.

Inputs may be incomplete. When they are, inspect the repository before inventing conventions.

## Expected outputs

The expected output is one or more project-level guidance documents.

Common outputs include:

- a development guide;
- an API conventions guide;
- a database or layering guide;
- a project-wide implementation conventions guide;
- an `AGENTS.md` style repository guidance file.

The output should make clear whether it is describing:

- current observed conventions;
- intended conventions for future work;
- unresolved or inconsistent areas.

## Output modes

This skill supports at least two modes:

### 1. Developer-docs mode

Use when the primary audience is human developers.

Favor:

- explanation;
- rationale;
- onboarding clarity;
- examples where they materially help;
- readable structure for people browsing `docs/`.

### 2. Agent-guidance mode

Use when the primary audience is an agent or automation layer.

Favor:

- concise rules;
- sharper boundaries;
- operational clarity;
- explicit do/do-not guidance;
- repository-shape awareness.

Do not let this mode drift into:

- a global persona;
- workflow orchestration rules;
- execution-state management;
- multi-step state-machine policy.

If both modes are requested, derive them from the same underlying convention map, then adapt tone and structure to the audience instead of duplicating text blindly.

## Working approach

Before drafting, determine:

- the target audience;
- the target artifact or file;
- whether the goal is to describe current reality, define intended practice, or do both;
- which convention domains matter most.

Then recover what is already true from:

- repository structure;
- existing code patterns;
- existing docs;
- user-provided constraints and preferences.

Separate clearly between:

- observed current conventions;
- intended conventions;
- unresolved or inconsistent areas.

Do not flatten these into one false source of truth.

## Convention domains to cover selectively

Cover only the domains that matter for the current request.

Common domains include:

- API design and layering;
- database boundaries and persistence rules;
- controller/service/repository responsibilities;
- recurring implementation patterns;
- testing expectations;
- project file structure and ownership;
- naming and module conventions.

Do not generate a giant handbook when only one or two domains are needed.

## Guidance design rules

When writing project guidance:

- anchor guidance in actual project reality when possible;
- call out inconsistencies instead of hiding them;
- distinguish “how the project works now” from “how it should work going forward”;
- keep rules concrete enough that future contributors can act on them;
- adapt explanation depth to the audience.

For developer-facing docs, explain enough that a human can apply the guidance sensibly.

For agent-facing guidance, compress toward executable boundaries and repository-specific rules.

## Important failure modes to prevent

This skill should prevent:

- inventing conventions that the repository does not support;
- confusing feature-level docs with project-level guidance;
- mixing current reality and desired future rules without labeling the difference;
- writing agent guidance in a vague human-handbook style;
- writing developer docs in a terse machine-rule style;
- over-generalizing into a generic engineering guide with little project value.

## Constraints and anti-patterns

- Do not treat one local implementation detail as a universal project rule without evidence.
- Do not assume all current patterns are intentional conventions.
- Do not silently normalize obvious inconsistencies into a fake clean architecture.
- Do not collapse repo-level guidance into one feature’s technical explanation.
- Do not force output into one fixed path; follow user intent and project structure.
- Do not over-document domains the user did not ask for.

## Good result characteristics

A good result from this skill should:

- help future developers or agents work correctly in the project;
- reflect actual project structure where possible;
- distinguish current conventions from intended ones;
- make important boundaries explicit;
- stay scoped to the requested domains instead of becoming a giant handbook.
