# Agent Skills

A collection of reusable skills and instructions for AI agents.

The skills in this repository are designed to be:

* **Agent-agnostic** — usable by different AI agents and frameworks.
* **Reusable** — suitable for personal, team, and automated agent workflows.
* **Practical** — focused on clear behavior and predictable results.
* **Composable** — individual skills can be used independently.

## Agents

### Requirements Analyst

Identifies and resolves material requirements and ambiguity before planning or implementation.

`agents/requirements-analyst/SOUL.md`

### Planner

Turns confirmed requirements into an actionable technical implementation plan.

`agents/planner/SOUL.md`

### Coder

Executes the approved development plan and delegates implementation to OpenCode.

`agents/coder/SOUL.md`

## Skills

### Bot-to-Bot Communication

Compact, structured communication protocol for AI agents working together.

`skills/bot-to-bot-communication/SKILL.md`

### Technical Documentation

Guidelines for scanning, updating, and maintaining codebase documentation.

`skills/technical-documentation/SKILL.md`

## Using an Agent

Agents define specific roles and responsibilities. Each agent is designed to work as part of a larger workflow.

Copy or adapt the relevant `SOUL.md` into the agent/profile system used by your AI framework.

Agents are agent-agnostic and do not require a specific model or provider.

## Using a Skill

Skills define reusable capabilities that agents can use when needed.

Copy or adapt the relevant `SKILL.md` into the skill system supported by your AI framework.

Skills are designed to be reusable across different agents and frameworks.

## Contributing

Contributions are welcome.

When adding an agent or skill:

1. Keep it agent-agnostic where possible.
2. Define clear behavior and responsibilities.
3. Avoid unnecessary verbosity.
4. Prefer deterministic instructions over vague guidance.
5. Include examples where they clarify expected behavior.
6. Do not duplicate an existing agent or skill without a clear reason.
7. Keep agents focused on roles and skills focused on reusable capabilities.
8. Update the README when adding a new agent or skill.

## Road map

For a multi-agent development system, I would keep the number of agents small and give each one a clear responsibility.

| Agent             | Team           | Purpose                                                     |
| ----------------- | -------------- | ----------------------------------------------------------- |
| **Orchestrator**  | Management     | Breaks requests into tasks, assigns agents, tracks progress |
| **Architect**     | Architecture   | System design, architecture decisions, technical tradeoffs  |
| **Developer**     | Engineering    | Implements features and fixes                               |
| **Frontend**      | Engineering    | UI, UX implementation, frontend code                        |
| **Backend**       | Engineering    | APIs, services, databases, business logic                   |
| **QA**            | Quality        | Tests, test strategy, regression testing                    |
| **Reviewer**      | Quality        | Code review, maintainability, correctness                   |
| **Security**      | Security       | Vulnerability analysis, auth, secrets, threat modeling      |
| **DevOps**        | Infrastructure | CI/CD, Docker, deployment, infrastructure                   |
| **Debugger**      | Engineering    | Investigates failures and root causes                       |
| **Performance**   | Engineering    | Profiling, optimization, scalability                        |
| **Product**       | Product        | Requirements, acceptance criteria, feature definition       |

#### Practical Team Structure

```
ORCHESTRATOR
├── ARCHITECT
├── RESEARCHER
└── PRODUCT
    └── ENGINEERING
        ├── FRONTEND
        ├── BACKEND
        └── DEVOPS
            ├── QA
            └── SECURITY
                └── REVIEWER
```

#### For example a Hermes + OpenCode setup
```
Hermes
├── Orchestrator (Agent)
├── Researcher (Agent)
└── Developer (Agent)
       └── OpenCode
            ├── Architect skill
            ├── Frontend skill
            ├── Backend skill
            ├── Testing skill
            └── Security skill
```

## License

This repository is licensed under the MIT License.
You are free to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software and associated skill content, subject to the terms of the license.


See [`LICENSE`](LICENSE) for the full license text.
