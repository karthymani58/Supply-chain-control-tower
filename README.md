# 🚢 Supply Chain Control Tower | Excel · Power Query · Power BI

<div align="center">

<a href="https://github.com/karthymani58/Supply-chain-control-tower">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0D47A1,50:1565C0,100:42A5F5&height=220&section=header&text=SUPPLY%20CHAIN%20CONTROL%20TOWER&fontSize=30&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Operational%20Visibility%20%7C%20Risk%20Intelligence%20%7C%20Business%20Insights&descSize=13&descAlignY=58" width="100%" alt="Supply Chain Control Tower animated banner"/>
</a>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=18&duration=2500&pause=700&color=1565C0&center=true&vCenter=true&width=800&lines=Supply+Chain+Analytics;Power+Query+%7C+Data+Modeling+%7C+DAX;Route+Performance+%7C+Freight+%7C+Risk+Analysis;From+Raw+Data+to+Business+Decisions" alt="Animated supply chain analytics introduction"/>

<br/>

![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-1565C0?style=for-the-badge&logo=powerbi&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0D47A1?style=for-the-badge&logo=powerbi&logoColor=white)
![Data Modeling](https://img.shields.io/badge/Data%20Modeling-Star%20Schema-1976D2?style=for-the-badge)
![GitHub](https://img.shields.io/badge/Portfolio-GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

**Transforming supply chain data into operational visibility, risk intelligence, and actionable business insights.**

[View Repository](https://github.com/karthymani58/Supply-chain-control-tower) · [View Excel Workbook](https://github.com/karthymani58/Supply-chain-control-tower/blob/main/Supply%20chain%20Working.xlsx)

</div>

---

## 📌 1. Executive Summary

The **Supply Chain Control Tower** is a business intelligence project focused on supply chain operations, transportation routes, freight costs, trade activity, commodity markets, and external disruption indicators.

The objective is to transform operational data into structured KPIs, interactive dashboards, and evidence-based recommendations that help management monitor performance and investigate potential risks.

The project follows five core business questions:

| Business Question | Analytical Objective |
|---|---|
| What is happening? | Monitor overall operational performance. |
| Where is it happening? | Identify routes, markets, and regions requiring attention. |
| Why is it happening? | Investigate potential causes of delays and disruptions. |
| What could happen next? | Monitor historical trends and available risk indicators. |
| What should management do? | Prioritize investigations and corrective actions. |

### 🎯 Business Objectives

- Analyze transportation and route performance.
- Examine freight costs and trade volumes.
- Investigate delayed operations and disruption indicators.
- Analyze market and country-level information.
- Build a structured Power BI data model.
- Develop DAX measures and interactive dashboards.
- Convert validated analytical findings into management actions.

## 🛠️ 2. Technology Stack

| Technology | Purpose |
|---|---|
| Microsoft Excel | Source data inspection and validation |
| Power Query | Data cleaning and transformation |
| Power BI Desktop | Interactive dashboard development |
| DAX | KPI calculations and business logic |
| Star Schema | Analytical data modeling approach |
| GitHub | Documentation and portfolio presentation |

---

## 📊 3. Dataset Overview

The existing project documentation reports the following figures. Validate them against the source workbook before presenting them as independently verified results.

| Metric | Reported Value |
|---|---:|
| Operational route runs | 30,048 |
| International trade corridors | 50 |
| Geopolitical/operational disruption events | 10,003 |
| Operational weeks | 626 |
| Average shipping delay | 6.38 days |
| Total freight cost | $122,062,713.71 |
| Total trade volume | 569,367,812.73 tons |
| Delayed records | 19,219 |
| Disrupted records | 960 |
| Duplicate records | 0 reported |
| Missing keys | 0 reported |

> These are previously documented project figures, not the result of a new audit. Confirm the metric definitions, currency, units, row grain, and data-quality rules before using them in business decisions.

### Source Workbook Tables

The workbook documentation lists these sheets:

- `Summary`
- `FactRouteOperations`
- `FactTradeRoutes`
- `FacGgeopoliticalEvents`
- `WeeklyTimeline`
- `CountryMetadata`
- `FactCommodityMarket`

Use the exact table names in the workbook and Power BI model. In particular, verify the spelling of `FacGgeopoliticalEvents` before renaming or referencing it.

---

## ⚙️ 4. End-to-End Project Workflow

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=15&duration=2200&pause=500&color=1565C0&center=true&vCenter=true&width=700&lines=01+%E2%86%92+Source+Data;02+%E2%86%92+Power+Query+Transformation;03+%E2%86%92+Data+Modeling;04+%E2%86%92+DAX+Analytics;05+%E2%86%92+Power+BI+Dashboards;06+%E2%86%92+Business+Actions" alt="Animated analytics workflow"/>

</div>

```mermaid
flowchart TD
    A["Excel Source Data"] --> B["Power Query"]
    B --> C["Data Cleaning and Validation"]
    C --> D["Data Modeling"]
    D --> E["DAX Measures and KPIs"]
    E --> F["Power BI Dashboards"]
    F --> G["Business Insights"]
    G --> H["Prioritize and Take Action"]

    classDef source fill:#E3F2FD,stroke:#1565C0,color:#0D47A1
    classDef process fill:#FFFFFF,stroke:#1565C0,color:#263238
    classDef output fill:#DCEBFA,stroke:#0D47A1,color:#0D47A1

    class A source
    class B,C,D,E process
    class F,G,H output
```

### Data Preparation

- Validate column names and data types.
- Investigate null values, errors, and duplicates.
- Standardize dates, categories, and identifiers.
- Validate dimension keys and relationships.
- Reconcile transformed totals with source totals.

---

## 🏗️ 5. Data Modeling — Conceptual Supply Chain Model

A well-designed data model separates measurable operational events from descriptive information. This supports consistent filtering, reusable DAX measures, and easier report maintenance.

**Important:** The diagram below is a conceptual model using your documented table names. The exact primary keys, foreign keys, and relationships must be confirmed against the actual workbook and PBIX model before this is described as the implemented schema.

### 📐 Visual Data Model

```mermaid
flowchart TB
    subgraph DIM["DIMENSION / REFERENCE DATA"]
        WT["WeeklyTimeline<br/>Date / Week Attributes"]
        CM["CountryMetadata<br/>Country / Region Attributes"]
    end

    subgraph FACT["OPERATIONAL AND ANALYTICAL TABLES"]
        RO["FactRouteOperations<br/>Route Performance"]
        TR["FactTradeRoutes<br/>Trade Activity"]
        GE["FacGgeopoliticalEvents<br/>External Events"]
        MC["FactCommodityMarket<br/>Market Indicators"]
    end

    WT -. "Verify date/week key" .-> RO
    WT -. "Verify date/week key" .-> TR
    WT -. "Verify date/week key" .-> GE
    WT -. "Verify date/week key" .-> MC

    CM -. "Verify country/region key" .-> RO
    CM -. "Verify country/region key" .-> TR
    CM -. "Verify country/region key" .-> GE
    CM -. "Verify country/region key" .-> MC

    classDef dimension fill:#E3F2FD,stroke:#1565C0,color:#0D47A1,stroke-width:2px
    classDef fact fill:#FFFFFF,stroke:#1976D2,color:#263238,stroke-width:2px

    class WT,CM dimension
    class RO,TR,GE,MC fact
```

<sub>The dashed connections indicate candidate relationships to investigate, not confirmed joins. Do not create relationships unless compatible keys exist and the dimension side is unique.</sub>

### Why Use a Star Schema?

- Dimensions provide descriptive context for filtering and grouping.
- Fact tables contain measurable business events or observations.
- One-to-many relationships help filter facts through dimensions.
- Consistent dimensions can support comparisons across compatible fact tables.
- A dedicated date dimension supports reliable time-based analysis.

### Recommended Relationship Pattern

```mermaid
flowchart LR
    D["Dimension<br/>Unique Key"] -->|"1 : Many"| F["Fact Table<br/>Foreign Key"]

    classDef dim fill:#E3F2FD,stroke:#1565C0,color:#0D47A1,stroke-width:2px
    classDef fact fill:#FFFFFF,stroke:#1976D2,color:#263238,stroke-width:2px

    class D dim
    class F fact
```

For example, a valid relationship might be:

```text
CountryMetadata[CountryKey]  1 ───── *  FactRouteOperations[CountryKey]
```

This is only an example. Use it only if both columns exist, the country dimension key is unique, and the values match.

### Data Model Validation Checklist

- [ ] Define the grain of every fact table.
- [ ] Identify candidate primary keys and foreign keys.
- [ ] Check dimension key uniqueness.
- [ ] Check for unmatched fact-table keys.
- [ ] Prefer one-to-many relationships where appropriate.
- [ ] Avoid unnecessary many-to-many relationships.
- [ ] Avoid direct fact-to-fact relationships unless specifically justified.
- [ ] Confirm date/week relationships.
- [ ] Validate relationship filter directions.
- [ ] Reconcile report totals after modeling.

### Suggested Modeling Improvements

Where the source data supports them, consider creating:

- `DimDate` — a proper calendar table.
- `DimRoute` — unique route information.
- `DimCountry` — standardized country and region attributes.
- `DimMarket` — standardized market attributes.

Do not create these as disconnected or duplicated dimensions without a clear modeling purpose. Verify whether `CountryMetadata` or `WeeklyTimeline` already provides the required attributes.

---

## 📈 6. Five Dashboard Pages

The following is the intended analytical structure. Keep the descriptions aligned with the pages actually implemented in the Power BI report.

### Page 1 — Executive Control Tower

**Question: What is happening?**

Recommended KPIs:

- Total operational records
- Total freight cost
- Total trade volume
- Average shipping delay
- Delayed records
- Disruption events

Recommended visuals:

- KPI cards
- Operational trend over time
- Freight cost by region or market
- Route performance comparison
- Delay and disruption overview

**Management objective:** Identify exceptions and understand overall operating performance.

### Page 2 — Route Performance & Operations

**Question: Where is it happening?**

Recommended visuals:

- Route-level performance matrix
- Route activity comparison
- Delay analysis by route
- Freight cost by route
- Origin and destination analysis
- Active and inactive route counts, if valid status fields exist

**Management objective:** Prioritize routes for operational investigation.

### Page 3 — Freight & Commodity Market Intelligence

**Question: How do freight and market conditions vary?**

Recommended visuals:

- Freight cost by market
- Trade volume by region or commodity
- Weekly or monthly trends
- Market comparisons
- Cost and volume analysis

**Management objective:** Understand changes in trade activity and freight expenditure.

### Page 4 — Geopolitical Risk & External Events

**Question: Where might operations be exposed to disruption?**

Recommended visuals:

- External events over time
- Events by country or region
- Risk category analysis
- Route exposure, where a valid route-to-event mapping exists
- Operational performance compared with external indicators

**Management objective:** Investigate potential exposure and support contingency planning.

> Correlation between external events and operational delays does not by itself prove causation.

### Page 5 — Sustainability & Supply Chain Resilience

**Question: What should management improve?**

Recommended visuals:

- Available sustainability indicators
- Route or market concentration
- Resilience indicators
- Disruption exposure trends
- Prioritized exceptions and follow-up actions

**Management objective:** Identify opportunities to strengthen resilience using evidence available in the dataset.

> Do not report carbon emissions or other sustainability KPIs unless the source data supports the required calculations.

---

## 🧮 7. DAX Measures — Starter Templates

The measures below are templates. Replace table and column names with those in the actual Power BI model and validate the business definitions.

### Total Operational Records

```dax
Total Operational Records =
COUNTROWS ( FactRouteOperations )
```

Use a distinct business identifier instead if one operational event occupies multiple rows.

### Total Freight Cost

```dax
Total Freight Cost =
SUM ( FactRouteOperations[FreightCost] )
```

Replace `FreightCost` with the actual freight-cost column.

### Total Trade Volume

```dax
Total Trade Volume =
SUM ( FactTradeRoutes[TradeVolume] )
```

Confirm the source column and unit of measurement.

### Average Shipping Delay

```dax
Average Shipping Delay (Days) =
AVERAGE ( FactRouteOperations[ShippingDelayDays] )
```

Use only if a validated numeric delay column exists.

### Delayed Records

```dax
Delayed Records =
CALCULATE (
    COUNTROWS ( FactRouteOperations ),
    FactRouteOperations[DeliveryStatus] = "Delayed"
)
```

Adapt the status value and row-counting logic to the actual dataset.

### Delay Percentage

```dax
Delay % =
DIVIDE (
    [Delayed Records],
    [Total Operational Records],
    0
)
```

Format the measure as a percentage. The numerator and denominator must use a consistent grain.

### Total External Event Records

```dax
External Event Records =
COUNTROWS ( FacGgeopoliticalEvents )
```

This counts rows, not necessarily unique events. If an event identifier exists, consider `DISTINCTCOUNT`.

### Operational Records — Weekly Trend

```dax
Operational Records =
COUNTROWS ( FactRouteOperations )
```

Use a validated date/week field on the visual axis and confirm that the date relationship filters the fact table correctly.

### DAX Best Practices

- Use measures for filter-responsive calculations.
- Use `DIVIDE()` for ratios.
- Use `VAR` and `RETURN` for complex calculations.
- Validate filter context and totals.
- Use consistent units and number formats.
- Reconcile key KPIs against source data.

---

## 🔍 8. Business Insight Framework

| Business Question | Analysis | Possible Action |
|---|---|---|
| What is happening? | Review operational KPIs and trends. | Monitor exceptions against targets. |
| Where is it happening? | Compare routes, markets, and regions. | Prioritize the highest-impact areas. |
| Why is it happening? | Investigate delays and supporting operational evidence. | Validate root causes before changing processes. |
| What could happen next? | Monitor historical trends and risk indicators. | Prepare contingency plans. |
| What should management do? | Rank issues by impact and urgency. | Assign actions, owners, and review dates. |

### How to Document a Finding

For each actual insight, record:

1. **Observation:** What does the report show?
2. **Evidence:** Which KPI, comparison, or trend supports it?
3. **Business impact:** Why does it matter?
4. **Recommendation:** What action should be considered?
5. **Follow-up:** Who owns the action, and when will it be reviewed?

The dashboard should communicate validated findings rather than assume that every unusual pattern has a single proven cause.

---

## 🧹 9. Data Quality & Power Query

### Data Preparation Steps

1. Inspect source tables and column names.
2. Correct date, numeric, and text data types.
3. Standardize category values and identifiers.
4. Investigate nulls, errors, and missing keys.
5. Check duplicates using the defined business grain.
6. Validate costs, quantities, and dates.
7. Check foreign-key coverage.
8. Reconcile source and transformed totals.
9. Document assumptions and exclusions.
10. Refresh the report and retest key measures.

### Quality Checklist

- [ ] Source row counts recorded.
- [ ] Data types validated.
- [ ] Missing values investigated.
- [ ] Duplicate records investigated.
- [ ] Dimension keys checked for uniqueness.
- [ ] Fact-to-dimension relationships validated.
- [ ] KPI totals reconciled.
- [ ] Refresh tested successfully.

---

## 🎨 10. Dashboard Design Theme

The recommended style is a clean white-and-blue executive dashboard.

| Element | Color |
|---|---|
| Page background | `#FFFFFF` |
| Primary blue | `#1565C0` |
| Dark blue | `#0D47A1` |
| Light blue | `#E3F2FD` |
| Main text | `#263238` |
| Secondary text | `#607D8B` |

### Design Principles

- Use consistent page headers.
- Keep KPI cards simple and readable.
- Apply consistent number formats.
- Use slicers for relevant dimensions.
- Use conditional formatting with documented thresholds.
- Avoid unnecessary visual clutter.
- Make chart titles communicate the business question.

---

## 🚀 11. How to Access the Project

### Repository

[Open Supply Chain Control Tower on GitHub](https://github.com/karthymani58/Supply-chain-control-tower)

### Clone the Repository

```bash
git clone https://github.com/karthymani58/Supply-chain-control-tower.git
cd Supply-chain-control-tower
```

### Open the Source Workbook

Open `Supply chain Working.xlsx` in Excel and verify the actual source sheets and columns.

### Open Power BI

Open the `.pbix` file if it is available in the repository or in your local project folder.

Then:

1. Check Power Query source paths.
2. Review the model relationships.
3. Validate DAX measures.
4. Refresh the report.
5. Compare important results against the source data.

**Note:** Add links to the PBIX and dashboard screenshots only after the corresponding files have been committed to GitHub.

---

## 📂 12. Suggested Repository Structure

```text
Supply-chain-control-tower/
│
├── README.md
├── Supply chain Working.xlsx
├── archive.zip
│
├── PowerBI/
│   └── Supply_Chain_Control_Tower.pbix
│
├── Screenshots/
│   ├── executive_control_tower.png
│   ├── route_performance.png
│   ├── market_intelligence.png
│   ├── geopolitical_risk.png
│   └── resilience_sustainability.png
│
└── Documentation/
    ├── data_model.md
    ├── dax_measures.md
    └── data_quality_checks.md
```

This is a suggested structure. Create the folders only when the relevant files are ready.

---

## 💼 13. Skills Demonstrated

- Excel data inspection and validation
- Power Query data transformation
- Data modeling and star-schema concepts
- DAX measures and KPI development
- Power BI dashboards
- Route and operational performance analysis
- Freight and trade analytics
- External risk indicator analysis
- Data quality and reconciliation
- Business insight communication
- GitHub portfolio documentation

---

## 🔮 14. Future Enhancements

- Automated data refresh and quality monitoring.
- Validated shipment tracking integration.
- Predictive delay-risk analysis.
- Evidence-based root-cause analysis.
- Role-specific reporting for operations and leadership.
- Sustainability measures where suitable data exists.
- Exception thresholds, ownership, and action tracking.
- Performance monitoring after corrective actions.

---

## 👨‍💻 15. About the Project

The Supply Chain Control Tower demonstrates how data preparation, analytical modeling, KPI development, and visualization can support supply chain decision-making.

**Focus areas:** Supply Chain Analytics · Data Analytics · Business Intelligence · Power BI · DAX · Data Modeling

<div align="center">

### ⭐ If you find this project useful, consider starring the repository!

**Excel · Power Query · Power BI · DAX**

*Turning supply chain data into actionable decisions.*

[Back to Top](#-supply-chain-control-tower--excel--power-bi)

</div>

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

<div align="center">

*Designed for professional supply chain analytics and business intelligence reporting.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0078D4,100:217346&height=120&section=footer" width="100%" alt="Animated project footer"/>

</div>
