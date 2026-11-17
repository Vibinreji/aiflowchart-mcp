# AI Flowchart MCP server

Official remote [Model Context Protocol](https://modelcontextprotocol.io) server for [AI Flowchart](https://aiflowchart.io).

Ask GitHub Copilot, Claude, ChatGPT, Cursor or any MCP client for a diagram and get back a link that opens it as an **editable board** (edit, present, export PNG / SVG / PDF / PowerPoint), plus the Mermaid code.

- **URL:** `https://mcp.aiflowchart.io/mcp` (Streamable HTTP)
- **Auth:** OAuth 2.1 (dynamic client registration + PKCE). Your client opens a sign-in page the first time; no API key needed.
- **Registry name:** `io.aiflowchart/diagrams`
- **Docs:** https://aiflowchart.io/mcp

> This repository holds the documentation for the hosted server. The server itself runs at the URL above; there is nothing to install or run locally.

## Tools

| Tool | What it does |
|---|---|
| `create_diagram` | Flowchart, sequence, ER, UML (class, state, activity, use case), architecture / system design, swimlane, BPMN, mind map, org chart, Gantt, timeline or data chart from a plain-English description |
| `edit_diagram` | Change a diagram made earlier: add, remove, rename or reconnect steps, restructure, recolour |
| `code_to_flowchart` | A function (C, C++, Java, Python, JavaScript) as a flowchart linked to its code lines, plus a step-by-step dry run |
| `render_diagram` | Mermaid code to a hosted PNG or SVG image URL, for READMEs, pull requests, docs and Slack |
| `create_visual` | An infographic of a topic or of an earlier diagram (steps, timeline, funnel, comparison, matrix…) |
| `create_sop` | A standard operating procedure with a RACI matrix for a process |
| `simulate_process` | Run a process as a simulation: time per case, cost and the bottleneck |
| `list_templates`, `open_template` | Browse and open ready-made templates (no sign-in needed) |

## Set up

### VS Code (GitHub Copilot)

Install from the MCP server gallery in VS Code, or add to `.vscode/mcp.json`:

```json
{
  "servers": {
    "aiflowchart": {
      "type": "http",
      "url": "https://mcp.aiflowchart.io/mcp"
    }
  }
}
```

Start the server, sign in when VS Code asks, then in Copilot Chat (Agent mode) ask for a diagram.

### Claude Code

```bash
claude mcp add --transport http aiflowchart https://mcp.aiflowchart.io/mcp
```

### Cursor

`~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "aiflowchart": { "url": "https://mcp.aiflowchart.io/mcp" }
  }
}
```

### Claude.ai and ChatGPT

- **Claude:** Settings → Connectors → Add custom connector → `https://mcp.aiflowchart.io/mcp`
- **ChatGPT:** search for **AI Flowchart** in the ChatGPT app directory.

## Examples

- "Draw a sequence diagram of our JWT login with refresh tokens"
- "Make an ER diagram for this schema" (paste SQL or Prisma)
- "Turn this function into a flowchart and dry run it with n = 5"
- "Render this Mermaid as an SVG I can put in the README"
- "Map our refund process as a swimlane and find the bottleneck"

Each result includes a link like `https://aiflowchart.io/import/<id>` that opens the diagram as an editable board in your AI Flowchart account.

## Plans

Free: 5 AI credits a month (templates and `render_diagram` are free). Pro ($9.99/month) makes AI unlimited in every app. See https://aiflowchart.io/pricing.

## Privacy and security

Only the text you send to a tool is processed, by our AI provider (Anthropic) under commercial terms; it is never used to train models. Diagrams are private to your account unless you share them. Details: https://aiflowchart.io/security

## Support

support@aiflowchart.io · https://aiflowchart.io/help
