# Agent Tool Builder Skill

A Claude skill for designing tools that AI agents can call reliably. It focuses on the interface exposed to the model, including tool schemas, descriptions, input validation, error handling, and Model Context Protocol (MCP) tool design.

## What This Skill Covers

- Designing clear, unambiguous JSON schemas for tool inputs.
- Writing descriptions that help an LLM select and use the correct tool.
- Providing examples that clarify expected inputs and outputs.
- Validating arguments and handling malformed requests.
- Returning actionable errors that help an agent recover.
- Applying MCP concepts when exposing tools to agents.
- Avoiding vague descriptions, silent failures, and unnecessarily large tool sets.

## Repository Structure

- `SKILL.md`: Skill instructions, design principles, patterns, anti-patterns, and related guidance.
- `LICENSE`: MIT License for this repository.

## Core Design Principle

An agent generally interacts with a tool through its schema and description, not through the implementation details behind it. A well-implemented function can still be difficult for an agent to use if the interface is ambiguous. Clear names, precise parameter definitions, useful examples, and explicit error responses are therefore essential.

## When to Use It

Use this skill when creating function-calling tools, designing an MCP server, reviewing an agent's tool interface, or debugging repeated tool-selection and argument errors.

## Getting Started

1. Add the skill to a Claude-compatible skills environment.
2. Describe the tool's purpose and the tasks an agent must complete with it.
3. Define the input schema and document each field precisely.
4. Include examples and validation rules.
5. Design recoverable error responses and test the tool with realistic agent requests.

## License

Released under the MIT License. See [LICENSE](LICENSE) for details.
