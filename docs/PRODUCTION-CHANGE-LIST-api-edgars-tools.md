# Production Change List: api.edgars.tools

## Change 1: Deploy Cloudflare Worker
- Worker name: `edgars-agent-gateway-api`
- Entry: `src/adapters/cloudflare-worker/worker.mjs`
- Generated assets:
  - `src/adapters/cloudflare-worker/registry.generated.mjs`
  - `src/adapters/cloudflare-worker/openapi.generated.mjs`

## Change 2: Attach Custom Domain
- Custom domain: `api.edgars.tools`

## What this does NOT change
- Does NOT modify `entry.edgars.tools`
- Does NOT modify MCP Portal
- Does NOT modify Cloudflare Access policies
- Does NOT create tunnels or VPCs
- Does NOT bind D1/KV/R2/Queues
- Does NOT read or create secrets
- Does NOT call external APIs

## Rollback options
1. `wrangler rollback` from dashboard or CLI
2. Remove custom domain `api.edgars.tools` from Worker settings
3. Disable the route without deleting the Worker

## Verification commands
- Local validation:
  - `.\scripts\validate-p2a-local.ps1`
- Local worker smoke:
  - `.\scripts\smoke-worker-local.ps1`
- Deploy:
  - `npm run deploy:worker`
- Public smoke (after deploy + DNS):
  - `.\scripts\smoke-public-readonly.ps1`

## Public endpoints after deploy
- `GET https://api.edgars.tools/health`
- `GET https://api.edgars.tools/version`
- `GET https://api.edgars.tools/v1/tools`
- `GET https://api.edgars.tools/openapi.json`
- `POST https://api.edgars.tools/v1/tools/health.check`
- `POST https://api.edgars.tools/v1/tools/version.get`
- `POST https://api.edgars.tools/v1/tools/gateway.capabilities.list`
- `POST https://api.edgars.tools/v1/tools/gateway.client_guide.get`

## Notes
- Read-only public gateway
- No auth required
- No secrets involved
- No external service mutations
