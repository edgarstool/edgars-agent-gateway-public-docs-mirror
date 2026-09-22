# STATUS

**Verified:** 2026-09-22  
**Phase:** live MCP + skeleton HTTP gateway + legacy entry placeholder

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
  - Worker responds and `/health` -> HTTP 200
  - health reports `stage=skeleton`
  - `/v1/tools`, `/openapi.json`, and `/version` -> HTTP 404
  - public HTTP/OpenAPI client surface is therefore **not currently accepted as live**

## Interpretation

Older snapshots in this repository that say the MCP Portal is live at
`entry.edgars.tools/mcp` or that the OpenAPI tool surface is live at
`api.edgars.tools` are stale relative to the verification above.

No secret, DNS, route, OAuth, Access, or Worker deployment change is implied by this documentation correction.
