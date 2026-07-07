# P0 Contract

## Acceptance criteria

- `src/core/tool-registry.json` exists
- `schemas/openapi.p0.json` exists
- Routes are contract-only; no Cloudflare production changes
- No secrets in repo
- No external API calls

## Verification

Run in PowerShell:

```powershell
cd V:\projects\edgars-agent-gateway
.\scripts\validate-p0-contract.ps1
```

Expected: all checks PASS.

## Scope boundary

This phase does not deploy anything. It only defines the shared contract between adapters.
