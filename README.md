# Gummble MCP

**Real app screens, flows, and UX copy for your AI agent.**

Gummble MCP is a remote [Model Context Protocol](https://modelcontextprotocol.io) server that
connects Claude, Cursor, Codex, Windsurf, and v0 to a curated library of **300,000+ real app
screens**, **24,000+ product flows**, and the UX microcopy inside them — from 1,500+ shipped
iOS and web apps.

Coding agents are good at producing UI, but they guess at what works. Gummble replaces
guessing with reference: before building an onboarding, paywall, empty state, or settings
screen, your agent searches how top products actually solved it.

> This repository hosts documentation and registry metadata for the hosted Gummble MCP
> server. The server itself is a managed service — there is nothing to install or run from
> this repo.

## Quick start

**Server URL:** `https://mcp.gummble.com/mcp` (Streamable HTTP, OAuth)

### Claude Code

```bash
claude mcp add --transport http --scope user gummble https://mcp.gummble.com/mcp
```

### Claude.ai / Claude Desktop

Settings → Connectors → **Add custom connector** → paste `https://mcp.gummble.com/mcp`

### Cursor

Add to `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "gummble": { "url": "https://mcp.gummble.com/mcp" }
  }
}
```

### Codex / Windsurf / other clients

See the per-client guides at [gummble.com/mcp](https://gummble.com/mcp).

On first use you'll be asked to sign in with your Gummble account (OAuth). MCP access is
included in every paid plan (from $9/month); new accounts get a 7-day free trial.

## Tools

All 12 tools are **read-only** (`readOnlyHint: true`). Gummble never modifies your files,
projects, or data.

| Tool | What it does |
|------|--------------|
| `gummble_search_screens` | Search UI screens in natural language ("paywall with annual discount toggle") |
| `gummble_search_flows` | Find complete user flows (onboarding, checkout, upgrade, cancellation) |
| `gummble_get_flow_screens` | Walk a flow step by step |
| `gummble_search_microcopy` | Search real UX copy — empty states, validation errors, paywall copy |
| `gummble_search_apps` | Look up a specific app in the library |
| `gummble_get_app` | Drill into one app's screens and flows |
| `gummble_search_patterns` | Discover UI patterns across products |
| `gummble_find_similar_screens` | Find visually similar screens to iterate on a direction |
| `gummble_get_screen_detail` | View a screen's image and metadata |
| `gummble_get_screen_details_batch` | Fetch several screens at once |
| `gummble_search_store_screenshots` | Search App Store screenshots by keyword (marketing/ASO reference) |
| `gummble_get_store_screenshots` | Get an app's App Store screenshot set |

## Try these prompts

- *"Design a paywall for my meditation app. Search Gummble for real paywall patterns first."*
- *"Show me how Duolingo onboards new users, step by step."*
- *"Rewrite my empty states using real microcopy from top fitness apps."*

## Links

- Website & docs: https://gummble.com/mcp
- Prompt guide: https://gummble.com/mcp (see "Read the prompt guide")
- Gummble MCP vs Mobbin MCP: https://gummble.com/blog/gummble-mcp-vs-mobbin-mcp
- Privacy policy: https://gummble.com/privacy
- Support: support@gummble.com or [open an issue](../../issues)
- More design MCP servers: [awesome-design-mcp](https://github.com/gummble/awesome-design-mcp)

## Registry

Published to the [official MCP Registry](https://registry.modelcontextprotocol.io) as
`com.gummble/mcp` — see [server.json](server.json).
