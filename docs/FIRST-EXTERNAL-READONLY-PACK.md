# First External Read-only Pack

## Decision

This pack intentionally does NOT implement GitHub raw fetch yet.

## Why

- A safe public GitHub mirror is not yet confirmed for this repo.
- The repo is not verified as public with a stable raw URL suitable for unauthenticated fetch.
- Hard-coding external fetch without a confirmed public mirror risks coupling to a moving target and could leak assumptions.

## Delivered instead

- `docs/snapshot-manifest.json`
- Snapshot manifest is indexed in `gateway.docs.search` and `gateway.docs.get`.
- External read-only docs fetching can be enabled after a public mirror strategy is chosen.

## Current constraint reminder

- No secrets
- No private GitHub API
- No OAuth
- No token-based sources
- No SaaS integrations
- No D1/KV/R2/Queues
- No Tunnel/VPC
