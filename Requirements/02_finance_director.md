# Persona: Finance Director

> **Role:** Finance Director  
> **Reports to:** Managing Director (Europe)  
> **Scope:** Group financial performance, budgeting, cost control, and reporting

---

## Profile

The Finance Director oversees all financial operations for Landon Hotels' UK portfolio. They are responsible for annual budgets, expense control, financial reporting to senior leadership, and ensuring each property operates within its cost envelope. They are the ultimate owner of the P&L and work with hotel managers to manage profitability.

---

## Key Questions They Need Data to Answer

| Priority | Question |
|----------|---------|
| **Monthly** | What is the portfolio-wide P&L (revenue, expenses, profit) this month? |
| **Monthly** | Which hotels are over/under budget on expenses? |
| **Monthly** | What is the expense-to-revenue ratio by hotel? |
| **Quarterly** | How are expense categories trending vs prior year (payroll, utilities, maintenance)? |
| **Quarterly** | What is the cost per available room (COPAR) by property? |
| **Annually** | How accurate were the annual expense budgets vs actuals? |
| **Ad hoc** | Which expense categories are growing fastest? |
| **Ad hoc** | What is the procurement spend by property and category? |
| **Ad hoc** | What is the financial impact of manager changes on profitability? |

---

## Metrics & KPIs

| Metric | Definition | Source |
|--------|-----------|--------|
| Total Expenses (£) | Sum of `ExpenseAmountGBP` | `gold.fact_expenses` |
| Expense-to-Revenue Ratio (%) | Expenses / Revenue × 100. Flagged when above Expense-to-Revenue Threshold parameter (default 75%). See Model Parameters below. | `gold.fact_expenses` + `gold.fact_revenue` |
| Cost per Available Room (COPAR) | Total expenses / (RoomCount × Days) | Calculated |
| Payroll-to-Revenue Ratio (%) | Payroll expense / Revenue × 100 | Filtered `gold.fact_expenses` |
| Budget Variance (£ and %) | Actual spend vs annual budget | `gold.fact_expenses` vs budget |
| Procurement Spend (£) | Sum of `TotalSpendGBP` | `gold.fact_property_orders` |
| Net Operating Income (£) | Revenue − Operating Expenses | Calculated |
| YoY Expense Growth (%) | Current year vs prior year expenses | `gold.fact_expenses` + `gold.dim_date` |

---

## Model Parameters (What-If)

| Parameter | Default | Range | Purpose |
|-----------|---------|-------|----------|
| Expense-to-Revenue Threshold % | 75% | 50–100% | Hotels with an expense-to-revenue ratio above this threshold are flagged for investigation. Default of 75% is the upper bound of the UK mid-scale benchmark (HotStats/USALI, range 60–75%). Users can adjust to tighten or relax the alert threshold. |

---

## Typical Analysis Patterns

1. **Portfolio P&L Summary** — Monthly revenue and expenses, and profit by hotel with margin calculation
2. **Expense Category Breakdown** — Treemap or waterfall showing the 11 expense categories, with YoY comparison
3. **Budget vs Actual Variance** — Monthly tracking of actual expenses against annual budget allocation
4. **COPAR Benchmarking** — Cost per room comparison across the 10 properties
5. **Procurement Analysis** — Spend by product category and property, identifying consolidation opportunities
6. **Profitability Ranking** — Hotels ranked by profit margin with drill-through to expense detail

---

## Tools & Interfaces

- **Primary:** Power BI financial dashboards with drill-through to hotel and category detail
- **Secondary:** Excel exports for board pack preparation
- **Advanced:** DAX queries for ad hoc scenario modelling (e.g. "what if payroll increases 5%?")

---

## Industry Benchmarks (UK Hotel Sector)

| Metric | UK Mid-Scale Benchmark |
|--------|----------------------|
| Total Operating Expenses (% of Revenue) | 60–75% |
| Payroll (% of Revenue) | 30–35% |
| Utilities (% of Revenue) | 4–6% |
| Maintenance (% of Revenue) | 4–6% |
| GOP Margin | 25–40% |

*Sources: HotStats, USALI benchmarks, BHA (British Hospitality Association)*
