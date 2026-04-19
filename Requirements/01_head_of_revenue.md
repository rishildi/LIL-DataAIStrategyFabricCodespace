# Persona: Head of Revenue

> **Role:** Head of Revenue  
> **Reports to:** Finance Director  
> **Scope:** Portfolio-wide revenue strategy across all 10 UK properties

---

## Profile

The Head of Revenue is responsible for maximising top-line revenue across the Landon Hotels portfolio. They set pricing strategy, manage rate cards, analyse demand patterns, and ensure each property is optimising its room revenue. They work closely with hotel managers and the marketing team, and report into the Finance Director on revenue performance.

---

## Key Questions They Need Data to Answer

| Priority | Question |
|----------|---------|
| **Daily** | How did each hotel perform yesterday vs the same day last year? |
| **Weekly** | Which properties are trending above/below their monthly pace? |
| **Monthly** | What is the portfolio RevPAR, ADR, and revenue by hotel? |
| **Monthly** | How does actual revenue compare to forecast and prior year? |
| **Monthly** | Which hotels have the highest/lowest profit margins? |
| **Quarterly** | What is the revenue mix by type (rooms, catering, other)? |
| **Quarterly** | How are room rates performing vs the competitive set? |
| **Ad hoc** | What is the revenue impact of major local events? |
| **Ad hoc** | Which rate changes have driven the biggest uplift? |

---

## Metrics & KPIs

| Metric | Definition | Source |
|--------|-----------|--------|
| Total Revenue (£) | Sum of `RevenueAmountGBP` | `gold.fact_revenue` |
| Total Profit (£) | Sum of `ProfitAmountGBP` | `gold.fact_revenue` |
| Profit Margin (%) | Profit / Revenue × 100 | Calculated |
| RevPAR | Revenue / Available Room Nights | Calculated using Assumed Occupancy % parameter (default 75%) × RoomCount × Days. See Model Parameters below. |
| ADR | Room Revenue / Rooms Sold | Requires booking granularity |
| Revenue YoY Growth (%) | Current vs same period prior year | `gold.fact_revenue` + `gold.dim_date` |
| Forecast Variance (£) | Actual vs anticipated revenue | `gold.fact_revenue` vs `gold.fact_forecast` |
| Event Revenue Uplift | Revenue delta during event periods | `gold.fact_revenue` + `gold.fact_event_demand` |

---

## Model Parameters (What-If)

| Parameter | Default | Range | Purpose |
|-----------|---------|-------|----------|
| Assumed Occupancy % | 75% | 50–100% | Used to estimate RevPAR when actual occupancy data is unavailable. Default of 75% is the UK mid-scale industry benchmark (STR/PwC UK Hotels Forecast, range 72–78%). Users can adjust to model RevPAR sensitivity to occupancy assumptions. |

---

## Typical Analysis Patterns

1. **Portfolio Revenue Dashboard** — Monthly revenue and profit by hotel, with trend sparklines, YoY comparison, and ranking
2. **Rate Analysis** — Current rack rates by hotel and day-of-week, with weekday/weekend spread
3. **Forecast vs Actual** — Pre-opening forecast compared to realised revenue, by revenue type and quarter
4. **Event Correlation** — Overlay city event attendance on hotel revenue to identify demand drivers
5. **Manager Attribution** — Revenue performance segmented by manager tenure

---

## Tools & Interfaces

- **Primary:** Power BI dashboards (self-service exploration with pre-built reports)
- **Secondary:** Natural language queries via Fabric Data Agent or Copilot
- **Advanced:** Ad hoc SQL/DAX queries for deep-dive analysis

---

## Industry Benchmarks (UK Hotel Sector)

| Metric | UK Mid-Scale Benchmark |
|--------|----------------------|
| RevPAR | £55–£85 (regional); £90–£140 (London) |
| ADR | £80–£120 (regional); £120–£180 (London) |
| Occupancy | 72–78% |
| Profit Margin | 25–35% |

*Sources: STR, PwC UK Hotels Forecast, HotStats*
