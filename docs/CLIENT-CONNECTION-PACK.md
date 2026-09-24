# Client Connection Pack

**Verified:** 2026-09-25

## MCP clients

Use:

`https://mcp.edgars.tools/mcp`

Current live behavior:

- unauthenticated request -> HTTP 401 Bearer challenge
- `https://mcp.edgars.tools/health` -> HTTP 200
- protected-resource metadata is available
- authorization server is provided by Descope

### Knowledge MCP

Use:

`https://knowledge-mcp.edgars.tools/mcp`

## Legacy entry hostname

Do **not** use `https://entry.edgars.tools/mcp` as the canonical MCP endpoint.
It currently returns the `edgars-entry` placeholder JSON.

## HTTP / OpenAPI clients

Use:

- API base: `https://api.edgars.tools`
- OpenAPI schema: `https://api.edgars.tools/openapi.json`
- Tool catalog: `https://api.edgars.tools/v1/tools`
- Tool invocation: `POST https://api.edgars.tools/v1/tools/<tool-id>`

Live acceptance on 2026-09-25:

- `/health` -> HTTP 200
- `/version` -> HTTP 200 with `deployed=true`
- `/v1/tools` -> HTTP 200 with 11 tools
- `/openapi.json` -> HTTP 200, OpenAPI 3.1.0, 12 paths
- real `POST /v1/tools/health.check` -> HTTP 200
- docs search -> PASS
- Cursor client guide -> `https://mcp.edgars.tools/mcp`

## Current client matrix

| client type | current entry | status |
|---|---|---|
| Cursor / Windsurf / Claude Desktop / Codex / generic MCP | `https://mcp.edgars.tools/mcp` | canonical MCP |
| Knowledge-aware MCP client | `https://knowledge-mcp.edgars.tools/mcp` | canonical Knowledge MCP |
| ChatGPT Actions / Custom GPT OpenAPI | `https://api.edgars.tools/openapi.json` | live accepted |
| Browser / generic HTTP client | `https://api.edgars.tools` | live accepted |
| `entry.edgars.tools/mcp` consumers | none | legacy placeholder |

## Revalidation rule

A documented gateway remains current only while live endpoint verification and a
real client consumption test continue to pass.
