---
name: careful-implementation
description: Use during feature implementation, bug fixing, refactoring, and other non-trivial code changes in an existing codebase. Helps the agent avoid silent assumptions, overengineering, unrelated edits, and unverifiable completion claims. Especially useful when modifying existing code where diffs should stay minimal, focused, and well-verified. Do not use for feature-spec writing, technical-document writing, document polishing, brainstorming, or architecture-only discussion.
---

# Careful Implementation

Use this skill during implementation work when the main risk is not lack of ideas, but bad execution habits:

- silently guessing requirements;
- overengineering the solution;
- touching too much unrelated code;
- claiming completion without meaningful verification.

This skill is primarily for:

- RD / software engineers;
- implementation-focused coding agents;
- existing-codebase work where changes should stay narrow and reviewable.

It is not a full workflow manager and not a general writing style guide. Its job is to improve implementation judgment during code-editing work.

## Use this skill when

Use this skill when the user wants help with any of the following:

- implementing a feature in an existing codebase;
- fixing a bug or regression;
- refactoring code without changing intended behavior;
- making a risky or non-trivial code change;
- keeping a diff narrow and focused;
- avoiding overengineering during implementation;
- verifying that implementation work is actually complete.

Typical requests may sound like:

- “Implement this feature.”
- “Fix this bug.”
- “Refactor this without changing behavior.”
- “Make the smallest safe change here.”
- “Update this area without touching unrelated code.”

## Do not use this skill when

Do not use this skill when the main need is:

- writing a feature spec;
- writing a technical document;
- polishing or rewriting an existing document draft;
- brainstorming product or architecture directions before implementation starts;
- broad open-ended research without code changes;
- high-level design discussion where the main problem is choosing the approach, not executing it carefully;
- workflow orchestration, task sequencing, or execution-state management.

In those cases, a more specialized writing, design, research, or planning skill should own the work.

## What this skill prevents

This skill exists to reduce these common failure modes:

- **silent assumption drift** — the agent picks one interpretation and runs without surfacing uncertainty;
- **speculative abstraction** — the agent builds flexibility or architecture that was not requested;
- **oversized diffs** — the agent edits adjacent code that is not required for the task;
- **cleanup sprawl** — the agent starts refactoring or deleting unrelated code “while it is here”;
- **false completion** — the agent writes code and declares success without real verification;
- **misunderstood edits** — the agent changes code it does not understand just to make things look cleaner.

## Scope boundary

This skill improves how implementation work is carried out locally.

It should not take over:

- workflow routing;
- task sequencing across multiple work units;
- checklist ownership;
- long-horizon execution-state management.

Use it to strengthen the quality of the code-editing slice itself, not to manage the surrounding workflow.

## Core implementation posture

### 1. Control assumptions

Before editing, separate:

- what is explicitly known;
- what is inferred but uncertain;
- what is missing and important.

If a missing detail would materially change the implementation, surface it instead of guessing silently.

If the ambiguity is low-risk and the task can move forward safely, state the assumption briefly and continue.

### 2. Prefer the smallest sufficient solution

Bias toward the simplest change that fully satisfies the request.

Avoid:

- abstractions for one-time use;
- future-proofing that was not asked for;
- configurability with no current need;
- extra edge-case handling for impossible or unsupported scenarios;
- expanding scope because a “better system” could be imagined.

If 50 lines solve the problem safely, do not write 200.

### 3. Keep changes contained

Every changed line should trace back to the current task.

Do not:

- refactor adjacent code just because it looks messy;
- rename unrelated symbols for style reasons;
- reformat or rewrite comments outside the needed area;
- remove pre-existing dead code unless the user asked for cleanup.

Do clean up the specific imports, variables, or orphaned helpers that your own change makes unnecessary.

### 4. Verify before claiming done

Code edits alone are not completion.

Use the smallest meaningful verification available, such as:

- a focused test;
- a reproduction that now passes;
- a build/lint check for the changed area;
- a direct observable behavior check.

If proper verification is not possible, say so explicitly and state what remains uncertain.

## Execution heuristics

During implementation, prefer this sequence:

1. identify the exact task and likely file scope;
2. check for critical ambiguity;
3. choose the smallest workable change;
4. implement narrowly;
5. verify the change;
6. report any remaining uncertainty or risk.

For bug fixes:

- prefer reproducing or naming the failing behavior before patching;
- avoid speculative fixes that are not tied to an observed failure mode.

For refactors:

- preserve behavior unless the user explicitly asked for behavior change;
- keep before/after verification clear.

For feature work:

- implement the requested behavior, not an imagined framework for future variants.

## Good pushback behavior

Push back briefly when:

- the requested approach is clearly overcomplicated;
- a much smaller change would satisfy the same goal;
- the task description hides a high-risk ambiguity;
- the user appears to be asking for cleanup or architecture expansion that is much broader than the stated need.

Pushback should be short and practical, not philosophical.

## Constraints and anti-patterns

- Do not treat uncertainty as permission to invent requirements.
- Do not treat elegance as a reason to broaden scope.
- Do not rewrite large areas just to make the code look more uniform.
- Do not smuggle architecture work into a bug fix.
- Do not claim success based only on code being written.
- Do not let “while I’m here” cleanup dominate the requested task.
- Do not let this skill override writing-oriented or planning-oriented skills outside implementation work.

## Good result characteristics

A good result from this skill should:

- make the minimum necessary change;
- surface important assumptions instead of hiding them;
- avoid speculative architecture;
- keep the diff focused on the request;
- include meaningful verification or explicit verification limits;
- leave the codebase safer, not merely larger.
