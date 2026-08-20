# Requirements Discovery

## Purpose

Determine exactly what needs to be built before technical planning or implementation begins.

The goal is not to ask as many questions as possible. The goal is to eliminate **material ambiguity** that could cause incorrect implementation, architectural rework, or unmet requirements.

## Mandatory Gate

Do not proceed to planning or implementation while material requirements remain unresolved.

## Workflow

```text
REQUEST
  ↓
INSPECT CONTEXT
  ↓
IDENTIFY AMBIGUITIES
  ↓
ASK QUESTIONS
  ↓
UPDATE REQUIREMENTS
  ↓
RECHECK
  ↓
REQUIREMENTS CONFIRMED
```

## 1. Understand the Request

Extract:

* Goal
* Users
* Required behavior
* Features
* Constraints
* Expected outcome
* Explicit technical requirements

Do not infer requirements that are not supported by the request or project context.

## 2. Inspect Existing Context

Before asking questions, inspect relevant available information, including:

* Existing source code
* Repository structure
* README and documentation
* Configuration
* Existing architecture
* Dependencies
* APIs
* Database/schema
* Tests
* Existing project conventions
* Previous decisions

Use existing information instead of asking the user to repeat it.

## 3. Identify Ambiguity

Check for missing or unclear requirements affecting:

* Scope
* User behavior
* UI/UX
* Data
* APIs
* Authentication and authorization
* Integrations
* Error handling
* Security
* Performance
* Compatibility
* Deployment
* Testing
* Documentation
* Acceptance criteria

Only ask questions that can materially affect the result.

## 4. Ask Questions

Ask concise, specific questions.

Group related questions when practical.

Prefer:

```text
1. Should users authenticate with email/password, OAuth, or both?
2. Should users have different roles?
3. Should tasks be visible to all users or only their owner?
```

Avoid vague questions such as:

```text
How should authentication work?
```

Do not overwhelm the user with unnecessary questions if the project already establishes the answer.

## 5. Track Decisions

As answers are received, update the requirements.

Distinguish between:

* Confirmed
* Existing project convention
* Explicit assumption
* Unknown
* Blocked

Never silently convert an assumption into a requirement.

## 6. Recheck After Answers

After receiving answers, reassess the requirements.

New answers may introduce additional ambiguity.

Continue asking questions until:

* Material requirements are resolved.
* Remaining unknowns cannot materially affect implementation.
* Any necessary assumptions are explicitly identified.

## 7. Requirements Summary

Before planning, provide a concise summary:

```text
REQUIREMENTS

GOAL:
...

USERS:
...

FEATURES:
...

CONSTRAINTS:
...

TECHNICAL REQUIREMENTS:
...

ASSUMPTIONS:
...

OPEN QUESTIONS:
none
```

If user confirmation is required by the surrounding workflow, stop here and request confirmation.

## Constraints

* Do not implement code.
* Do not create the technical implementation plan.
* Do not make architectural decisions unless explicitly required to resolve a requirement.
* Do not invent missing information.
* Do not repeatedly ask questions that have already been answered.
* Do not ask about trivial implementation details that can safely be decided during planning.
* Do not treat personal preference as a requirement unless the user confirms it.

## Completion

Use:

```text
STATUS: REQUIREMENTS READY
OPEN QUESTIONS: none
ASSUMPTIONS: <list or none>
NEXT: development planning
```

The primary rule:

**Do not optimize for the number of questions. Optimize for eliminating material ambiguity.**
