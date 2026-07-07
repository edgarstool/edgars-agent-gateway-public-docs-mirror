# ChatGPT Actions Setup

## Entry point

- OpenAPI schema: `https://api.edgars.tools/openapi.json`

## Authentication

- None required for current read-only endpoints.

## Test tools

- `health.check`
- `gateway.docs.search`
- `gateway.client_guide.get`

## Example

```json
POST https://api.edgars.tools/v1/tools/gateway.docs.search
Content-Type: application/json

{
  "query": "Client Matrix"
}
```

## Current scope

- Read-only only
- Does not connect Gmail
- Does not connect Notion
- Does not connect GitHub
- Does not connect Google Workspace
- Does not expose private user data
