# edgars-agent-gateway public docs

This repository is a public documentation mirror. **Current live status wins over older phase documents.**

## Verified live entry points — 2026-09-22

- Canonical MCP: `https://mcp.edgars.tools/mcp`
  - unauthenticated request -> HTTP 401 Bearer challenge
  - health: `https://mcp.edgars.tools/health` -> HTTP 200
  - OAuth protected-resource metadata is live and points to Descope
- Knowledge MCP: `https://knowledge-mcp.edgars.tools/mcp`
  - unauthenticated request -> HTTP 401 authentication challenge
- Legacy entry shell: `https://entry.edgars.tools/mcp`
  - currently returns placeholder JSON
  - **not** the active MCP authority
- HTTP/OpenAPI gateway: `https://api.edgars.tools`
  - `/health` -> HTTP 200 and reports `stage=skeleton`
  - `/v1/tools`, `/openapi.json`, and `/version` -> HTTP 404
  - do not treat it as an accepted public client surface until those routes pass again

See `STATUS.md` and `docs/CLIENT-CONNECTION-PACK.md` for the current handoff.
Older documents may describe superseded portal/API phases and should be read as historical unless re-verified.
