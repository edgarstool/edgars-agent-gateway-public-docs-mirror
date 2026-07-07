# Client Matrix

## MCP-capable clients

- Cursor
- Claude Code / Claude Desktop
- Windsurf
- Codex
- Comet
- Cursor Cloud Agents
- Factory.ai Droid
- ChatGPT (Custom GPTs with MCP connector)
- Perplexity
- Lovable
- Browser agents with MCP support

Entry point: https://entry.edgars.tools/mcp

Auth: Cloudflare Access Managed OAuth or mcp-remote stdio proxy with service token.

## Web Chat AI / Actions clients

- ChatGPT web (Custom GPT Actions)
- Claude web
- Perplexity
- Lovable
- Browser agents without MCP support

Entry point: https://api.edgars.tools/v1/tools/*
OpenAPI schema: https://api.edgars.tools/openapi.json

Auth: Bearer token or OAuth 2.0.

## Browser agents

- admin.edgars.tools (management UI)
- api.edgars.tools (tool execution)

Auth: Cloudflare Access (human) or API Bearer token (machine).
