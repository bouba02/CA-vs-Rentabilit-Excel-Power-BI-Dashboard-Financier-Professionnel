# Revenue vs Profitability Dashboard — SME Financial Management | Excel + Power BI

> **40% of entrepreneurs generate revenue but don't make money.**  
> 24 months · 233 rows · 9 DAX measures · Automatic alerts · 43-min YouTube tutorial

![Dashboard Preview](Dashboard_CA_vs_Rentabilité.png)

🇫🇷 [Version française disponible ici](README_FR.md)

---

## Business Problem

The confusion between **Revenue** and **Profitability** costs entrepreneurs
thousands of dirhams every year.

```
Revenue (what comes in) − Variable Costs − Fixed Costs = Net Profit (what stays)
```

This project demonstrates how to build a complete financial management system
that automatically detects problematic months before they become crises,
and enables data-driven decisions.

---

## Results Over 24 Months (Jan 2023 – Dec 2024)

| Indicator | Value |
|---|---|
| Total Revenue | 2,079,000 MAD |
| Net Profit | 1,590,717 MAD |
| Average Net Margin | **76.5%** |
| Variable Costs | 109,083 MAD — 5.3% of revenue |
| Fixed Costs | 379,200 MAD — controlled |

---

## Case Study — July 2024 : The Disaster Month

| Indicator | January 2024 | July 2024 | Change |
|---|---|---|---|
| Revenue | 105,000 MAD | 48,000 MAD | -54% |
| Variable Costs | 2,300 MAD | 40,000 MAD | +1,639% |
| Net Profit | 86,900 MAD | -7,800 MAD | -109% |
| Net Margin | 82.8% | **-16.2%** | -99 pts |

**Root cause:** Marketing campaign — 40,000 MAD invested, 48,000 MAD revenue generated.  
Real ROI: -16.2%. Cost/Revenue ratio: 83% (critical threshold > 50%).

**Business decisions triggered by the dashboard:**
- Immediate halt of this campaign type
- Marketing budget capped at 5% of projected revenue
- A/B testing mandatory before any investment > 5,000 MAD

**Dashboard alerts automatically activated:**
🔴 Margin Status: Fragile · 🔴 Cost Alert: Too high

---

## Dashboard — Components

![Dashboard](Dashboard_CA_vs_Rentabilité.png)

| Component | Description |
|---|---|
| 4 KPI cards | Revenue · Gross Margin % · Net Profit · Net Margin % |
| 2 conditional alerts | Margin Status · Variable Cost Alert |
| Waterfall chart | Revenue → Gross Margin → Net Profit (gains/losses colored) |
| Monthly trend | Revenue and Net Profit over 24 months — flags July 2024 |
| Revenue by service | Net Margin % by service type (horizontal bars) |
| Interactive filters | Year + Month slicers — dynamic update |

---

## DAX Measures — 9 Measures

```dax
// Core KPIs
CA_Total = SUM(Ventes[Montant_HT])

Variable_Costs =
CALCULATE(SUM(Depenses[Montant]), Depenses[Type_Cout] = "Variable")

Fixed_Costs =
CALCULATE(SUM(Depenses[Montant]), Depenses[Type_Cout] = "Fixe")

Gross_Margin       = [CA_Total] - [Variable_Costs]
Gross_Margin_%     = DIVIDE([Gross_Margin], [CA_Total], 0)
Net_Profit         = [Gross_Margin] - [Fixed_Costs]
Net_Margin_%       = DIVIDE([Net_Profit], [CA_Total], 0)

// Conditional alerts
Margin_Status =
VAR Margin = [Net_Margin_%]
RETURN SWITCH(TRUE(),
    Margin < 0.10, "Fragile",
    Margin < 0.20, "Acceptable",
    Margin < 0.30, "Good",
    Margin < 0.40, "Very Good",
    "Excellent"
)

Cost_Alert =
VAR Ratio = DIVIDE([Variable_Costs], [CA_Total], 0)
RETURN SWITCH(TRUE(),
    Ratio > 0.50, "Costs too high",
    Ratio > 0.30, "Monitor",
    "Under control"
)
```

---

## Dataset

| Parameter | Value |
|---|---|
| Volume | 233 rows (126 sales + 107 expenses) |
| Period | 24 months — Jan 2023 → Dec 2024 |
| Power BI tables | 3 (Sales · Expenses · Calendar) |
| Currency | MAD — Moroccan Dirham |
| Source | 5-tab Excel file (Parameters · Sales · Expenses · Cash Flow · Dashboard) |

**Critical column:** `Type_Cout` (FIXED / VARIABLE) — drives all DAX profitability measures.

---

## YouTube Tutorial — 43 Minutes

[![YouTube](https://img.shields.io/badge/YouTube-Watch%20full%20tutorial%2043%20min-red?logo=youtube)](https://youtu.be/AUYo3agdDWY)

| Timestamp | Content |
|---|---|
| 00:00 | Business problem: Revenue ≠ Profitability |
| 01:00 | Theory — P&L framework |
| 03:00 | Excel structure — 5 tabs |
| 06:00 | Power BI import + relational model |
| 09:50 | 9 DAX measures + conditional alerts |
| 15:00 | Full dashboard design |
| 38:00 | Business analysis — January vs July 2024 |

---

## Tech Stack

- **Excel 365** — data structuring (233 rows)
- **Power BI Desktop** — interactive dashboard
- **DAX** — 9 calculated measures
- **Power Query / M** — import and cleaning

---

## Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/bouba02/Dashboard-CA-Rentabilite.git

# 2. Open Excel
# Excel/Pilotage_Financier_Ngroup.xlsx

# 3. Open Power BI
# PowerBI/Dashboard_CA_Rentabilite.pbix
# → Data already imported and dashboard ready
```

---

## Repository Structure

```
Dashboard-CA-Rentabilite/
├── README.md
├── README_FR.md
├── Dashboard_CA_vs_Rentabilité.png
├── Excel/
│   └── Pilotage_Financier_Ngroup.xlsx
├── PowerBI/
│   └── Dashboard_CA_Rentabilite.pbix
└── Documentation/
    ├── Guide_Complet.pdf
    ├── Formules_DAX.txt
    └── Analyses_Business.md
```

---

## Author

**Boubacar Nikiema** — Data Analyst & BI Consultant

Specialized in financial dashboards, sales & supply chain analytics and SME financial
management using Power BI, SQL, Python and Excel. Based in Morocco, working with
clients across Africa and French-speaking Europe.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-boubacar--nikiema-blue?logo=linkedin)](https://linkedin.com/in/boubacar-nikiema)
[![YouTube](https://img.shields.io/badge/YouTube-BoubacarDataAnalyst-red?logo=youtube)](https://youtube.com/@BoubacarDataAnalyst)
[![Email](https://img.shields.io/badge/Email-nikiemaboubacar%40gmail.com-gray?logo=gmail)](mailto:nikiemaboubacar@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-data.ngroupmediadigital.com-green)](https://data.ngroupmediadigital.com)

---

*Simulated data for educational purposes · Code: MIT License*
