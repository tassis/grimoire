---
name: compact-skill-authoring
description: Create compact, high-leverage OpenCode skills by first interviewing the user for missing context, trigger boundaries, failure modes, and intended leverage, then writing a tightly scoped SKILL.md. Use when the goal is to author or refine a small, reusable skill that improves knowledge, judgment, or task capability without turning into a workflow engine, global persona, or overly broad handbook.
---

# Compact Skill Authoring

Create compact, high-leverage skills.

This skill is for authoring **small, reusable, sharply bounded** OpenCode skills that improve agent behavior without becoming a bloated framework.

The expected pattern is:

1. gather missing context from the user;
2. sharpen the skill boundary;
3. compress the idea into its highest-leverage form;
4. write a concise `SKILL.md`.

## Use this skill when

Use this skill when the user wants help with any of the following:

- creating a new OpenCode skill;
- turning a rough behavioral idea into a reusable skill;
- designing a narrowly scoped judgment, capability, or writing skill;
- tightening an existing skill that feels too broad, too long, or too workflow-heavy;
- authoring a skill that should be compact, reusable, and easy to install.

Typical requests may sound like:

- “Help me turn this into a skill.”
- “I want a small skill for this behavior.”
- “Can you write a SKILL.md for this idea?”
- “This skill is too broad — help me compress it.”

## Do not use this skill when

Do not use this skill when the main need is:

- running a full eval/benchmark/review loop for a mature skill set;
- installing or packaging a completed skill without changing its design;
- creating a workflow-orchestration system rather than a compact skill;
- generating a giant reference-heavy handbook skill;
- skipping user context gathering when the intended behavior is still ambiguous.

In those cases, a broader skill-creation or workflow tool should own the work.

## Core principle

Do not start by writing the skill.

Start by understanding what problem the skill should solve, where it should trigger, where it should not trigger, and what kind of leverage it should provide.

The compactness is not just about fewer lines. It is about keeping only the instructions that materially improve behavior.

## Required intake behavior

Before drafting, gather enough context to answer these questions:

1. **What should the skill enable?**
   - What useful behavior should become more reliable after the skill exists?

2. **When should it trigger?**
   - What kinds of user requests or work situations should cause the skill to load?

3. **When should it not trigger?**
   - What nearby tasks should be kept out of scope?

4. **What failure modes should it prevent?**
   - What bad agent habits, common mistakes, or missing behaviors is this skill meant to correct?

5. **What kind of leverage is intended?**
   - Is this mainly a knowledge skill, a judgment skill, a task-capability skill, or a writing/review skill?

6. **What shape should the output have?**
   - Should the resulting skill be posture-oriented, checklist-oriented, template-oriented, or playbook-oriented?

Ask targeted follow-up questions when the answers are still fuzzy.

## Compression mindset

Once the context is clear, compress the idea before writing.

Reduce the design to its smallest useful form.

Prefer:

- a sharp trigger boundary over a broad one;
- 3-6 strong principles over 20 weak instructions;
- explicit anti-patterns over vague “best practices”;
- one clear type of leverage over several loosely related purposes.

Remove or challenge:

- workflow ownership that should live elsewhere;
- instructions that act like a global persona;
- future-proofing that the user did not ask for;
- long examples that do not materially change behavior;
- “do everything” ambitions.

## Authoring rules

When writing the `SKILL.md`:

- keep it self-contained;
- define what the skill is for;
- define when to use it;
- define when not to use it;
- define expected inputs;
- define expected outputs if relevant;
- name the main constraints or anti-patterns;
- keep the writing dense, concrete, and behavior-shaping.

Prefer instructions that improve behavior at many future uses, not just one current example.

## Section structure guidance

Do not force every skill into an identical full template.

However, do use a **light fixed skeleton** so the result does not become vague or incomplete.

### Usually include these minimum sections

- what the skill is for;
- when to use it;
- when not to use it;
- expected inputs;
- constraints or anti-patterns.

### Add these only when they materially help

- expected outputs;
- failure modes the skill prevents;
- operating posture or process guidance;
- output structure or report template;
- examples.

The goal is not full uniformity.

The goal is to keep every skill:

- bounded;
- triggerable;
- self-contained;
- readable;
- not heavier than necessary.

## Preferred skill style

This skill is optimized for creating skills that are:

- compact;
- reusable;
- high-leverage;
- failure-mode-driven;
- easy to install independently;
- resistant to trigger sprawl.

Especially good targets include:

- judgment skills;
- implementation-posture skills;
- review heuristic skills;
- focused writing skills;
- bounded task-capability skills.

## Failure modes to avoid while authoring

Avoid producing skills that are:

- too broad to trigger safely;
- mostly a manifesto with no operational boundary;
- secretly workflow engines;
- giant generic handbooks;
- missing a `Do not use` section in practice even if not titled exactly that;
- trying to solve several unrelated problems at once.

## Suggested authoring flow

Use this sequence:

1. restate the user's goal in plain language;
2. identify the intended leverage type;
3. identify trigger situations and near-miss non-trigger situations;
4. identify 3-6 core failure modes or behavior improvements;
5. compress the scope;
6. draft the skill;
7. review the draft for breadth, overlap, and unnecessary weight.

## Good result characteristics

A good result from this skill should:

- feel smaller than the original idea, not bigger;
- have clearer boundaries than the user started with;
- improve one category of agent behavior strongly;
- avoid unnecessary workflow ownership;
- be realistic to install and reuse in other projects.
