---
name: "zapier"
displayName: "Zapier"
description: "Connect 9,000+ apps to your AI workflow. Discover, enable, and execute Zapier actions directly from your AI assistant."
keywords: ["zapier", "automation", "integrations", "workflow", "ai-actions", "mcp", "no-code", "productivity", "slack", "gmail", "jira", "notion", "hubspot"]
---

# Zapier Power

Connect your AI assistant to 9,000+ apps — Slack, Gmail, Google Calendar, Jira, Notion, HubSpot, and thousands more. Once set up, you can search across your tools, take actions, and automate workflows through natural conversation.

## Onboarding

### Step 1: Connect the Zapier MCP server

After installing this power, connect the Zapier MCP server:

Connection: HTTPS API endpoint at https://mcp.zapier.com/api/v1/connect
Authorization: Use OAuth to connect to the Zapier MCP server

### Step 2: Detect your server mode

Zapier MCP operates in one of two modes. Check which tools are available:

- **Agentic mode**: `list_enabled_zapier_actions` is present — actions are managed and executed via meta-tools in chat
- **Classic mode**: `get_configuration_url` + individual `app_action_name` tools (e.g., `gmail_send_email`) — each configured action is its own MCP tool
- **Not connected**: No Zapier tools available — the server needs authentication

### Step 3: Get started

- **Agentic mode**: Call `get_zapier_skill` with name `"zapier-mcp-onboarding"` and follow its instructions
- **Classic mode**: Say **"setup zapier"** to trigger the setup workflow
- **Not connected**: Attempt `mcp_auth` on the Zapier MCP server, or follow the manual connection steps above

## When to Load Steering Files

- Setting up Zapier or troubleshooting connection issues → `zapier-setup.md`
- Checking tool health, auditing setup, or diagnosing broken tools → `zapier-status.md`
- Generating a personalized tools profile after setup → `create-my-tools-profile.md`
- Any interaction with Zapier MCP tools (reads, writes, error handling) → `zapier-lifecycle.md`

## MCP Server

This power uses the Zapier MCP server defined in `mcp.json`. The server connects to `https://mcp.zapier.com/api/v1/connect` and requires authentication via mcp.zapier.com.
