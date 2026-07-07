# Client Connection Pack

## Gateway current status

- API base: `https://api.edgars.tools`
- MCP Portal: `https://entry.edgars.tools/mcp`
- Worker: `edgars-agent-gateway-api`
- Custom domain: `api.edgars.tools`
- Current Version ID: `5b9f2313-6e34-4a63-9936-9a9c6afef31b`
- Public smoke: passed
- Read-only public endpoints: no secrets required for current API surface

## Public HTTP/OpenAPI entry

- OpenAPI schema: `https://api.edgars.tools/openapi.json`
- Tool execution: `https://api.edgars.tools/v1/tools/*`
- Health: `https://api.edgars.tools/health`
- Version: `https://api.edgars.tools/version`

## MCP entry

- MCP Portal: `https://entry.edgars.tools/mcp`
- Use this for MCP-capable clients.
- Do NOT confuse `api.edgars.tools` with MCP Portal.

## Client matrix

| client type | recommended entry | notes |
|---|---|---|
| ChatGPT Actions / Custom GPT | `https://api.edgars.tools/openapi.json` | OpenAPI only |
| Browser agents / Comet / Perplexity | `https://api.edgars.tools` | HTTP/OpenAPI |
| Cursor / Windsurf / Claude Desktop / Codex | `https://entry.edgars.tools/mcp` | MCP Portal |
| Generic HTTP clients | `https://api.edgars.tools/v1/tools/*` | POST JSON |
| Generic MCP clients | `https://entry.edgars.tools/mcp` | MCP Portal |

## Which client should use which entry

- If your client supports OpenAPI or raw HTTP: use `api.edgars.tools`
- If your client supports MCP: use `entry.edgars.tools/mcp`
- If you are unsure: start with `gateway.client_guide.get` or `gateway.docs.search`

## Known limitations

- Current API is read-only
- No secrets required for current endpoints
- No external SaaS integrations: Gmail, Notion, GitHub, Google Workspace are not connected
- No D1/KV/R2/Queues
- No Cloudflare Access policy changes in this package
- No Tunnel/VPC

## MCP Portal separate from api.edgars.tools

- `api.edgars.tools` is HTTP/OpenAPI
- `entry.edgars.tools/mcp` is MCP Portal
- They are separate surfaces
