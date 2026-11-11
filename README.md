<p align="center"><img src="assets/zapx-icon-512.png" width="96" alt="ZapX logo"></p>

# ZapX MCP Server by ZAP-Hosting

Official, hosted remote MCP server for **ZapX**, the customer panel of [ZAP-Hosting](https://zap-hosting.com/en/mcp).
Connect Claude, ChatGPT, Cursor, Gemini or any other MCP client and manage the services in your ZapX account from chat.
Nothing to install: the server runs at ZAP-Hosting.

**This repository contains documentation only.** The server is operated by ZAP-Hosting; there is no source code or package here.

| | |
|---|---|
| Endpoint | `https://zap-hosting.com/api/mcp` |
| Transport | Streamable HTTP |
| Authentication | OAuth 2.1 (Dynamic Client Registration, PKCE S256) |
| Documentation | https://zap-hosting.com/en/mcp |
| Setup guide | https://zap-hosting.com/en/help/articles/connect-zapx-api-and-mcp-to-ai-clients |
| REST API | https://zap-hosting.com/en/developers/api |
| Requirements | ZapX account with an active ZapX Pass (Plus or higher) |

## What you can do

- **Game servers:** live status, start, stop, restart, console logs and commands, files and configs, backups, save games, mods, versions.
- **VPS:** status and metrics, power actions, backups and snapshots, schedules, rescue mode, traffic and DDoS status, firewall overview.
- **Dedicated servers:** power state, hardware and metrics, reinstall, custom ISOs, rescue mode, reverse DNS, remote management.
- **TeamSpeak:** status, configuration, privilege keys, bans, connected clients.
- **Discord bots:** status, power actions, logs and files.
- **Domains:** DNS records, nameservers, auto-renew.

## Security

- Sign-in uses OAuth with your ZapX account. By default the connector can only **read**.
- You choose which areas it may change (power, console, configuration, backups, TeamSpeak, domains) and can revoke access at any time under *Settings → API access*.
- Every tool carries MCP annotations (`readOnlyHint`, `destructiveHint`), so your client asks before anything changes.
- The connector cannot place new orders.

## Connect

**Claude (claude.ai / Claude Desktop):** Settings → Connectors → *Add custom connector* → URL `https://zap-hosting.com/api/mcp` → sign in with ZapX.

**Claude Code:**

```bash
claude mcp add --transport http zapx https://zap-hosting.com/api/mcp
```

**Cursor / VS Code / Windsurf / other clients** (`mcp.json`):

```json
{
  "mcpServers": {
    "zapx": { "url": "https://zap-hosting.com/api/mcp" }
  }
}
```

**ChatGPT:** Settings → Apps & Connectors → developer mode → add the URL above.

**Gemini CLI** (`settings.json`):

```json
{
  "mcpServers": {
    "zapx": { "httpUrl": "https://zap-hosting.com/api/mcp" }
  }
}
```

Your client opens the ZapX login on first use. Step-by-step guide with screenshots: https://zap-hosting.com/en/help/articles/connect-zapx-api-and-mcp-to-ai-clients

## Example prompts

- *Show the live status of all my servers.*
- *Show the last 50 console lines of my Minecraft server and explain any errors.*
- *Create a backup of my VPS, then restart it.*

## Support

- Help center: https://zap-hosting.com/en/help
- Feedback about the MCP server itself: ask your AI client to use the `report_mcp_feedback` tool.

## Legal

[Privacy](https://zap-hosting.com/en/privacy) · [Terms](https://zap-hosting.com/en/terms) · [Imprint](https://zap-hosting.com/en/imprint)

© ZAP-Hosting GmbH. ZapX and ZAP-Hosting are trademarks of ZAP-Hosting GmbH.
