# Fabric Agentic Development

Exercise files and pre-configured environment for the **Fabric Agentic Development** topic of the LinkedIn Learning course *Data & AI Strategy with Microsoft Fabric*.

In this topic you use the **ldi-fabric-developer** MCP server to build a complete Fabric medallion pipeline — workspaces, lakehouses, and data ingestion notebooks — entirely through Copilot Chat.

---

## What's included

### MCP server (pre-installed in the container)

| Server | What it does |
|---|---|
| **ldi-fabric-developer** | Create Fabric workspaces, lakehouses, notebooks; ingest CSV/PDF data into delta tables |

### Exercise files

| Folder | Contents |
|---|---|
| `Files_FabricDev/AgentPrompt.txt` | The agent prompt — paste this into Copilot Chat to begin |
| `Files_FabricDev/Data/Bronze/Booking PDFs/` | Sample hotel booking PDFs |
| `Files_FabricDev/Data/Bronze/CSV/` | Bronze, Silver, and Gold CSV data |

### Also installed

- Python 3.11 with `python-docx`, `semantic-link-labs`, `azure-identity`
- Node.js 22
- Fabric CLI (`fab`)

---

## Getting started

### 1. Create the Codespace

1. On this repo page, click the green **<> Code** button
2. Select the **Codespaces** tab
3. Click **Create codespace on fabric-agentic-development**
4. VS Code opens in your browser with everything already configured
5. Wait for the terminal to show `✅ LDI Learner Workspace ready`

### 2. Start the agent

1. Open **Copilot Chat** (chat icon in the sidebar)
2. Open `Files_FabricDev/AgentPrompt.txt`
3. Copy the prompt and paste it into Copilot Chat
4. The agent will guide you through each step

---

## How the workflow works

The agent generates **Fabric notebooks** and configuration files locally in the Codespace. At each step:

1. **Agent generates** a notebook or script
2. **You download** it from the Codespace (right-click → Download)
3. **You import** it into your Fabric workspace via the Fabric portal
4. **You run** it in Fabric and report the result
5. **Agent moves** to the next step

For data files (CSVs, PDFs), you upload them manually to your Fabric lakehouse via the Fabric portal.

---

## Verify the MCP server is running

Press `Ctrl+Shift+P` → type `MCP: List Servers` → you should see **ldi-fabric-developer** listed.

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
| Microsoft Fabric access | ✅ Required for running notebooks |
| Docker Desktop | Not needed (runs in browser) |
| VS Code installed locally | Not needed (runs in browser) |

---

## License and intended use

### ⚠️ Educational use only

The `ldi-fabric-developer` MCP server and the skills it exposes are distributed **for educational purposes only**, as companion material for the LinkedIn Learning course *Data & AI Strategy with Microsoft Fabric*.

They are **not licensed for commercial use**. Do **not** use this agent, its skills, or the generated notebooks as a process to build pipelines on commercial, proprietary, confidential, regulated, or customer datasets. The exercise data in `Files_FabricDev/Data/` is synthetic sample data for the Landon Hotels scenario and is the only data this Codespace is intended to be used with.

**Anything you upload into this Codespace is sent to the MCP server and to GitHub Copilot.** Do not upload real client data, PII, financial records, health records, or anything covered by an NDA or regulatory controls.

If you want to apply these patterns to commercial work, contact Learn Data Insights at [learndatainsights.com](https://learndatainsights.com) for a commercial arrangement.

See [`LICENSE`](../../blob/master/LICENSE) for the full terms, including the warranty disclaimer and the limitation of liability that apply to anything you run or generate with this agent — in particular, **you are responsible for reviewing all generated notebooks and SQL before running them against any Fabric environment.**
