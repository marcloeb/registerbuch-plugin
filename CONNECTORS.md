# Connectors

This plugin brings its own connector: the Registerbuch MCP server.

| Connector | Endpoint | Authentication |
|-----------|----------|----------------|
| **Registerbuch** | `https://mcp.protime.ai/register/mcp` | OAuth 2.0 with PKCE (Dynamic Client Registration) |

The server is declared in `.mcp.json` and activates when you install the plugin. On first use you sign in with your Protime account.

## What the connector provides

| Tool | Use |
|------|-----|
| `search_shab` | One company's publications, history, bankruptcies; counting and listing companies |
| `check_companies` | Several named companies at once |
| `search_persons` | Board members, managing directors, signatories; a person's board seats |
| `search_revisions` | Statutory auditors, and all clients of an audit firm |
| `search_building_permits` | Building applications in 13 cantons |
| `estimate_company_size` | Revenue, headcount and personnel cost, marked as an estimate |
| `verify_claims` | Check a text claim by claim against the register |

The tools work for every account within a free quota.

## Optional integrations

These connectors fit well alongside Registerbuch when installed separately:

| Connector | Use |
|-----------|-----|
| Gmail / Outlook | Check the companies in a client mail against the register |
