# Client Connection Pack

**Verified:** 2026-09-22

## MCP clients

Use:

`https://mcp.edgars.tools/mcp`

Current live behavior:

- unauthenticated request -> HTTP 401 Bearer challenge
- `https://mcp.edgars.tools/health` -> HTTP 200
- protected-resource metadata is available
- authorization server is provided by Descope

This is the current canonical MCP entry for MCP-capable clients.

### Knowledge MCP

Use:

`https://knowledge-mcp.edgars.tools/mcp`

It is a separate authentication-protected MCP surface for Edgar Knowledge.

## Legacy entry hostname

Do **not** currently use `https://entry.edgars.tools/mcp` as the MCP endpoint.

Live verification shows it returns the `edgars-entry` placeholder JSON on
`/mcp` and on OAuth well-known paths. Older documents that call this the
Cloudflare MCP Portal are historical/stale.

## HTTP / OpenAPI clients

`https://api.edgars.tools` is currently only a skeleton gateway:

- `/health` -> HTTP 200, service `edgars-api-gateway`, `stage=skeleton`
- `/v1/tools` -> HTTP 404
- `/openapi.json` -> HTTP 404
- `/version` -> HTTP 404

Therefore there is **no currently accepted public HTTP/OpenAPI tool surface in this package**.
Do not configure ChatGPT Actions, Custom GPT OpenAPI, browser agents, or generic HTTP
clients against those missing routes until a fresh deployment and client-level verification pass.

## Current client matrix

| client type | current entry | status |
|---|---|---|
| Cursor / Windsurf / Claude Desktop / Codex / generic MCP | `https://mcp.edgars.tools/mcp` | current canonical MCP |
| Knowledge-aware MCP client | `https://knowledge-mcp.edgars.tools/mcp` | current Knowledge MCP |
| `entry.edgars.tools/mcp` consumers | none | legacy placeholder; do not use |
| ChatGPT Actions / Custom GPT OpenAPI | none from this package | API schema route currently 404 |
| Generic HTTP/OpenAPI clients | none from this package | tool routes currently 404 |

## Revalidation rule

A previously documented gateway becomes current again only after live endpoint
verification and a real client consumption test pass.
