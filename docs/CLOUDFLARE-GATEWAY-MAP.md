# Cloudflare Gateway Map

**Verified:** 2026-09-25

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

- `api.edgars.tools`
  - Worker: `edgars-api-gateway`
  - Role: canonical read-only HTTP/OpenAPI gateway
  - Production version: `fd1a5104-0087-40ac-afdf-319f64517df8`
  - `/health`, `/version`, `/v1/tools`, `/openapi.json`: HTTP 200
  - OpenAPI: 3.1.0 / 12 paths
  - Real POST tool invocation: PASS

## Reserved / non-canonical surface

- `entry.edgars.tools`
  - Worker: `edgars-entry`
  - Role: legacy / reserved entry shell
  - Status: placeholder
  - `/mcp` currently returns placeholder JSON
  - Do not treat as active MCP authority

## Documentation rule

Live provider state + consumption-boundary checks override older phase documents.
