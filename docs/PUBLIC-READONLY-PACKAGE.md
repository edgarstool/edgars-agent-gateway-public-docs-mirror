# Public Read-only Package

## Purpose

Publish a read-only HTTP/OpenAPI gateway for `edgars-agent-gateway` via Cloudflare Worker.

## Status

- Deployed: true
- Worker: `edgars-agent-gateway-api`
- Custom Domain: `api.edgars.tools`
- Current Version ID: `8dcca713-5430-4ac2-8259-0c7fb2c0fd7f`
- Public smoke: VALIDATION PASSED
- Note: `api.edgars.tools` was previously attached to `edgars-api` and has been repointed to `edgars-agent-gateway-api`.

## Public endpoints

- `GET https://api.edgars.tools/health`
- `GET https://api.edgars.tools/version`
- `GET https://api.edgars.tools/v1/tools`
- `GET https://api.edgars.tools/openapi.json`
- `POST https://api.edgars.tools/v1/tools/health.check`
- `POST https://api.edgars.tools/v1/tools/version.get`
- `POST https://api.edgars.tools/v1/tools/gateway.capabilities.list`
- `POST https://api.edgars.tools/v1/tools/gateway.client_guide.get`

## Allowed production changes

1. Deploy Worker `edgars-agent-gateway-api`
2. Attach custom domain `api.edgars.tools`

## Do NOT change

- Do NOT modify `entry.edgars.tools`
- Do NOT modify MCP Portal
- Do NOT modify Cloudflare Access policies
- Do NOT create secrets
- Do NOT bind D1/KV/R2/Queues
- Do NOT call external SaaS

## Local smoke

```powershell
cd V:\projects\edgars-agent-gateway
.\scripts\smoke-worker-local.ps1
```

## Deploy

```powershell
cd V:\projects\edgars-agent-gateway
npm run build:worker
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

## Known limits

- No auth
- Read-only only
- No external tool execution
- No secrets
- MCP Portal not included
