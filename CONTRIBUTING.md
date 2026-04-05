# Contributing to Q-CLAW Registry

Thank you for contributing agent capabilities to Q-CLAW!

## How to Submit a Skill

1. **Fork** this repository
2. **Create** a `skill.json` manifest for your skill (see README for schema)
3. **Add** an entry to the `plugins` array in `registry.json`
4. **Submit** a Pull Request

## Requirements

- `name` must be scoped: `@yourname/skill-name` or `yourorg/skill-name`
- `version` must follow semver: `X.Y.Z`
- `description` must be under 200 characters
- `tools` array must have at least 1 tool with a valid `inputSchema`
- `category` must be one of: `web-data`, `code-dev`, `communication`, `knowledge`, `creative`, `enterprise`
- `transport` must specify either `stdio` (with `command`) or `streamable-http` (with `url`)

## What We Check

- No embedded API keys, tokens, or secrets
- No destructive shell commands in transport config
- Valid JSON Schema for all tool inputSchemas
- Description accurately reflects what the skill does
- Category and tags are appropriate

## Tiers

| Tier | Meaning |
|------|---------|
| `builtin` | Ships with Q-CLAW. Maintained by Qualixar. |
| `verified` | Reviewed and trusted. Qualixar stamp of approval. |
| `community` | Submitted by community. Reviewed before merge. |

## Review Time

We aim to review all PRs within 48 hours. Complex skills may take longer.

## Questions?

Open an issue in this repository.
