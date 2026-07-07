# Cloudflare Gateway Map

## Live gateways

- api.edgars.tools
  - Public read-only HTTP/OpenAPI gateway
  - Worker: edgars-agent-gateway-api
  - Status: live
  - Auth: none for current read-only endpoints

- entry.edgars.tools/mcp
  - MCP Portal
  - Status: live
  - Note: separate from api.edgars.tools

- mcp.edgars.tools
  - Upstream MCP endpoint
  - Status: live
  - Note: separate from api.edgars.tools

## Hard rules

- Do NOT change Access policy
- Do NOT add secrets
- Do NOT expose private APIs
