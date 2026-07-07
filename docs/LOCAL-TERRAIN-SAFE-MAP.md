# Local Terrain Safe Map

## Safe canonical paths

- C:\Users\EdgarsTool
  - Windows user / agent config layer
- V:\projects / V:/projects
  - Repo / project workspace
- G:\AI_WORK_512
  - Runtime / cache / heavy layer
- G:\Agent-KB
  - Agent-KB canonical intent
- G:\Obsidian\Edgar'sObsidianVault
  - Obsidian canonical intent
- D:\
  - Deprecated / do not use as source of truth

## Notes

- `V:\projects` and `V:/projects` refer to the same repo/project workspace.
- Use `repo/project workspace` when describing this layer abstractly.

## Hard exclusions

- Do NOT scan the full G:\
- Do NOT scan the full Obsidian vault
- Do NOT scan the full Agent-KB store
- Do NOT publish secrets
- Do NOT publish .env / tokens / API keys / private URLs
- Do NOT connect to Gmail / Notion / Google Drive / GitHub private API
- Do NOT modify entry.edgars.tools
- Do NOT modify mcp.edgars.tools
- Do NOT modify Cloudflare Access policy
- Do NOT create D1 / KV / R2 / Queues
- Do NOT create Tunnel / VPC
