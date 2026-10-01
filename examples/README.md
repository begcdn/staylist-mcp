# Client configuration examples

Replace the URL with your personal link from https://staylist.world/connect if you have one.

**Claude Code**
```bash
claude mcp add --transport http staylist https://staylist.world/mcp
```

**Cursor** (`~/.cursor/mcp.json`)
```json
{ "mcpServers": { "staylist": { "url": "https://staylist.world/mcp" } } }
```

**VS Code** (`.vscode/mcp.json`)
```json
{ "servers": { "staylist": { "type": "http", "url": "https://staylist.world/mcp" } } }
```

**Codex CLI** (`~/.codex/config.toml`)
```toml
[mcp_servers.staylist]
url = "https://staylist.world/mcp"
```

**Gemini CLI** (`~/.gemini/settings.json`)
```json
{ "mcpServers": { "staylist": { "httpUrl": "https://staylist.world/mcp" } } }
```

**Any HTTP client** (raw JSON-RPC)
```bash
curl -s https://staylist.world/mcp \
  -H 'content-type: application/json' -H 'accept: application/json, text/event-stream' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"search_hotels","arguments":{"city":"Rome","query":"quiet"}}}'
```
