# Auth Model

## Human login

- Cloudflare Access for web UI and interactive MCP clients.
- Redirect URI: https://edgarstools.cloudflareaccess.com/cdn-cgi/access/callback

## Machine clients

- API Bearer token for HTTPS/OpenAPI clients.
- OAuth 2.0 client credentials for service-to-service.

## MCP clients

- Managed OAuth flow via entry.edgars.tools for interactive clients.
- mcp-remote stdio proxy with CF Access service token headers for CLI agents.

## Do not store secrets in config files

Use Doppler or equivalent secret manager. Repo config files must not contain API keys, tokens, or passwords.
