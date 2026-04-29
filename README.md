# Power BI Agentic Development

Exercise files and pre-configured environment for the **Power BI Agentic Development** topic of the LinkedIn Learning course *Data & AI Strategy with Microsoft Fabric*.

In this topic you use the **ldi-pbi-developer** MCP server to build a Power BI report end-to-end — from scoping template to finished report pages — entirely through Copilot Chat.

---

## What's included

### MCP server (pre-installed in the container)

| Server | What it does |
|---|---|
| **ldi-pbi-developer** | Scaffold Power BI projects (PBIP), create semantic models, themes, reports, DAX measures |

### Exercise files

| Folder | Contents |
|---|---|
| `Files_PowerBIDev/Agent Prompt.txt` | The agent prompt — paste this into Copilot Chat to begin |
| `Files_PowerBIDev/Requirements/` | Stakeholder requirements (Head of Revenue, Finance Director) |
| `Files_PowerBIDev/Data/Gold/` | 18 Gold-layer CSV files (star schema — dimensions, facts, reference tables) |

### Also installed

- Python 3.11 with `python-docx`, `semantic-link-labs`, `azure-identity`
- Node.js 22
- [Power BI Agentic Development Skills/CLI](https://github.com/data-goblin/power-bi-agentic-development) (cloned to `.pbi-plugins/`)

---

## Getting started

### 1. Create the Codespace

1. On this repo page, click the green **<> Code** button
2. Select the **Codespaces** tab
3. Click **Create codespace on powerbi-agentic-development**
4. VS Code opens in your browser with everything already configured
5. Wait for the terminal to show `✅ LDI Learner Workspace ready`

### 2. Download the Gold CSV files to your local machine

The Power BI report will read data from CSV files on **your local machine** via a Power Query parameter. Before starting:

1. In the Codespace Explorer, navigate to `Files_PowerBIDev/Data/Gold/`
2. Select all 18 CSV files, right-click → **Download**
3. Save them to a folder on your machine (e.g. `C:\Users\me\Documents\Gold\`)
4. **Note the full folder path** — you'll provide it during the first step

### 3. Start the agent

1. Open **Copilot Chat** (chat icon in the sidebar)
2. Open `Files_PowerBIDev/Agent Prompt.txt`
3. Copy the prompt and paste it into Copilot Chat
4. The agent will ask for any missing information (including your local CSV folder path) and guide you through each step

---

## How the workflow works

This is a **back-and-forth process** between the Codespace and Power BI Desktop:

```
Agent generates artifacts in Codespace
        ↓
You download the PBIP folder to your machine
        ↓
You open the .pbip in Power BI Desktop to check it
        ↓
You upload the PBIP folder back into Codespace (when needed)
        ↓
Agent modifies it and generates the next step
        ↓
... repeat ...
```

At each step the agent will tell you what to do — whether to download, review, upload, or just confirm.

---

## Verify the MCP server is running

Press `Ctrl+Shift+P` → type `MCP: List Servers` → you should see **ldi-pbi-developer** listed.

---

## Troubleshooting

| Problem | Solution |
|---|---|
| MCP server doesn't appear in `MCP: List Servers` | Check that `.vscode/mcp.json` exists. Try closing and reopening Copilot Chat. |
| Copilot doesn't seem to use the MCP skills | Make sure you have a Copilot Pro subscription active, and that `chat.mcp.discovery.enabled` is `true` in your VS Code settings |
| Agent stops responding mid-way / skills stop being called | You've likely exhausted your monthly premium requests. Copilot Free = 50/month, Copilot Pro = 300/month. Upgrade or wait for the monthly reset (1st of each month UTC). |
| Power BI Desktop can't find CSV files | Check the Power Query parameter points to the correct local folder path |
| Agent calls the wrong MCP server | This branch is configured for ldi-pbi-developer only. If you see other servers, check `.vscode/mcp.json` |

---

## Prerequisites

| Requirement | Needed? |
|---|---|
| GitHub account | ✅ Required |
| GitHub Copilot **Pro** subscription (or higher) — ~$10/month | ✅ Required — Copilot **Free is not sufficient** |
| Power BI Desktop (on your local machine) | ✅ Required for validating reports |
| Docker Desktop | Not needed (runs in browser) |
| VS Code installed locally | Not needed (runs in browser) |

---

## License and intended use

### ⚠️ Educational use only

The `ldi-pbi-developer` MCP server and the skills it exposes are distributed **for educational purposes only**, as companion material for the LinkedIn Learning course *Data & AI Strategy with Microsoft Fabric*.

They are **not licensed for commercial use**. Do **not** use this agent, its skills, or the generated PBIP outputs as a process to build reports on commercial, proprietary, confidential, regulated, or customer datasets. The exercise data in `Files_PowerBIDev/Data/Gold/` is synthetic sample data for the Landon Hotels scenario and is the only data this Codespace is intended to be used with.

**Anything you upload into this Codespace is sent to the MCP server and to GitHub Copilot.** Do not upload real client data, PII, financial records, health records, or anything covered by an NDA or regulatory controls. If you want to apply these patterns to commercial work, contact Learn Data Insights at [learndatainsights.com](https://learndatainsights.com) for a commercial arrangement.

### Attribution — GPL-3.0-or-later components

Two of the skills inside `ldi-pbi-developer` are **derivative works** of [**data-goblin/power-bi-agentic-development**](https://github.com/data-goblin/power-bi-agentic-development) by Kurt Buhler, and are therefore licensed under **GNU General Public License v3.0 or later (GPL-3.0-or-later)**:

| Skill | What is derived from data-goblin |
|---|---|
| `pbi-create-scaffold-pbip` | PBIP project tree layout, `.platform` metadata, shapes for `definition.pbir` / `version.json` / `report.json` / `pages.json` / `page.json`, minimal TMDL for `database.tmdl` and `model.tmdl`, page-folder name regex |
| `pbi-create-report-pages` | Visual JSON templates for: card, cardVisual, tableEx, pivotTable, lineChart, barChart, columnChart, comboChart, donutChart, gauge, kpi, scatterChart, areaChart, stackedAreaChart, waterfallChart, slicer (list and dropdown), textbox |

**Scope of GPL-3.0**: the GPL licence applies only to the source files inside those two skill folders. It does **not** apply to:

- Reports, semantic models, or other artefacts **you generate** by invoking these skills (those are your work)
- The other skills in `ldi-pbi-developer` (DAX patterns, themes, scoping, measure creation, etc.)
- The other MCP servers (`ldi-fabric-developer`, `ldi-fabric-agent`)
- The Codespace template, devcontainer, exercise files, or course materials

**Your obligations under GPL-3.0** if you redistribute or modify the two derivative skill folders above: preserve the attribution to Kurt Buhler / data-goblin, keep the GPL-3.0 licence text, and make your modifications available under the same licence. The full GPL-3.0 licence text is available at [https://www.gnu.org/licenses/gpl-3.0.html](https://www.gnu.org/licenses/gpl-3.0.html).

Note: As a learner using this Codespace to work through the course exercises, you are **not** redistributing or modifying the skill source — you are running the MCP server. The GPL obligations above only apply if you fork the MCP source and redistribute modified versions.

All other components of this Codespace are © Learn Data Insights. All rights reserved, with a limited licence granted for Course exercise use — see [`LICENSE`](../../blob/master/LICENSE) for the full terms, including the warranty disclaimer and the limitation of liability that apply to anything you run or generate with this agent.
