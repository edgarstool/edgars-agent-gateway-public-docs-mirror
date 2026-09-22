# Cloudflare Gateway Map

**Verified:** 2026-09-22

## Current canonical gateways

- `mcp.edgars.tools`
  - Role: canonical EDGAR MCP endpoint
  - MCP path: `/mcp`
  - Status: live
  - Unauthenticated behavior: HTTP 401 Bearer challenge
  - Health: HTTP 200
  - OAuth resource metadata: live, backed by Descope

- `knowledge-mcp.edgars.tools`
  - Role: canonical Knowledge MCP endpoint
  - MCP path: `/mcp`
  - Status: live / authentication-protected
  - Unauthenticated behavior: HTTP 401

## Reserved / non-canonical surfaces

- `entry.edgars.tools`
  - Worker: `edgars-entry`
  - Role: legacy / reserved entry shell
  - Status: placeholder
  - `/mcp` currently returns placeholder JSON
  - Do not treat as active MCP Portal authority

- `api.edgars.tools`
  - Service: `edgars-api-gateway`
  - Role: HTTP gateway skeleton
  - `/health`: HTTP 200, `stage=skeleton`
  - `/v1/tools`: HTTP 404
  - `/openapi.json`: HTTP 404
  - `/version`: HTTP 404
  - Do not advertise as a working OpenAPI/tool-execution surface until re-verified

## Documentation rule

Live provider state + consumption-boundary checks override older phase documents.
Historical references to `entry.edgars.tools/mcp` as the active portal or to
`api.edgars.tools` as a complete public OpenAPI gateway are not current authority.
