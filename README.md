# Fabric AI Agentic Development

Exercise files and pre-configured environment for the **Fabric AI Agentic Development** topic of the LinkedIn Learning course *Data & AI Strategy with Microsoft Fabric*.

In this topic you use the **ldi-fabric-agent** MCP server to design Fabric AI agents, Fabric IQ, GraphQL APIs, Lakeview dashboards, and data ontologies — entirely through Copilot Chat.

---

## What's included

### MCP server (pre-installed in the container)

| Server | What it does |
|---|---|
| **ldi-fabric-agent** | Design Fabric AI agents, Fabric IQ, GraphQL APIs, Lakeview dashboards, data ontology |

### Exercise files

| Folder | Contents |
|---|---|
| `Files_FabricAIDev/Requirements/01_head_of_revenue.md` | Head of Revenue stakeholder requirements |
| `Files_FabricAIDev/Requirements/02_finance_director.md` | Finance Director stakeholder requirements |

### Also installed

- Python 3.11 with `python-docx`, `semantic-link-labs`, `azure-identity`
- Node.js 22
- Fabric CLI (`fab`)

---

## Getting started

### 1. Create the Codespace

1. On this repo page, click the green **<> Code** button
2. Select the **Codespaces** tab
3. Click **Create codespace on fabric-ai-agentic-development**
4. VS Code opens in your browser with everything already configured
5. Wait for the terminal to show `✅ LDI Learner Workspace ready`

### 2. Start the agent

1. Open **Copilot Chat** (chat icon in the sidebar)
2. Ask the agent to review the stakeholder requirements in `Files_FabricAIDev/Requirements/`
3. The agent will guide you through design and generation of AI agent artifacts

> **Note:** This topic builds on the data foundation from the Fabric Agentic Development branch. The skills may reference tables and schemas created in that branch.

---

## How the workflow works

The agent generates **design documents, SQL scripts, ontology definitions, and notebooks** locally in the Codespace. At each step:

1. **Agent generates** an artifact (instructions, SQL scripts, ontology, notebook, etc.)
2. **You review** the output
3. **You download** artifacts that need to run in Fabric (right-click → Download)
4. **You import/run** them in your Fabric workspace via the Fabric portal
5. **Agent moves** to the next step

---

## Verify the MCP server is running

Press `Ctrl+Shift+P` → type `MCP: List Servers` → you should see **ldi-fabric-agent** listed.

---

## Troubleshooting

| Problem | Solution |
|---|---|
| MCP server doesn't appear in `MCP: List Servers` | Check that `.vscode/mcp.json` exists. Try closing and reopening Copilot Chat. |
| Copilot doesn't seem to use the MCP skills | Make sure you have a Copilot Pro subscription active, and that `chat.mcp.discovery.enabled` is `true` in your VS Code settings |
| Agent stops responding mid-way / skills stop being called | You've likely exhausted your monthly premium requests. Copilot Free = 50/month, Copilot Pro = 300/month. Upgrade or wait for the monthly reset (1st of each month UTC). |

---

## Prerequisites

| Requirement | Needed? |
|---|---|
| GitHub account | ✅ Required |
| GitHub Copilot **Pro** subscription (or higher) — ~$10/month | ✅ Required — Copilot **Free is not sufficient** |
| Microsoft Fabric access | ✅ Required for running generated artifacts |
| Docker Desktop | Not needed (runs in browser) |
| VS Code installed locally | Not needed (runs in browser) |

---

## License and intended use

### ⚠️ Educational use only

The `ldi-fabric-agent` MCP server and the skills it exposes are distributed **for educational purposes only**, as companion material for the LinkedIn Learning course *Data & AI Strategy with Microsoft Fabric*.

They are **not licensed for commercial use**. Do **not** use this agent, its skills, or the generated agents/ontologies/SQL as a process to build data products on commercial, proprietary, confidential, regulated, or customer datasets. The stakeholder requirements in `Files_FabricAIDev/Requirements/` are synthetic sample data for the Landon Hotels scenario and are the only data this Codespace is intended to be used with.

**Anything you upload into this Codespace is sent to the MCP server and to GitHub Copilot.** Do not upload real client data, PII, financial records, health records, or anything covered by an NDA or regulatory controls.

If you want to apply these patterns to commercial work, contact Learn Data Insights at [learndatainsights.com](https://learndatainsights.com) for a commercial arrangement.

See [`LICENSE`](../../blob/master/LICENSE) for the full terms, including the warranty disclaimer and the limitation of liability that apply to anything you run or generate with this agent — in particular, **you are responsible for reviewing all generated ontologies, SQL, and notebooks before running them against any Fabric environment.**
