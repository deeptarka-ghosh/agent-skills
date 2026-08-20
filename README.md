# Agent Skills

A collection of reusable skills and instructions for AI agents.

The skills in this repository are designed to be:

* **Agent-agnostic** — usable by different AI agents and frameworks.
* **Reusable** — suitable for personal, team, and automated agent workflows.
* **Practical** — focused on clear behavior and predictable results.
* **Composable** — individual skills can be used independently.

### Skills

#### Bot-to-Bot Communication

Compact, unambiguous communication protocol for AI agents working together.

`skills/bot-to-bot-communication/SKILL.md`

#### Technical Documentation

Guidelines for scanning, updating, and maintaining codebase documentation.

`skills/technical-documentation/SKILL.md`

## Using a Skill

Copy the required skill into the skill directory supported by your agent, or reference it according to the agent/framework's skill mechanism.

Skills are intentionally written without depending on a specific AI agent, model, provider, or orchestration framework.

## Contributing

Contributions are welcome.

When adding a skill:

1. Keep it agent-agnostic where possible.
2. Define clear behavior and constraints.
3. Avoid unnecessary verbosity.
4. Prefer deterministic instructions over vague guidance.
5. Include examples where they clarify expected behavior.

## License

This repository is licensed under the MIT License.

You are free to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software and associated skill content, subject to the terms of the license.

See [`LICENSE`](LICENSE) for the full license text.
