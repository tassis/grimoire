# AGENTS.md

This repository defines a personal OpenCode skill collection.

## Purpose

- Build reusable skills for personal work workflows.
- Focus on giving agents better **knowledge**, **judgment**, and **task capability**.
- Do **not** treat this repo as the main workflow/orchestration layer.
- Workflow control, scheduling, and installation flows are expected to be handled by other plugins/tools.

## Repository shape

Use a flat, self-contained skill layout.

```text
<repo-root>/
  AGENTS.md
  <skill-name>/
    SKILL.md
  <skill-name>/
    SKILL.md
```

Rules:

- Each top-level skill directory is one installable unit.
- Each skill directory must contain its own `SKILL.md`.
- Do not introduce shared dependency folders like `_shared/`, `common/`, or cross-skill includes.
- A skill must remain useful when copied or installed by itself.

## Authoring rules

- Prefer **flat top-level directories** over nested category trees.
- Use **kebab-case** for skill directory names.
- Keep every skill **self-contained**.
- If a skill needs helper files later, keep them inside that skill's own directory.
- Do not rely on repo-level docs for behavior-critical instructions.

## Skill design intent

Skills in this repo should primarily provide:

- domain knowledge
- review heuristics
- decision frameworks
- task playbooks
- reusable output structures

Skills in this repo should generally avoid owning:

- end-to-end orchestration
- session scheduling
- multi-skill workflow state machines
- project-specific install glue outside the skill itself

## Installation model

- Assume skills may be installed individually into arbitrary projects.
- Design every skill as a portable package-like directory.
- Avoid references that break when the skill is detached from this repo.

## Default expectations for `SKILL.md`

Each skill should define, in its own file:

- what the skill is for
- when to use it
- when not to use it
- expected inputs
- expected outputs
- important constraints or anti-patterns

## Change guidance

When adding or editing a skill:

1. Preserve the flat installable structure.
2. Keep the skill self-sufficient.
3. Tighten trigger boundaries instead of making the skill overly general.
4. Optimize for reuse across different target projects.

## Non-goals

- No shared support library structure.
- No mandatory monorepo-style internal dependency graph between skills.
- No assumption that all skills are always installed together.
