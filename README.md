# Data & AI Strategy with Microsoft Fabric — Learner Workspace

Exercise files and pre-configured development environment for the LinkedIn Learning course **Data & AI Strategy with Microsoft Fabric**.

Each topic has its own **branch** with a dedicated MCP server, exercise files, and Copilot instructions. Pick the topic you're working on and create a Codespace from that branch.

---

## Topics

| Branch | Topic | MCP Server | What you build |
|---|---|---|---|
| [`fabric-agentic-development`](../../tree/fabric-agentic-development) | Fabric Agentic Development | ldi-fabric-developer | Fabric medallion pipeline (workspaces, lakehouses, data ingestion) |
| [`powerbi-agentic-development`](../../tree/powerbi-agentic-development) | Power BI Agentic Development | ldi-pbi-developer | Power BI report (PBIP scaffold, semantic model, theme, report pages) |
| [`fabric-ai-agentic-development`](../../tree/fabric-ai-agentic-development) | Fabric AI Agentic Development | ldi-fabric-agent | Fabric AI agents, Fabric IQ, GraphQL APIs, Lakeview dashboards, data ontology |

---

## Getting started

1. **Switch to the branch** for your topic (links above)
2. Click the green **<> Code** button → **Codespaces** tab → **Create codespace on `<branch>`**
3. VS Code opens in your browser with everything pre-configured
4. Wait for the terminal to show `✅ LDI Learner Workspace ready`
5. Open **Copilot Chat** and follow the branch README instructions

Each branch README has topic-specific setup steps, exercise files, and workflow guidance.

---

## Prerequisites

| Requirement | Needed? |
|---|---|
| GitHub account | ✅ Required |
| GitHub Copilot **Pro** subscription (or higher) — ~$10/month | ✅ Required — Copilot **Free is not sufficient**; its 50 premium-requests/month allowance runs out partway through the exercises |
| Power BI Desktop (local machine) | ✅ Required for the Power BI Agentic Development branch |
| Microsoft Fabric access | ✅ Required for the Fabric Agentic Development and Fabric AI Agentic Development branches |
| Docker Desktop | Not needed (everything runs in browser) |
| VS Code installed locally | Not needed (everything runs in browser) |

---

## Troubleshooting

| Problem | Solution |
|---|---|
| MCP server doesn't appear in `MCP: List Servers` | Check that `.vscode/mcp.json` exists. Try closing and reopening Copilot Chat. |
| Copilot doesn't use the MCP skills | Make sure you have a Copilot Pro subscription active, and `chat.mcp.discovery.enabled` is `true` in VS Code settings |
| Agent stops responding mid-way / skills stop being called | You've likely exhausted your monthly premium requests. Copilot Free = 50/month, Copilot Pro = 300/month. Upgrade or wait for the monthly reset (1st of each month UTC). |
| Can't create a Codespace | Make sure you're on the correct branch before clicking "Create codespace" |

---

## License and intended use

### ⚠️ Educational use only

The MCP servers, skills, and workflows provided in this Codespace are distributed **for educational purposes only**, as companion material for the LinkedIn Learning course *Data & AI Strategy with Microsoft Fabric*.

They are **not licensed for commercial use**. Do **not** use these skills, agents, or workflows to process commercial, proprietary, confidential, regulated, or customer datasets. If you want to apply these patterns to commercial work, contact Learn Data Insights at [learndatainsights.com](https://learndatainsights.com) for a commercial arrangement.

**Data in this Codespace is sent to the MCP servers and to GitHub Copilot.** Only upload exercise data or synthetic/sample data into this environment. Do not upload real client data, personally identifiable information, financial records, health records, or any data subject to NDA or regulatory controls.

### Attribution — third-party components

The `ldi-pbi-developer` MCP server used in the Power BI Agentic Development branch contains two skills that are **derivative works of [data-goblin/power-bi-agentic-development](https://github.com/data-goblin/power-bi-agentic-development)** by Kurt Buhler, and are licensed under **GPL-3.0-or-later**:

- `pbi-create-scaffold-pbip` — PBIP project tree, `.platform` metadata patterns, and minimal TMDL shapes
- `pbi-create-report-pages` — visual JSON templates (card, table, line/bar/column/combo/donut charts, slicers, etc.)

The GPL-3.0 licence applies **only to those specific skill folders**, not to reports or other files you generate with them, and not to the rest of this Codespace template or the other MCP servers. See the [Power BI Agentic Development branch README](../../tree/powerbi-agentic-development) for the full attribution details and the scope of the GPL licence.

All other skills, MCP servers (`ldi-fabric-developer`, `ldi-fabric-agent`, and the non-derivative parts of `ldi-pbi-developer`), and Codespace tooling are © Learn Data Insights. All rights reserved, with a limited licence granted for Course exercise use — see [`LICENSE`](LICENSE) for the full terms, including the warranty disclaimer and limitation of liability that apply to anything you run or generate with this Codespace.
