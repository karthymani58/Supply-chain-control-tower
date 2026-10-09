<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:217346,100:0078D4&height=220&section=header&text=Supply%20Chain%20Control%20Tower&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Data%20Governance%20%7C%20Data%20Quality%20Pipelines%20%7C%20Financial%20Validation%20Model&descSize=16&descAlignY=60" alt="Supply Chain Control Tower Header" />

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&duration=3000&pause=1000&color=217346&center=true&vCenter=true&width=700&lines=30%2C000%2B+Maritime+Operational+Runs+Analyzed;50+Global+Trade+Corridors+Monitored;Data+Governance+and+Audit-Ready+Validation;Excel-Based+KPI+Reconciliation+and+Validation" alt="Typing Banner" />

<br />

![Microsoft Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power_Query-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Data Quality](https://img.shields.io/badge/Data_Quality-100%25_Validated-brightgreen?style=for-the-badge)

[Overview](#executive-summary) |
[Architecture](#repository-structure--workbook-architecture) |
[Data Governance](#data-quality--governance) |
[KPI Baselines](#summary-page-kpi-baselines) |
[Fiscal Calendar](#timeline--fiscal-calendar-engineering) |
[Route Analysis](#route-performance-pivot-analysis) |
[Author](#author)

</div>

---

## Executive Summary

This project is an enterprise-grade **Supply Chain Analytics and Control Tower Model** built in Microsoft Excel and supported by **Power Query** for data transformation.

It contains the core data governance framework, automated duplicate and null auditing routines, fiscal calendar engineering, and baseline KPI validations across **30,000+ maritime operational runs** spanning **50 global trade corridors**.

> **Core Objective:** Establish an immutable baseline model in Excel to ensure 100% financial and operational reconciliation across all reporting views.

### Key Highlights

| Area | Detail |
| :--- | :--- |
| Operational Records | 30,048 route operation runs |
| Trade Corridors | 50 international routes |
| Disruption Events | 10,003 geopolitical and operational events |
| Time Horizon | 626 operational weeks |
| Data Quality | 0 duplicates, 0 missing keys |
| Primary Tool | Microsoft Excel with Power Query |

---

## Repository Structure & Workbook Architecture

The workbook **`Supply chain Working.xlsx`** follows a modular dimensional schema across seven worksheets.

```text
Supply Chain Control Tower
|-- Summary                     Executive dashboard and KPI baseline audits
|-- FactRouteOperations         Fact: primary transaction log (30,048 rows)
|-- FactTradeRoutes             Dimension: route metadata and SLAs (50 routes)
|-- FacGgeopoliticalEvents      Fact: disruptions and risk ratings (10,003 rows)
|-- WeeklyTimeline              Dimension: master fiscal calendar (626 weeks)
|-- CountryMetadata             Dimension: macroeconomic and LPI benchmarks (10 countries)
`-- FactCommodityMarket         Fact: benchmark energy and metal prices (626 rows)
```

### Detailed Sheet Inventory

| Sheet Name | Type | Granularity / Volume | Core Purpose |
| :--- | :--- | :--- | :--- |
| `Summary` | Analytical View | KPI level | Baseline reconciliation formulas, data audit checks and route PivotTables |
| `FactRouteOperations` | Fact Table | 30,048 transaction runs | Volume, delays, costs, congestion, risk scores and carbon emissions |
| `FactTradeRoutes` | Dimension | 50 trade routes | Route metadata, origin, destination, shipping distance (km) and SLA |
| `FacGgeopoliticalEvents` | Fact / Event Log | 10,003 disruption events | Chronological record of cyber attacks, port strikes and political unrest |
| `WeeklyTimeline` | Dimension | 626 operational weeks | Date key mapping weeks to months, quarters and April to March fiscal years |
| `CountryMetadata` | Dimension | 10 primary nations | GDP per capita, Logistics Performance Index (LPI) and port capacity |
| `FactCommodityMarket` | Fact Table | 626 weekly records | Benchmark prices for crude oil, natural gas, steel, wheat and copper |

---

## Data Quality & Governance

Before analysis, a rigorous data cleaning pipeline was executed to ensure full data fidelity across all **30,048 operational logs**.

### 1. Composite Key Uniqueness Audit

- **Key Evaluated:** Composite pair (`route_id` + `date`) across `FactRouteOperations`
- **Validation Method:** Checked for multi-record collisions on identical week-start dates
- **Audit Outcome:**

```diff
+ PASS: 0 duplicate records found (0 composite key clashes across 30,048 rows)
```

### 2. Null and Blank Integrity Check

- **Method:** `=COUNTBLANK()` applied across critical dimensional foreign keys
- **Audit Outcome:**

```diff
+ PASS: 0 missing Route IDs
+ PASS: 0 missing operational dates
```

### 3. Standardization Rules

- **Categorical Normalization:** Text fields (`route_status`, `shipping_method`, `trade_route_type`) processed with `=TRIM()` and uppercase routines
- **Numeric Casting:** Explicit numeric types enforced on key metrics:
  - `container_availability_index`
  - `port_congestion_index`
  - `fuel_cost_index`
  - `geopolitical_risk_score`

---

## Summary Page KPI Baselines

The matrix below lists the exact Excel baseline formulas used to reconcile and validate data across all reporting views.

| Metric Description | Excel Audit Formula | Validated Baseline | Status |
| :--- | :--- | :--- | :---: |
| Average Shipping Delay | `=AVERAGE(FactRouteOperations[shipping_delay_days])` | 6.38 days | PASS |
| Total Recorded Freight Cost | `=SUM(FactRouteOperations!E:E)` | $122,062,713.71 | PASS |
| Total Recorded Trade Volume | `=SUM(FactRouteOperations!C:C)` | 569,367,812.73 tons | PASS |
| Total Delayed Records | `=COUNTIF(FactRouteOperations!L:L, "Delayed")` | 19,219 records | PASS |
| Total Disrupted Records | `=COUNTIF(FactRouteOperations!L:L, "Disrupted")` | 960 records | PASS |
| Missing Route ID Count | `=COUNTBLANK(FactRouteOperations[route_id])` | 0 blanks | PASS |
| Missing Date Count | `=COUNTBLANK(FactRouteOperations[date])` | 0 blanks | PASS |

> **Note:** All figures serve as hard-coded target benchmarks for validating future analysis, for example `SUM(FactRouteOperations[freight_cost_usd])`.

---

## Timeline & Fiscal Calendar Engineering

Custom time-intelligence attributes were built in the `WeeklyTimeline` sheet from the weekly date key starting at cell `A2`.

```excel
Day Name        = TEXT(A2, "dddd")                      -> "Sunday"
Month Name      = TEXT(A2, "mmmm")                      -> "January"
Month Number    = MONTH(A2)                             -> 1
Quarter         = "Q" & INT((MONTH(A2)-1)/3)+1          -> "Q1"
Calendar Year   = YEAR(A2)                              -> 2015
Fiscal Year     = "FY " & IF(MONTH(A2)>=4,
                    YEAR(A2) & "-" & RIGHT(YEAR(A2)+1, 2),
                    (YEAR(A2)-1) & "-" & RIGHT(YEAR(A2), 2))
```

This supports standard **April to March** fiscal cycle reporting across the multi-year operational horizon.

---

## Route Performance Pivot Analysis

A route-level summary on the `Summary` page isolates key performance metrics across 50 international corridors (`R00001` to `R00050`).

| Configuration | Setting |
| :--- | :--- |
| Global Filter | `route_status` (Normal, Delayed, Disrupted) |
| Row Grouping | `route_id` |
| Values Calculated | `AVERAGE(shipping_delay_days)`, `SUM(freight_cost_usd)`, `AVERAGE(port_congestion_index)` |

### Sample Corridor Breakdown

| Route ID | Avg Delay (Days) | Total Freight Cost ($) | Avg Congestion Index |
| :--- | ---: | ---: | ---: |
| R00003 | 3.27 | 1,174,596.73 | 37.14 |
| R00004 | 3.17 | 1,229,400.65 | 37.13 |
| R00005 | 3.25 | 1,316,773.93 | 36.37 |
| R00036 | 3.31 | 1,063,921.33 | 38.28 |
| **Grand Total** | **3.13** | **39,163,326.27** | **37.19** |

---

## Tech Stack

| Layer | Tool |
| :--- | :--- |
| Data Modeling & Validation | Microsoft Excel (Tables, PivotTables, Formulas) |
| Data Transformation | Power Query |
| Reporting & Analysis | Excel PivotTables, Summary Dashboard |

---

## Author

<div align="center">

### Karthik M

**Supply Chain Analytics | Data Governance | Business Intelligence**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/karthik--m--online/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/karthymani58)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:karthymani58@gmail.com)

</div>

---

## Contributing

Feedback, issues and feature requests are welcome. Please open an issue or submit a pull request.

<div align="center">

*Designed and maintained for enterprise supply chain control tower reporting.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0078D4,100:217346&height=120&section=footer" alt="Footer" />

</div>
