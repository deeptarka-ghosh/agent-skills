# Bot-to-Bot Communication

## Purpose

Use this skill when communicating with other AI agents through shared chats, message queues, agent-to-agent channels, or other machine-mediated communication.

The goal is to communicate efficiently while preserving meaning, context, and unambiguous interpretation.

## Core Principle

Optimize communication in this order:

1. Correctness
2. Unambiguous meaning
3. Actionability
4. Compactness
5. Token efficiency

Never reduce message length if doing so makes the meaning ambiguous.

## Default Communication Style

Use concise technical language.

Remove:

* Greetings
* Pleasantries
* Filler
* Repetition
* Unnecessary explanations
* Information already known to the recipient

Prefer:

```text
STATUS: implementation complete
TESTS: 42 passed
BLOCKED: none
NEXT: deploy to staging
```

Over verbose prose containing the same information.

## Structured Messages

Use labels when they improve clarity:

```text
TASK:
STATUS:
RESULT:
BLOCKED:
NEED:
NEXT:
DECISION:
QUESTION:
```

Do not use labels when they provide no additional value.

## Requests

Use direct requests:

```text
NEED: database schema from backend agent
```

Avoid unnecessary politeness or conversational padding.

## Status Updates

Include only information relevant to other agents:

```text
STATUS: API implementation 80%
BLOCKED: waiting for auth interface
NEXT: integrate auth after interface received
```

## Results

Report the result and relevant evidence:

```text
RESULT: login endpoint implemented
TESTS: 18 passed
FAILURES: 0
```

Do not include implementation details unless another agent needs them.

## Questions

Make questions precise:

```text
QUESTION: should refresh tokens be stored server-side or remain stateless?
```

Include the minimum context required to answer correctly.

## Decisions

Record important decisions explicitly:

```text
DECISION: use PostgreSQL for persistent storage
REASON: existing infrastructure and transaction requirements
```

## Errors and Blockers

Never hide failures, uncertainty, or missing information.

```text
BLOCKED: repository unavailable
CAUSE: repository path not accessible
NEED: valid repository path
```

If uncertain, say so:

```text
UNCERTAIN: deployment appears successful; production health check not verified
```

## Completion

When work is complete, provide a concise completion message:

```text
STATUS: DONE
RESULT: user authentication implemented
TESTS: 31 passed
FILES: auth/, tests/auth/
```

## Avoid Ambiguous Compression

Do not compress language to the point where the recipient must guess the meaning.

Avoid:

```text
auth db done need api?
```

Prefer:

```text
AUTH: database implementation complete
NEED: API contract confirmation
```

## Context Management

Do not repeat information already established in the conversation unless:

* it prevents ambiguity;
* the information has changed;
* the recipient may not have access to the previous context;
* it is necessary for the recipient to perform the requested action.

## Human Communication

When communicating with a human, or when explicitly asked for an explanation, use normal English.

Example:

```text
Human: Why did the tests fail?

Agent: 3 integration tests failed because the test database was unavailable.
The application code passed the unit tests.
```

Do not use compressed bot-to-bot syntax when it would reduce readability for a human.

## Agent-to-Agent Communication

Assume the recipient is another capable agent.

Do not explain basic concepts unless:

* requested;
* required for correctness;
* the recipient lacks required context.

Focus on information needed to make a decision or perform an action.

## Information Integrity

Never invent missing information to make a message shorter.

If information is unavailable:

```text
UNKNOWN: deployment status
```

If verification has not occurred:

```text
UNVERIFIED: database migration completed
```

Distinguish clearly between:

* known
* inferred
* assumed
* unknown
* verified

## Message Priority

When multiple pieces of information are included, put the most actionable information first.

Example:

```text
BLOCKED: deployment failed
CAUSE: missing production environment variable DATABASE_URL
NEED: configure DATABASE_URL
```

## Default Rule

Communicate like a concise technical teammate:

**State what happened, what is needed, what is blocked, and what happens next. Omit everything else.**
