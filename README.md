# 🦘 Kangaroo Revenue Command Centre

**Audience-Adaptive FP&A Revenue Analysis · Portfolio Case Study**  
*Built by Julaluk Clements · CPA (ASA) · [julalukclements.com](https://julalukclements.com)*

---

> **Reporting explains what happened.**  
> **FP&A storytelling helps leaders decide what to do next.**

---

## What This Is

The Kangaroo Revenue Command Centre is an AI-assisted, finance-led portfolio project that turns a 216-row commercial revenue dataset into audience-adaptive executive decision support.

This is not just a dashboard. It is a revenue decision layer.

**Dataset:** 216 rows · Jan 2024 – Dec 2025 · 3 business units · 3 products · $22.6M net revenue  
**Primary KPI:** Net Revenue  
**Supporting metrics:** Gross Revenue · ARR · MRR · Discount % · Deferred Revenue · Recognized Revenue

---

## The Core Idea

Most dashboards show numbers. This one answers questions.

| Audience | Business Question |
|---|---|
| **CEO** | Are we growing in the right direction? |
| **CFO** | Is revenue quality strong and predictable? |
| **FP&A** | What is driving the movement? |
| **Sales Leadership** | Where are we winning — and where are we discounting too hard? |
| **Board** | Is performance repeatable and scalable? |

One dataset. Five decision lenses. Same numbers — different insight for each stakeholder.

---

## Files in This Repository

| File | Purpose |
|---|---|
| `index.html` | Interactive audience-adaptive HTML dashboard — live filters, 14 charts, 5 audience views |
| `Kangaroo_Master_Data.xlsx` | Raw 216-row revenue dataset — source of truth |
| `Kangaroo_Excel_Dashboard.xlsx` | Excel workbook — 9 sheets, Power Query, QA control layer |
| `Kangaroo_Finance_Review_Editorial_Infographic.pdf` | One-page editorial finance infographic |
| `README.md` | This file |

---

## Live Dashboard

**[→ Open Interactive Dashboard](https://thehalloffrey-collab.github.io/kangaroo-dashboard/)**

The HTML dashboard includes:
- Audience selector — CEO / CFO / FP&A / Sales Leadership / Board
- Date range filter — any window within Jan 2024 – Dec 2025
- Business unit, product, segment, and revenue type filters
- 14 live charts including trend, donut, heatmap, scatter, and league table
- Audience-adaptive narrative and KPI cards that change with each view

---

## Excel Workbook

The Excel workbook is the finance control layer. It includes:

### Sheets
| Sheet | Purpose |
|---|---|
| 📋 Cover | Navigation index · version · AI disclosure |
| 📊 Executive Summary | KPI cards · BU · product · segment breakdown |
| 👁 Audience Lens | What each stakeholder needs to see and why |
| 📈 Revenue Analysis | 24-month trend · BU × Product matrix |
| 🗺 Dashboard Logic | KPI definitions · audience mapping matrix |
| ✅ QA Control | 13 integrity checks · all live formulas |
| 📂 Raw Data | 216-row source with row-level audit cols U–Y |

### Power Query (5 queries — Refresh All to update)
| Query | Output |
|---|---|
| `QA_ValidationModule` | Row-level derivation chain audit — 216 rows validated |
| `QA_AuditSummary` | Summary PASS/FAIL counts by check type |
| `Monthly_Summary` | Monthly aggregation with MoM change and % |
| `BU_Product_Summary` | Business unit × product breakdown |
| `Segment_Discount_Summary` | Discount risk by customer segment |

### QA Control — what is checked
- Row count = 216
- Total Gross Revenue tie-back
- Total Net Revenue tie-back
- Discount % within expected range
- ARR ≥ Net Revenue
- No blanks in Deferred Revenue
- Currency = USD throughout
- Net Revenue never exceeds Gross Revenue (SUMPRODUCT row-by-row)
- Recognized Revenue reconciliation (AASB 15)
- Date range = 24 unique months
- Discount logic tie-back: Gross × (1 – Disc%) ≈ Net Revenue (tolerance < $500)
- ARR = MRR × 12 (row-level ratio check — not aggregate)
- Row-level audit FAIL count (cols U–Y in Raw Data)

### Row-Level Audit (Raw Data cols U–Y)
Every row has five live audit checks:
- **U** — Net Revenue logic: `ABS(Gross × (1−Disc) − Net) / Gross < 0.1%`
- **V** — ARR = MRR × 12 (tolerance ≤ $1)
- **W** — Recognized bridge: `ABS(Net + Deferred − Recognized) ≤ $1`
- **X** — Critical fields not blank or zero
- **Y** — Row status: PASS / FAIL

---

## Finance Logic — Derivation Chain

Every number is reverse-engineered from first principles in Power Query:

```
Units Sold × Price per Unit       → Computed Gross Revenue
Gross Revenue × Discount %        → Discount Amount ($)
Gross Revenue − Discount Amount   → Computed Net Revenue
Net Revenue + Deferred Rev Change → Computed Recognized Revenue (AASB 15)
MRR × 12                          → Computed ARR
```

Any deviation beyond tolerance is flagged with the specific gap amount and which check failed.

---

## Key Findings

| Signal | Finding |
|---|---|
| **Growth** | Net revenue grew consistently through 2025 — Dec 2025 peak at $1.14M |
| **Revenue mix** | Expansion at 37.3% leads — healthy growth engine |
| **Renewal risk** | Renewal at 30.6% — below 35% benchmark, watch closely |
| **Discount risk** | Enterprise (12.05%) and SMB (11.98%) both above 12% threshold |
| **Discount leakage** | $3.18M total discount across the dataset |
| **Revenue quality** | Deferred revenue positive at $632K — billings ahead of recognition |
| **Top combination** | Enterprise × Product B — highest-value segment-product pairing |
| **BU spread** | Balanced — no single BU exceeds 35% of total net revenue |

---

## AI Use Disclosure

This project was developed with AI assistance for code generation, layout iteration, Power Query M code structure, and documentation support.

The finance logic, KPI selection, audience design, derivation chain validation, tolerance decisions, QA framework, and final business interpretation were directed and validated by Julaluk Clements.

**AI-assisted. Finance-led. QA-controlled.**

---

## Technology Stack

| Layer | Tools |
|---|---|
| Interactive dashboard | HTML · CSS · JavaScript · Chart.js |
| Data layer | Excel 365 · Power Query (M) · openpyxl |
| Fonts | Space Grotesk · JetBrains Mono · Inter |
| Hosting | GitHub Pages |
| DNS | Hostinger |

---

## About the Author

**Julaluk Clements** — Senior Financial Accountant · FP&A Specialist  
CPA Australia Associate (ASA) · Google AI Professional Certificate (distinctive) — completed April 2026  
15+ years global finance · Shell Business Operations (KL) · MES Mitr Project Services (Bangkok) · Melbourne, VIC

**Hall of Frey Advisory** — FP&A advisory · AI automation · Platform implementation

→ [julalukclements.com](https://julalukclements.com)  
→ [au.linkedin.com/in/julaluk-clements](https://au.linkedin.com/in/julaluk-clements)  
→ jc@julalukclements.com

---

*Built with finance discipline. Designed for decision-makers.*
