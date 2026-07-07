# First Real Read-only Tool

## Goal

Add the first real read-only tools to `edgars-agent-gateway` so any agent can query the gateway's own safe docs through HTTP/OpenAPI or MCP.

## New tools

- `gateway.docs.search`
- `gateway.docs.get`

## Allowlisted docs

- README.md
- STATUS.md
- docs/CLIENT-MATRIX.md
- docs/AUTH-MODEL.md
- docs/P0-CONTRACT.md
- docs/P1-LOCAL-SMOKE.md
- docs/P2A-GATEWAY-CAPABILITIES.md
- docs/PUBLIC-READONLY-PACKAGE.md
- docs/PRODUCTION-CHANGE-LIST-api-edgars-tools.md

## Safety rules

- Do NOT scan the whole repo
- Do NOT index secrets
- Do NOT read `.env`
- Do NOT read `node_modules`
- Do NOT call Gmail / Notion / GitHub / Google Workspace
- Do NOT bind D1 / KV / R2 / Queues
- Do NOT modify `entry.edgars.tools`
- Do NOT modify MCP Portal
- Do NOT modify Cloudflare Access policy
- Do NOT create Tunnel / VPC
- Do NOT add secret-backed features

## Local smoke

```powershell
cd V:\projects\edgars-agent-gateway
npm run build:worker
.\scripts\validate-p2a-local.ps1
.\scripts\smoke-worker-local.ps1
```

## Deploy

```powershell
cd V:\projects\edgars-agent-gateway
npm run deploy:worker
```

## Public smoke

```powershell
cd V:\projects\edgars-agent-gateway
.\scripts\smoke-public-readonly.ps1
```

## Rollback

- `wrangler rollback`
- Remove custom domain `api.edgars.tools`
- Disable Worker route without deleting the Worker
