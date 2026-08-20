name: development-planning

description: Create actionable technical implementation plans from confirmed software requirements and existing project context.

license: MIT

# Development Planning

## Purpose

Turn confirmed requirements into a concrete technical implementation plan.

The plan must be detailed enough for another development agent to execute without rediscovering the architecture or requirements.

## Prerequisite

Do not begin planning if material requirements are unresolved.

If requirements are ambiguous, return to requirements discovery.

## Workflow

```text
CONFIRMED REQUIREMENTS
  ↓
INSPECT CODEBASE
  ↓
UNDERSTAND ARCHITECTURE
  ↓
DESIGN CHANGES
  ↓
DEFINE IMPLEMENTATION STEPS
  ↓
DEFINE TESTING
  ↓
CHECK DOCUMENTATION IMPACT
  ↓
FINAL PLAN
```

## 1. Inspect the Codebase

Before creating the plan, inspect relevant:

* Source code
* Project structure
* Existing architecture
* Dependencies
* Configuration
* APIs
* Database/schema
* Tests
* Documentation
* Build and deployment configuration

Prefer extending existing patterns over introducing new ones.

## 2. Determine Technical Approach

Define:

* Components that change
* Components that are added
* Interfaces and APIs
* Data model changes
* Dependencies
* Configuration changes
* Integration points
* Error handling
* Security considerations
* Performance considerations

Do not introduce technology merely because it is familiar or preferred.

## 3. Define Implementation Steps

Each step must be actionable.

Prefer:

```text
1. Add `UserSession` model with user ID, token hash, expiration, and created-at fields.
2. Add session repository methods for creation, lookup, and revocation.
3. Add authentication middleware that validates the session.
4. Add API endpoints for login and logout.
5. Add unit and integration tests.
```

Avoid:

```text
1. Implement authentication.
2. Add tests.
```

## 4. Testing Strategy

Define tests appropriate to the change.

Consider:

* Unit tests
* Integration tests
* API tests
* End-to-end tests
* Regression tests
* Error cases
* Security cases
* Boundary conditions

Reuse existing testing frameworks and conventions.

## 5. Documentation Impact

Determine whether the change requires updates to:

* README
* API documentation
* Configuration documentation
* Architecture documentation
* User documentation
* Examples
* Changelog
* Operational documentation

Do not create documentation unnecessarily.

## 6. Risks and Decisions

Identify meaningful:

* Risks
* Dependencies
* Breaking changes
* Migration requirements
* Compatibility concerns
* Security concerns

Record important technical decisions and their reasons.

## 7. Final Plan

Use this structure:

```text
# Implementation Plan

## Objective
...

## Existing Architecture
...

## Proposed Changes
...

## Files / Components
...

## Data / API Changes
...

## Implementation Steps
1. ...
2. ...
3. ...

## Testing
...

## Documentation
...

## Risks / Considerations
...

## Acceptance Criteria
...
```

## Acceptance Criteria

Translate confirmed requirements into verifiable outcomes.

Example:

```text
- User can log in with valid credentials.
- Invalid credentials return the defined error response.
- Sessions expire after the configured duration.
- Revoked sessions cannot access protected endpoints.
- Authentication tests pass.
```

## Constraints

* Do not implement code unless explicitly instructed to proceed beyond planning.
* Do not invent requirements.
* Do not ignore existing architecture without justification.
* Do not introduce unnecessary technologies.
* Do not produce vague implementation steps.
* Do not claim a plan has been validated by tests when no implementation exists.
* Do not hide unresolved technical decisions.

## Completion

Use:

```text
STATUS: PLAN READY
REQUIREMENTS: confirmed
IMPLEMENTATION STEPS: <count>
TESTING: defined
DOCUMENTATION IMPACT: assessed
BLOCKERS: none
```

The primary rule:

**A developer should be able to execute the plan without having to rediscover what the planner already learned.**
