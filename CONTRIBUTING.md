# Contributing to Qualixar OS Registry

Thank you for contributing agent capabilities to Qualixar OS!

## How to Submit a Plugin or Skill

1. **Fork** this repository
2. For plugins: create `plugins/<your-plugin-id>/skill.json`
3. For skills: create `skills/<your-skill-id>.json`
4. **Add** an entry to the `plugins` array in `registry.json`
5. **Submit** a Pull Request

## Plugin Manifest Requirements

- `name` must be scoped: `@yourname/skill-name` or `yourorg/skill-name`
- `version` must follow semver: `X.Y.Z`
- `description` must be under 200 characters
- `tools` array must have at least 1 tool with a valid `inputSchema`
- `category` must be one of: `web-data`, `code-dev`, `communication`, `knowledge`, `creative`, `enterprise`
- `transport` must specify either `stdio` (with `command`) or `streamable-http` (with `url`)

## Skill Template Requirements

- `topology` must be one of: `sequential`, `parallel`, `debate`, `dag`, `hierarchical`, `mesh`, `star`, `circular`, `grid`, `forest`, `mixture_of_agents`, `maker`
- `agents` array must have detailed system prompts (5+ lines each)
- `workflow` must have valid `nodes` and `edges`
- `examples` must have 2+ realistic input/output pairs

## What We Check

- No embedded API keys, tokens, or secrets
- No destructive shell commands in transport config
- Valid JSON Schema for all tool inputSchemas
- Description accurately reflects what the plugin/skill does
- Category and tags are appropriate

## Tiers

| Tier | Meaning |
|------|---------|
| `verified` | Reviewed and trusted. Qualixar stamp of approval. |
| `community` | Submitted by community. Reviewed before merge. |

## Review Time

We aim to review all PRs within 48 hours.

## License

By contributing, you agree that your contributions will be licensed under the Elastic License 2.0.

---

Part of the [Qualixar](https://github.com/qualixar) ecosystem.
