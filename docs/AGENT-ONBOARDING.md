# Agent Onboarding

## Which client are you?

1. ChatGPT Actions / Custom GPT
   - Use: `https://api.edgars.tools/openapi.json`
   - Read docs: `gateway.docs.get` with `doc_id: chatgpt-actions-setup`

2. Browser agent / Comet / Perplexity
   - Use: `https://api.edgars.tools`
   - Read docs: `gateway.docs.get` with `doc_id: browser-agent-handoff`

3. Cursor / Windsurf / Claude Desktop / Codex / Generic MCP
   - Use: `https://entry.edgars.tools/mcp`
   - Read docs: `gateway.docs.get` with `doc_id: mcp-client-handoff`

4. Generic HTTP client
   - Use: `https://api.edgars.tools/v1/tools/*`
   - Read docs: `gateway.docs.get` with `doc_id: client-connection-pack`

## How to query docs

- `gateway.docs.search` with a query string
- `gateway.docs.get` with an allowlisted `doc_id`

## How to list tools

- HTTP: `GET https://api.edgars.tools/v1/tools`
- MCP: `tools/list` via `https://entry.edgars.tools/mcp`

## What you can do now

- Read gateway status
- Read gateway docs
- Discover tools and client guidance

## What you cannot do now

- Write or mutate gateway state
- Access secrets
- Call Gmail, Notion, GitHub, or Google Workspace
- Use D1/KV/R2/Queues
- Change Cloudflare Access policies
- Create Tunnel/VPC resources
