---
name: compact-skill-authoring
description: Create compact, high-leverage skills by first interviewing the user for missing context, trigger boundaries, failure modes, and intended leverage, then writing a tightly scoped skill document. Use when the goal is to author or refine a small, reusable skill that improves knowledge, judgment, or task capability without turning into a workflow engine, global persona, or overly broad handbook.
---

# Compact Skill Authoring

Create compact, high-leverage skills.

This skill is for authoring **small, reusable, sharply bounded** skills that improve agent behavior without becoming a bloated framework.

The expected pattern is:

1. gather missing context from the user;
2. sharpen the skill boundary;
3. compress the idea into its highest-leverage form;
4. write a concise skill document.

## Use this skill when

Use this skill when the user wants help creating a new skill, turning a rough behavioral idea into a reusable skill, or tightening an existing skill that feels too broad, too long, or too workflow-heavy.

Typical requests may sound like:

- “Help me turn this into a skill.”
- “I want a small skill for this behavior.”
- “Can you write a SKILL.md for this idea?”
- “This skill is too broad — help me compress it.”

## Do not use this skill when

Do not use this skill when the main need is running a full eval/benchmark/review loop for a mature skill set, installing or packaging a completed skill without changing its design, creating a workflow-orchestration system, generating a giant reference-heavy handbook skill, or skipping user context gathering when the intended behavior is still ambiguous.

In those cases, a broader skill-creation or workflow tool should own the work.

## Core principle

Do not start by writing the skill.

Start by understanding what problem the skill should solve, where it should trigger, where it should not trigger, and what kind of leverage it should provide.

The compactness is not just about fewer lines. It is about keeping only the instructions that materially improve behavior.

Also decide early whether the idea should become a reusable skill at all. Some ideas belong in project policy, agent configuration, workflow tooling, or one-off prompts instead.

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

Once the context is clear, reduce the design to its smallest useful form.

Prefer a sharp trigger boundary, 3-6 strong principles, explicit anti-patterns, and one clear type of leverage.

Challenge anything that behaves like workflow ownership, global persona, speculative future-proofing, or a “do everything” skill.

## Authoring rules

When writing the skill document:

- keep it self-contained;
- define what the skill is for;
- define when to use it;
- define when not to use it;
- define expected inputs;
- define expected outputs if relevant;
- name the main constraints or anti-patterns;
- keep the writing dense, concrete, and behavior-shaping.

Prefer instructions that improve behavior at many future uses, not just one current example.

Treat the frontmatter description as a trigger contract, not just a summary. It should describe both what the skill does and the situations where it should load.

Do not assume any one fixed installation path or repository layout. If the user already has a repository structure or target directory convention, follow that. Otherwise stay path-neutral and focus on the skill content first.

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

The goal is not full uniformity. The goal is to keep every skill bounded, triggerable, self-contained, readable, and not heavier than necessary.

## Preferred targets and common failures

This skill is optimized for compact, reusable, failure-mode-driven skills such as judgment skills, implementation-posture skills, review heuristic skills, focused writing skills, and bounded task-capability skills.

Avoid producing skills that are too broad to trigger safely, mostly manifesto with no operational boundary, secretly workflow engines, giant generic handbooks, or trying to solve several unrelated problems at once.

## Suggested authoring flow

Use this sequence:

1. restate the user's goal in plain language;
2. identify the intended leverage type;
3. identify trigger situations and near-miss non-trigger situations;
4. identify 3-6 core failure modes or behavior improvements;
5. compress the scope;
6. draft the skill;
7. do one final compression-and-clarity pass.

That final pass should remove repetition, sharpen trigger language, improve readability, preserve the intended boundary and leverage, and stop short of turning the task into pure editorial cleanup when real scope correction is still needed.

## Good result characteristics

A good result from this skill should:

- feel smaller than the original idea, not bigger;
- have clearer boundaries than the user started with;
- improve one category of agent behavior strongly;
- avoid unnecessary workflow ownership;
- be realistic to install and reuse in other projects.
