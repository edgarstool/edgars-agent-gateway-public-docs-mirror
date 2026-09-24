# STATUS

**Verified:** 2026-09-25  
**Phase:** live MCP + live read-only HTTP/OpenAPI gateway + legacy entry placeholder

## Current live state

- `https://mcp.edgars.tools/mcp`
  - canonical EDGAR MCP endpoint
  - unauthenticated request -> HTTP 401 Bearer challenge
  - `/health` -> HTTP 200
  - OAuth protected-resource metadata -> Descope authorization server
- `https://knowledge-mcp.edgars.tools/mcp`
  - canonical Knowledge MCP endpoint
  - unauthenticated request -> HTTP 401
- `https://entry.edgars.tools/mcp`
  - legacy/reserved entry shell
  - currently returns placeholder JSON, not MCP protocol/auth behavior
- `https://api.edgars.tools`
  - canonical read-only HTTP/OpenAPI gateway
  - Worker: `edgars-api-gateway`
  - production version: `fd1a5104-0087-40ac-afdf-319f64517df8`
  - `/health` -> HTTP 200
  - `/version` -> HTTP 200 with `deployed=true`
  - `/v1/tools` -> HTTP 200 with 11 tools
  - `/openapi.json` -> HTTP 200, OpenAPI 3.1.0 with 12 paths
  - real POST tool calls and docs search pass
  - `gateway.client_guide.get(cursor)` -> `https://mcp.edgars.tools/mcp`

## Interpretation

The HTTP/OpenAPI client surface is accepted as live again. Older snapshots that
call `api.edgars.tools` a skeleton are stale relative to this verification.

Older snapshots that call `entry.edgars.tools/mcp` the active MCP Portal also
remain stale; canonical MCP is `mcp.edgars.tools/mcp`.
