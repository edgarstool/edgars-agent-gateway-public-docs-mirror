# P2A Gateway Capabilities

## Purpose

Extend the gateway from fake status tools to real low-risk self-description tools:
- `gateway.capabilities.list`
- `gateway.client_guide.get`

These let any agent discover:
- Which adapters are enabled
- What public endpoints are targeted
- Whether the gateway is deployed
- Which adapter a specific client should use

## New tools

- `gateway.capabilities.list`
- `gateway.client_guide.get`

## Client type mapping

| client_type | adapter | recommended entry |
|---|---|---|
| cursor | mcp | https://entry.edgars.tools/mcp |
| windsurf | mcp | https://entry.edgars.tools/mcp |
| codex | mcp | https://entry.edgars.tools/mcp |
| claude_desktop | mcp | https://entry.edgars.tools/mcp |
| chatgpt_actions | http_openapi | https://api.edgars.tools/openapi.json |
| claude_web | browser_or_http | https://api.edgars.tools or admin.edgars.tools when deployed |
| perplexity_comet | browser_or_http | https://api.edgars.tools or admin.edgars.tools when deployed |
| browser_agent | browser_or_http | https://admin.edgars.tools or https://api.edgars.tools when deployed |
| generic_mcp | mcp | https://entry.edgars.tools/mcp |
| generic_openapi | http_openapi | https://api.edgars.tools/openapi.json |

## Scope

- Local-only validation
- Not deployed
- Does not modify Cloudflare
- Does not touch secrets
- Does not call external APIs

## Acceptance

Run:
```powershell
cd V:\projects\edgars-agent-gateway
.\scripts\validate-p2a-local.ps1
```

Expected:
- P0 contract passed
- HTTP smoke passed
- MCP smoke passed
- `gateway.capabilities.list` returns adapter info
- `gateway.client_guide.get` returns `http_openapi` for `chatgpt_actions`
- `gateway.client_guide.get` returns `mcp` for `cursor`
