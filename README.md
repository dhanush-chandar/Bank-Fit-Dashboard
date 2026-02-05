# BankFit Dashboard (Power BI) — Canadian Banks Comparison (2023–2025)

A Power BI dashboard that compares major Canadian banks across **profitability**, **operational efficiency**, and **risk** using a transparent composite scoring method called **BankFit Score**.

This report is designed to be **stakeholder-friendly**: quick to interpret, interactive, and structured for analysis (overview → trends → drill-through deep dive).

---

## What This Report Answers

- Which bank looks strongest overall based on selected priorities (**Balanced / Growth / Safety**)?
- How do key KPIs change **quarter-over-quarter** across banks?
- What does a single bank’s **efficiency vs return tradeoff** look like over time?
- Where are bank branches distributed across the **Toronto (GTA)** area?

---

## KPIs Used

| KPI | Meaning | Direction |
|---|---|---|
| **Net Income ($M)** | Profitability | Higher is better |
| **ROE (%)** | Shareholder return | Higher is better |
| **Efficiency Ratio (%)** | Operating efficiency | **Lower is better** |
| **PCL ($M)** | Credit risk exposure | **Lower is better** |

> Note: The dashboard uses **averages** for ratio KPIs (ROE, Efficiency Ratio) and **totals** where appropriate for scale-dependent metrics (Net Income, PCL), depending on the page context.

---

## BankFit Score (How Ranking Works)

**BankFit Score** is a composite index that ranks banks using a weighted combination of the KPIs above.

High-level approach:
1. KPI values are **normalized** to allow fair comparison across banks.
2. Metrics where **lower is better** (Efficiency Ratio, PCL) are **inverted** during scoring.
3. A weighted score is calculated based on the selected **Profile**.

### Profile Logic
- **Balanced:** equal weight to profitability, efficiency, and risk  
- **Growth:** higher weight on **Net Income & ROE**, lower penalty for risk  
- **Safety:** higher penalty for **PCL** and stronger emphasis on efficiency

> The goal is not “absolute truth,” but a **consistent, explainable ranking** aligned to different decision priorities.

---

## Report Pages (Structure)

### 1) **Onboarding**
A short “how to use this report” page (≈5 min read):
- Purpose & scope
- KPI definitions + interpretation (higher/lower is better)
- BankFit Score explanation
- Navigation instructions + drill-through tip

### 2) **Bank Fit Overview**
High-level comparison across banks:
- KPI summary cards
- Net Income vs ROE by bank
- Efficiency Ratio vs PCL by bank
- BankFit Score ranking (Profile-aware)

### 3) **Quarterly Trend**
Time-series analysis (2023–2025):
- **KPI Selector** to switch the metric shown on the chart
- Trend comparison by bank across quarters

### 4) **Bank Deep Dive (Drill-through)**
Bank-specific analysis:
- GTA branch distribution map (Toronto area)
- Quarterly KPI table for the selected bank
- **Scatter:** Efficiency Ratio vs ROE (each point = a quarter)

**Drill-through:** Select a bank on any page → Right-click → **Drill through → Bank Deep Dive**

---

## Data Model 

Core model elements:
- `Fact_BankQuarterly` — quarterly KPI values by bank  
- `DimBank` — bank dimension used for consistent filtering  
- `BankLocations_Toronto` — branch locations (GTA) per bank  
- `BankFitProfiles` — profile weights (Balanced/Growth/Safety)  
- `KPI Selector` — field parameter table for switching KPI visuals  

---

## Data Scope & Sources

- **Time period:** 2023–2025  
- **Granularity:** Quarterly  
- **Branch locations:** Toronto (GTA)

Data is sourced from **public financial disclosures** and **open location datasets**.  
This dashboard is intended for **analytical comparison**, not regulatory or audited reporting.

---

## Tools & Skills Demonstrated

- Power BI data modeling 
- DAX measures for normalized scoring + profile weighting
- Field Parameters (KPI Selector)
- Drill-through design pattern (overview → deep dive)
- Visual storytelling & report UX structure

---

## How to Use

1. Open the `.pbix` file in Power BI Desktop
2. Start with **Onboarding**
3. Use:
   - **Year slicer** (2023/2024/2025)
   - **Profile selector** (Balanced / Growth / Safety)
   - **KPI selector** on the Trends page
4. Drill through into **Bank Deep Dive** for bank-level exploration

---

## Author

**Dhanush Chandar Sivakumar**  
Data Analyst | Power BI | SQL | Analytics Storytelling  
https://www.linkedin.com/in/dhanush-chandar-sivakumar/
---
