# Qualixar OS — Official Plugin & Skill Registry

The official registry for [Qualixar OS](https://github.com/qualixar/qualixar-os) plugins and skills.

## What's Here

- **10 Official Plugins** — Production-ready tools for web search, GitHub, file operations, code execution, databases, web crawling, Slack, email, image generation, and API connectivity.
- **15 Official Skills** — Pre-built agent team workflows for code review, research, data analysis, content writing, security auditing, and more.

## For Users

Qualixar OS automatically fetches this registry. Browse and install from the **Marketplace** tab in the dashboard:

```bash
# Start Qualixar OS
npx qualixar-os

# Open dashboard → Marketplace tab → Browse & Install
```

Or via CLI:

```bash
qos marketplace search "code review"
qos marketplace install code-review-pipeline
```

## For Plugin Developers

Want to publish your own plugin? See the [Plugin Development Guide](https://qualixar.com/docs/guides/publishing-skills.md).

### Plugin Manifest Format

Create a `skill.json` in your package root:

```json
{
  "name": "@yourorg/your-plugin",
  "version": "1.0.0",
  "description": "What your plugin does",
  "author": { "name": "Your Name", "url": "https://yoursite.com" },
  "license": "MIT",
  "category": "web-data",
  "tags": ["search", "web"],
  "tools": [
    {
      "name": "your_tool",
      "description": "What the tool does",
      "inputSchema": { "type": "object", "properties": {} }
    }
  ],
  "transport": {
    "type": "stdio",
    "command": "npx",
    "args": ["-y", "@yourorg/your-plugin"]
  }
}
```

### Submission Process

1. Fork this repository
2. Add your plugin to `plugins/<your-plugin-id>/skill.json`
3. Add an entry to `registry.json`
4. Submit a pull request
5. Official review within 48 hours

## Registry Structure

```
qos-registry/
  registry.json          # Master index (fetched by Qualixar OS)
  server.json            # MCP registry metadata
  plugins/               # Plugin manifests
    web-search/skill.json
    github-tools/skill.json
    ...
  skills/                # Skill workflow templates
    code-review-pipeline.json
    research-team.json
    ...
  LICENSE
  README.md
```

## License

Elastic License 2.0

Copyright (c) 2026 Varun Pratap Bhardwaj
