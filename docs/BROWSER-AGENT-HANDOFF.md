# Browser Agent Handoff

## Start here

Open:

- `https://api.edgars.tools/health`
- `https://api.edgars.tools/v1/tools`
- `https://api.edgars.tools/openapi.json`

## Test tools

POST `https://api.edgars.tools/v1/tools/gateway.docs.search`

```json
{ "query": "Client Matrix" }
```

POST `https://api.edgars.tools/v1/tools/gateway.client_guide.get`

```json
{ "client_type": "browser_agent" }
```

## Prohibited actions

- Do not request secrets
- Do not modify Cloudflare
- Do not touch Access policy
