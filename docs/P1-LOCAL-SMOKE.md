# P1 Local Smoke

## Purpose

Prove the same tool core works through both adapters:
- HTTP: `src/adapters/http/server.mjs`
- MCP stdio: `src/adapters/mcp/server.mjs`

## Scope

- Contract-only routes
- No Cloudflare changes
- No secrets
- No external API calls

## Acceptance

Run:

```powershell
cd V:\projects\edgars-agent-gateway
.\scripts\validate-p1-local.ps1
```

Expected: P0 contract + HTTP smoke + MCP smoke all pass.

## Routes / Tools

- HTTP: `/health`, `/version`, `/v1/tools`, `/v1/tools/health.check`, `/v1/tools/version.get`
- MCP: `health.check`, `version.get`

Both adapters call `src/core/tool-runner.mjs`.
