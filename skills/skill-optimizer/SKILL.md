---

name: skill-optimizer
description: Optimize an existing Markdown agent skill for token efficiency, clarity, and execution reliability without changing its purpose, behavioral contract, safety requirements, or semantic meaning. Only modify the original skill when a reliable optimization of at least 30% is achievable.
---

# Skill Optimizer

## Purpose

Optimize an existing agent skill stored as a Markdown (`.md`) file.

The goal is to reduce unnecessary token usage while **improving or preserving execution reliability**.

The optimizer must never optimize past the skill's semantic boundary.

The original skill's:

* purpose
* intended behavior
* required behavior
* safety constraints
* tool requirements
* input/output contracts
* prohibitions
* precedence rules
* conditional logic
* important examples
* failure handling
* externally observable behavior

must remain semantically unchanged unless the original skill contains an obvious contradiction or ambiguity that can be resolved without inventing new behavior.

This is a **conservative optimizer**, not a rewriting or redesign agent.

---

# Operating Rules

## 1. Read the Entire Skill First

Before making any changes:

1. Read the complete Markdown file.
2. Understand its purpose and intended execution flow.
3. Identify all explicit requirements.
4. Identify implicit dependencies between requirements.
5. Identify safety-critical instructions.
6. Identify tool-use requirements and ordering constraints.
7. Identify output-format requirements.
8. Identify conditions, exceptions, and precedence rules.
9. Identify examples that convey behavior not stated elsewhere.
10. Establish the skill's behavioral contract before optimizing anything.

Do not optimize individual paragraphs in isolation.

---

# 2. Preserve the Semantic Boundary

Treat the existing skill as having an immutable semantic boundary.

An optimization is valid only when the optimized skill would cause an agent to make the same materially important decisions and produce the same intended outcomes.

Do NOT:

* change the purpose of the skill;
* introduce new capabilities;
* remove required capabilities;
* weaken safety requirements;
* weaken prohibitions;
* change tool selection requirements;
* change tool ordering requirements;
* change mandatory conditions;
* change exceptions;
* change precedence;
* change required output formats;
* change error handling;
* infer requirements that were not present;
* remove an instruction merely because it appears verbose;
* combine instructions when their conditions or scope differ;
* replace precise language with shorter but broader language;
* make an instruction more permissive or restrictive unless the original meaning is provably preserved.

When uncertain whether a change preserves semantics, **do not make the change**.

---

# 3. Safety Has Priority

Safety requirements have higher priority than token optimization.

Never remove or weaken safety instructions merely because they are repetitive.

However, genuine duplication may be consolidated when the resulting instruction provides the same or stronger safety guarantee.

For example, if three sections independently say that a dangerous operation must not be performed, they may be consolidated into one authoritative safety rule **only if doing so does not alter scope, precedence, or applicability**.

Do not assume that repetition is redundant when repetition establishes priority or reinforces a safety-critical constraint.

---

# 4. Reliability Has Priority Over Compression

Optimize for:

1. semantic correctness;
2. execution reliability;
3. clarity;
4. maintainability;
5. token efficiency.

Never reverse this order.

A shorter skill that is harder for an agent to execute correctly is **not an optimization**.

Prefer explicit instructions when they prevent:

* ambiguity;
* conflicting interpretations;
* incorrect tool use;
* skipped steps;
* incorrect ordering;
* accidental scope expansion;
* unsafe behavior;
* incorrect output;
* failure to handle exceptions.

---

# 5. Conservative Optimization

Do not perform deep compression.

Avoid optimization techniques that make instructions cryptic or overly dense.

Do not:

* turn several conditional rules into opaque shorthand;
* replace clear prose with difficult symbolic notation;
* eliminate useful headings solely to save tokens;
* excessively combine unrelated rules;
* remove whitespace that improves instruction boundaries;
* convert precise requirements into vague summaries;
* replace multiple important rules with a single overloaded sentence;
* remove examples when they communicate behavior that prose does not fully capture.

Prefer modest structural improvements and elimination of genuine redundancy.

---

# 6. What May Be Optimized

The optimizer may make changes such as:

### Remove genuine redundancy

Remove text that communicates the exact same requirement more than once, provided that:

* scope is identical;
* priority is identical;
* conditions are identical;
* no safety purpose is lost.

### Consolidate equivalent instructions

Combine closely related instructions when the combined form is at least as clear and preserves all conditions.

### Improve instruction ordering

Reorder sections when doing so improves execution reliability.

Prioritize placing:

1. purpose and scope;
2. critical constraints;
3. safety requirements;
4. inputs;
5. execution procedure;
6. exceptions;
7. output requirements

in a logical execution order.

Do not reorder instructions if their original order is itself behaviorally significant.

### Eliminate unnecessary prose

Remove:

* rhetorical language;
* repeated explanations;
* unnecessary introductions;
* motivational language;
* redundant summaries;
* duplicate examples;
* statements that do not affect execution.

### Resolve accidental ambiguity

If the existing skill contains wording that can reasonably produce multiple interpretations, improve the wording when the intended interpretation is clear from the surrounding skill.

Do not invent a new interpretation.

If the intended interpretation is genuinely unclear, preserve the original and report the ambiguity instead.

### Improve formatting

Use headings, lists, tables, or concise structure when this makes the skill easier for an agent to follow.

Do not restructure merely for cosmetic reasons.

---

# 7. What Must Not Be Optimized Away

Treat the following as potentially behaviorally significant:

* MUST / SHALL requirements;
* MUST NOT / SHALL NOT requirements;
* safety constraints;
* tool restrictions;
* tool-call ordering;
* required validation;
* required confirmation;
* conditional branches;
* exceptions;
* fallback behavior;
* error handling;
* output schemas;
* required fields;
* exact terminology;
* precedence rules;
* negative constraints;
* examples that clarify otherwise ambiguous behavior.

Before removing any such instruction, prove that its function is fully preserved elsewhere.

If proof is not possible, keep it.

---

# 8. Establish a Behavioral Contract

Before editing, internally extract a compact behavioral contract.

The contract should capture:

### Purpose

What problem does the skill solve?

### Inputs

What does the skill consume?

### Outputs

What must it produce?

### Required actions

What must the agent do?

### Prohibited actions

What must the agent never do?

### Conditions

When does each behavior apply?

### Exceptions

When do normal rules not apply?

### Ordering

Which actions must happen before others?

### Tools

Which tools must or must not be used?

### Safety

What safety constraints must remain intact?

### Failure behavior

What happens when the normal path cannot be completed?

### Precedence

Which instruction wins when rules conflict?

The optimized skill must satisfy this behavioral contract.

Do not include the full internal contract in the modified skill unless it is already part of the skill's intended content.

---

# 9. Detect Contradictions Before Optimizing

Look for:

* directly conflicting instructions;
* contradictory tool requirements;
* inconsistent output requirements;
* duplicated rules with different wording;
* exceptions that appear to contradict general rules;
* instructions whose scope is unclear.

Do not silently redesign the skill to resolve these problems.

If the intended resolution is obvious from context, clarify it while preserving the apparent intent.

If it is not obvious, leave the relevant content unchanged and report the ambiguity.

---

# 10. Estimate Optimization Before Editing

Estimate the token count of:

* the original skill;
* the proposed optimized skill.

Calculate:

`reduction_percentage = ((original_tokens - optimized_tokens) / original_tokens) × 100`

The optimization threshold is **30%**.

## If estimated reduction is below 30%

Do NOT modify the original skill.

Do NOT create a backup.

Do NOT create an optimized replacement.

Instead, produce only the final optimization report explaining:

* that the skill was analyzed;
* estimated achievable reduction;
* why further compression would risk reliability, clarity, or semantic fidelity;
* recommended non-destructive observations, if any.

A result below 30% is considered **not sufficiently valuable to justify modifying the skill**.

## If estimated reduction is 30% or greater

Proceed to validation before modifying the original.

Do not modify the original merely because a 30% reduction appears possible.

The proposed version must also pass semantic and reliability checks.

---

# 11. Backup Before Modification

If and only if the final validated optimization meets the 30% threshold:

1. Create a backup of the original Markdown file.
2. Preserve the original contents exactly.
3. Append the current date and time to the backup filename.
4. Only after the backup succeeds, replace/update the original with the optimized version.

Use a filename pattern such as:

`skill-name.backup-YYYY-MM-DD-HH-mm-ss.md`

Use the actual current date and time available to the agent.

Never overwrite the original before successfully creating the backup.

If backup creation fails:

* do not modify the original;
* report the failure;
* preserve the proposed optimization only as a report/draft if possible.

Do not create a backup when the optimization threshold is not met.

---

# 12. Validate the Proposed Skill

Before applying any optimization, compare the original and proposed versions against the behavioral contract.

Verify:

### Purpose

The purpose is unchanged.

### Scope

The scope is unchanged.

### Inputs

All required inputs remain supported.

### Outputs

All required outputs remain supported.

### Actions

Every required action remains present.

### Prohibitions

Every meaningful prohibition remains present.

### Conditions

All conditional behavior remains equivalent.

### Exceptions

All meaningful exceptions remain intact.

### Ordering

Required ordering remains intact.

### Tools

Tool requirements and restrictions remain intact.

### Safety

Safety guarantees are preserved or strengthened.

### Failure handling

Failure and fallback behavior remain intact.

### Precedence

Instruction priority remains unchanged.

### Examples

Examples removed during optimization must not contain unique behavioral information.

### Ambiguity

The optimized version must not introduce new ambiguity.

---

# 13. Semantic Equivalence Test

For every significant behavior in the original skill, ask:

> "Could an agent following the optimized skill reasonably make a different decision here?"

If the answer is yes or uncertain:

* restore the original instruction;
* revise the optimization;
* or abandon the optimization.

Do not assume semantic equivalence merely because two sentences have similar meanings.

Pay particular attention to words such as:

* always;
* never;
* only;
* unless;
* except;
* before;
* after;
* if;
* otherwise;
* must;
* may;
* should;
* can.

These words frequently encode behavioral constraints.

---

# 14. Reliability Test

The optimized skill must be at least as easy for an agent to execute correctly as the original.

Check for:

* clearer step boundaries;
* fewer competing instructions;
* clearer precedence;
* fewer duplicated rules;
* clearer conditions;
* explicit safety boundaries;
* preserved tool requirements;
* preserved exception handling.

If compression makes execution less reliable, reject the optimization even if it exceeds 30%.

---

# 15. Token Reduction Must Be Real

Do not artificially reach 30% by:

* removing meaningful whitespace only;
* moving content elsewhere;
* deleting examples that encode behavior;
* deleting safety rules;
* deleting edge cases;
* deleting output requirements;
* replacing instructions with unexplained references;
* making language intentionally vague.

The 30% threshold applies to **meaningful content reduction**, not cosmetic manipulation.

---

# 16. Final Decision

There are only three valid outcomes.

## Outcome A — Optimize

Use this when:

* meaningful reduction is at least 30%;
* semantic equivalence is maintained;
* reliability is maintained or improved;
* safety is preserved;
* backup succeeds.

Then:

1. create the timestamped backup;
2. apply the optimized skill;
3. verify the resulting file;
4. produce the final report.

## Outcome B — Do Not Optimize

Use this when:

* achievable reduction is below 30%;
* or the 30% reduction would require unacceptable semantic compression;
* or reliability would decrease;
* or safety would be weakened;
* or semantic equivalence cannot be established.

Do not modify the skill.

Do not create a backup.

Produce the final report.

## Outcome C — Cannot Safely Determine

Use this when:

* the skill is internally contradictory;
* the intended behavior is materially ambiguous;
* the file cannot be safely read or validated;
* required filesystem operations fail;
* or semantic equivalence cannot reasonably be assessed.

Do not modify the skill.

Do not create a backup unless an actual modification is about to occur.

Produce a report identifying the blocking issue.

---

# 17. Final Report

Always produce a final report.

The report should contain:

## Result

One of:

* `OPTIMIZED`
* `NOT OPTIMIZED — BELOW 30% THRESHOLD`
* `NOT OPTIMIZED — RELIABILITY RISK`
* `NOT OPTIMIZED — SEMANTIC RISK`
* `NOT OPTIMIZED — SAFETY RISK`
* `NOT OPTIMIZED — VALIDATION FAILURE`

## File

Report the original skill filename.

If optimized, report:

* optimized filename;
* backup filename.

## Token Analysis

Report:

* original estimated token count;
* optimized estimated token count;
* estimated tokens saved;
* estimated percentage reduction.

Do not falsely imply exactness if the tokenizer used for estimation differs from the target agent/model tokenizer. Label estimates appropriately.

## Changes

Summarize the meaningful changes.

Focus on:

* redundant instructions removed;
* instructions consolidated;
* structure improved;
* ambiguity clarified;
* unnecessary prose removed.

Do not provide a lengthy diff unless specifically requested.

## Preserved Guarantees

Confirm that the optimizer checked:

* purpose;
* behavior;
* safety;
* tools;
* conditions;
* exceptions;
* output requirements;
* failure handling.

## Risk Assessment

Report any remaining:

* ambiguity;
* contradiction;
* maintainability concern;
* semantic uncertainty.

## Recommendation

State whether the optimized skill should be used.

---

# 18. Do Not Hallucinate File Operations

Only claim that a backup, modification, validation, or file operation occurred if it actually occurred.

If the environment does not provide the ability to modify files or create backups:

* analyze the skill;
* provide the proposed optimization/report if appropriate;
* clearly state that the original file was not modified.

Never pretend that a backup was created.

---

# 19. Agent-Agnostic Design

Do not assume a particular agent framework unless the input skill explicitly depends on one.

The optimizer may recognize framework-specific syntax, frontmatter, tool names, or conventions, but must preserve them.

Do not convert a skill into another framework's format.

Do not remove framework-specific instructions merely because they are unfamiliar.

---

# 20. Core Principle

The optimizer is not rewarded for making a skill as short as possible.

It is rewarded for making a skill:

**smaller where safely possible, clearer where useful, more reliable where ambiguity exists, and behaviorally equivalent to the original.**

When optimization and semantic fidelity conflict:

**semantic fidelity wins.**

When optimization and safety conflict:

**safety wins.**

When optimization and reliability conflict:

**reliability wins.**

When the improvement is less than 30%:

**make no change.**
