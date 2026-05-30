# Zapier MCP

**Connect your AI to thousands of apps with the Model Context Protocol**

Transform your AI assistant from a conversational tool into a functional extension of your applications. [Zapier MCP](https://zapier.com/mcp) is a **remote** MCP server that gives your AI direct access to 9,000+ apps and 40,000+ actions—no complex API integrations required.

https://github.com/user-attachments/assets/8304058f-67da-40b9-bc4f-5095b2817d61

---

## What is Zapier MCP?

[Zapier MCP](https://zapier.com/mcp) is a standardized way to connect AI assistants to thousands of apps and services. It enables your AI to take real actions like:

- 💬 Send Slack messages and create channels
- 📊 Add rows to Google Sheets and create spreadsheets
- 📧 Send Gmail emails and manage labels
- ✅ Create Asana tasks and update projects
- 🐙 Create GitHub issues and manage PRs
- 📈 Update HubSpot deals and manage contacts

All through natural language commands—just describe what you want done.

---

## Key Features

- **8,000+ App Connections** — Access Zapier's massive library of pre-built integrations
- **40,000+ Actions** — Enable specific tasks and searches across apps
- **Natural Language** — No complex commands needed
- **Secure by Default** — Authentication, encryption, and rate limiting handled by Zapier
- **Multiple Client Support** — Works with Claude, ChatGPT, Cursor, Windsurf, and more

---

## Getting Started

**1. Generate your credentials**

Visit [mcp.zapier.com](https://mcp.zapier.com) to set up your server. Two auth options are available:

- **API Key** — Best for personal use and local development. Generate one at [mcp.zapier.com](https://mcp.zapier.com).
- **OAuth** — Best for building apps where end users connect their own Zapier account. Use the connect URL: `https://mcp.zapier.com/api/v1/connect`

**2. Connect your MCP client**

Point your AI client at your Zapier MCP server URL. See client-specific setup guides at [mcp.zapier.com](https://mcp.zapier.com).

**3. Add actions to your server**

Visit [mcp.zapier.com](https://mcp.zapier.com) to browse and enable specific actions. Each action you add becomes a callable tool in your AI client.

---

## Built-in Tools

Zapier MCP servers operate in one of two modes. Your server's mode determines which built-in tools are available.

### Agentic (Beta)

The Agentic configuration is currently in Beta and being rolled out to all users. Agentic servers provide 14 static meta-tools for managing and executing actions entirely within the chat experience:

| Tool | Category | Description |
|------|----------|-------------|
| `list_enabled_zapier_actions` | Action Management | See all your currently enabled actions |
| `discover_zapier_actions` | Action Management | Search for apps and actions available to add |
| `enable_zapier_action` | Action Management | Enable a specific action as a tool |
| `disable_zapier_action` | Action Management | Disable an action you no longer need |
| `auto_provision_mcp` | Action Management | Auto-setup tools from your existing Zapier connections |
| `execute_zapier_read_action` | Execution | Run a read/search action (e.g., find an email, look up a contact) |
| `execute_zapier_write_action` | Execution | Run a write action (e.g., send a message, create a task) |
| `get_configuration_url` | Configuration | Get the URL to your Zapier MCP config page |
| `list_zapier_skills` | Skills | List saved Zapier skills/workflows |
| `get_zapier_skill` | Skills | Retrieve a specific skill |
| `create_zapier_skill` | Skills | Create a new skill |
| `update_zapier_skill` | Skills | Update an existing skill |
| `delete_zapier_skill` | Skills | Delete a skill |
| `send_feedback` | Feedback | Send feedback to Zapier |

### Classic

Classic servers expose one built-in tool alongside your configured action tools:

| Tool | Description |
|------|-------------|
| `get_configuration_url` | Returns the URL to add/edit/remove actions from this server |

---

## How Actions Work

### Agentic (Beta)

Actions are managed and executed directly in chat. Use `discover_zapier_actions` to find available apps, `enable_zapier_action` to add one, and `execute_zapier_read_action` / `execute_zapier_write_action` to run it. Your AI can also call `list_enabled_zapier_actions` at any time to see what's currently available.

### Classic

When you add an action at [mcp.zapier.com](https://mcp.zapier.com), it gets exposed as a dedicated tool on your MCP server. Your AI can then call it directly.

**Example:** Enable the "Gmail - Send Email" action, and your AI gains a `gmail_send_email` tool it can invoke with the right parameters (to, subject, body) whenever you ask it to send an email.

The more actions you enable, the more capable your AI becomes. You can build a focused server with just a handful of tools, or a broad one that spans your entire stack.

---

## Plugins

This repo also hosts official Zapier plugins for AI workflows. Each plugin is a standalone directory under `plugins/` with its own manifest.

| Plugin | Category | Description |
|--------|----------|-------------|
| [Zapier](plugins/zapier/) | Productivity | Connect 9,000+ apps to your AI workflow. Discover, enable, and execute Zapier actions directly from your client. Includes onboarding skills, status tools, and safety rules. |

---

## Resources

- **[🤖 MCP Plugins →](plugins/)** — Official plugins in this repo
- **[🤖 MCP Skills →](plugins/zapier/skills/)** — Companion skills for AI clients
- **[📖 Developer Documentation →](https://docs.zapier.com/mcp/home)** — API references and integration guides
- **[🆘 Support →](https://mcp.zapier.app/home)** — Get help with Zapier MCP

---

## Contributing
PRs welcome!

<!-- Contributor: Arvuno - documentation update -->

