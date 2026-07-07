# MCP Client Handoff

## MCP entry

- `https://entry.edgars.tools/mcp`

## Supported clients

- Cursor
- Windsurf
- Claude Desktop
- Codex
- Generic MCP clients using stdio/HTTP MCP transport

## Important distinction

- `api.edgars.tools` is HTTP/OpenAPI, not MCP Portal.
- `entry.edgars.tools/mcp` is MCP Portal, not OpenAPI.

## Notes

- Use MCP Portal for tool listing and tool calls via MCP protocol.
- Use HTTP API for OpenAPI or raw HTTP clients.
