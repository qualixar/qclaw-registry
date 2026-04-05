# Q-CLAW Registry

**Global skill, plugin & tool registry for Q-CLAW Agent OS.**

Browse capabilities from your Q-CLAW dashboard. Install with one click. Your agents get new powers instantly.

## What's Here

This repository is the **universal catalog** of agent skills, tools, plugins, and topologies for Q-CLAW. Every entry in `registry.json` is browsable from the Marketplace tab in the Q-CLAW dashboard.

| Type | Count | Description |
|------|-------|-------------|
| **Agents** | 4 | Pre-configured agent roles (researcher, coder, analyst, support) |
| **Skills** | 4 | Prompt-based capabilities (summarize, translate, code review, reports) |
| **Tools** | 5 | Executable tool wrappers (web search, web crawl, file I/O, shell) |
| **Topologies** | 5 | Multi-agent execution patterns (sequential, parallel, debate, review, hierarchical) |

## For Users

**You don't need to interact with this repo directly.**

1. Open your Q-CLAW dashboard
2. Go to the **Marketplace** tab
3. Search or browse by category
4. Click **Install** on any skill
5. Your agents can use it immediately — Forge auto-selects tools

## For Developers — Publishing a Skill

Want to add your own skill to the registry? Here's how:

### 1. Create a `skill.json` manifest

```json
{
  "name": "@yourname/my-skill",
  "version": "1.0.0",
  "description": "What your skill does (max 200 chars)",
  "author": { "name": "Your Name" },
  "license": "MIT",
  "category": "code-dev",
  "tags": ["my-tag"],
  "tools": [
    {
      "name": "my_tool",
      "description": "What this tool does",
      "inputSchema": {
        "type": "object",
        "properties": {
          "input": { "type": "string" }
        },
        "required": ["input"]
      }
    }
  ],
  "transport": {
    "type": "stdio",
    "command": "npx",
    "args": ["-y", "@yourname/my-skill"]
  }
}
```

### 2. Add an entry to `registry.json`

Fork this repo, add your entry to the `plugins` array in `registry.json`:

```json
{
  "id": "my-skill",
  "name": "my-skill",
  "author": "yourname",
  "description": "What your skill does",
  "version": "1.0.0",
  "types": ["tool"],
  "category": "code-dev",
  "tags": ["my-tag"],
  "tools": ["my_tool"],
  "verified": false,
  "stars": 0,
  "installs": 0,
  "updatedAt": "2026-04-05T00:00:00Z",
  "tarballUrl": "https://registry.npmjs.org/@yourname/my-skill/-/my-skill-1.0.0.tgz",
  "sha256": "your-tarball-sha256",
  "tier": "community"
}
```

### 3. Submit a Pull Request

Open a PR to this repo. We'll review the manifest, check security, and merge.

Once merged, your skill appears in every Q-CLAW dashboard worldwide.

## Categories

| Category | ID | Description |
|----------|----|-------------|
| Web & Data | `web-data` | Search, crawl, scrape, RSS, API connectors |
| Code & Dev | `code-dev` | GitHub, code execution, linter, test runner |
| Communication | `communication` | Slack, email, Discord, webhook |
| Knowledge | `knowledge` | Vector search, document reader, DB query, RAG |
| Creative | `creative` | Image gen, video gen, TTS, diagrams |
| Enterprise | `enterprise` | CRM, project mgmt, analytics, cloud |

## Schema

See [`skill-manifest-schema.json`](./skill-manifest-schema.json) for the full JSON Schema.

## Security

All community submissions are reviewed before merge. We check for:
- No embedded secrets or API keys
- No malicious shell commands
- Valid transport configuration
- Accurate tool descriptions

Built-in and verified skills are maintained by the Qualixar team.

## License

MIT

---

Part of the [Qualixar](https://github.com/qualixar) ecosystem — AI Agent Reliability Engineering.
