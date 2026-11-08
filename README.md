# claude-agent-tool-builder-skill

A Claude Code skill for designing reliable tools that AI agents can discover, select, call, and recover from.

## Overview

Agents interact with tools through their names, descriptions, schemas, and returned results. A tool can be implemented correctly and still be difficult for an agent to use if its interface is ambiguous or its errors are unhelpful.

This skill focuses on tool contracts from schema design through validation, execution, error handling, and MCP integration.

## Main Capabilities

- Design clear tool names and descriptions.
- Define JSON Schema input contracts.
- Document required and optional parameters.
- Provide examples of valid calls.
- Validate tool arguments.
- Return structured, actionable errors.
- Design safe side-effect boundaries.
- Build tools for function calling and MCP servers.
- Reduce unnecessary tool complexity.
- Improve agent tool-selection reliability.

## Core Design Principles

### Make the Tool's Purpose Obvious

A name and description should communicate exactly what the tool does and when it should be used.

### Keep Schemas Precise

Define types, constraints, defaults, enumerations, and required fields. Avoid ambiguous free-form parameters when a structured schema is possible.

### Validate at the Boundary

Do not trust model-generated arguments. Validate types, ranges, identifiers, permissions, and business rules before execution.

### Return Useful Results

Provide structured output that clearly distinguishes success, empty results, validation errors, and execution failures.

### Make Side Effects Explicit

Document whether a tool reads, writes, deletes, publishes, or triggers an external action. Require approval where appropriate.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-agent-tool-builder-skill.git ~/.claude/skills/agent-tool-builder
```

## Usage

Invoke the skill when designing agent tools or MCP interfaces:

```text
/agent-tool-builder
```

Provide the tool's purpose, expected inputs, output format, runtime, permissions, and failure conditions.

## Recommended Workflow

1. Define the task the tool should perform.
2. Identify the smallest useful interface.
3. Choose a clear tool name.
4. Write a concise, discriminative description.
5. Define the input schema.
6. Add validation and authorization checks.
7. Design structured success and error outputs.
8. Document side effects and idempotency.
9. Test valid, invalid, and adversarial inputs.
10. Evaluate whether an agent can select and use the tool correctly.

## MCP Considerations

When exposing tools through MCP, define stable names, input schemas, and clear result structures. Keep server capabilities focused and document any resources or prompts that complement the tools.

## Tool Quality Checklist

- Tool name is unambiguous.
- Description explains when to use it.
- Parameters have clear types and constraints.
- Required fields are explicit.
- Inputs are validated server-side.
- Errors explain how to recover.
- Side effects are documented.
- Permissions are checked.
- Outputs are structured and predictable.
- Tool behavior is tested with realistic agent calls.

## Repository Contents

- `SKILL.md`: Main tool design and MCP guidance.
- `README.md`: Design principles, workflow, and checklist.

## Practical Principle

The model does not see your implementation. It sees the interface you expose. Invest in the schema, description, and error behavior as carefully as the underlying function.
