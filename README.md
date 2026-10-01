# Global Health and Life Expectancy: A Data-Driven Analysis of Development Disparities (1990–2023)
>One sentence: Analyzed World Bank health indicators across 190+ countries to uncover global life expectancy trends and disparities, visualized in an interactive Power BI dashboard.
---

## ⚙️ Project Type Flags
Check what applies. This helps reviewers and collaborators understand the nature of the work at a glance. Delete this block before publishing.*

- [ ] Exploratory Data Analysis (EDA)
- [ ] SQL Analysis / Querying
- [x] Dashboard / Data Visualization
- [ ] Data Pipeline / ETL
- [ ] Predictive Modelling / Machine Learning
- [x] Data Cleaning / Wrangling
- [x] End-to-End (multiple of the above)
- [ ] Other: ___________

---

## Table of Contents
1. [Project Overview](#1-project-overview)
2. [Objectives](#2-objectives)
3. [Project Scope & Tools](#3-project-scope--tools)
4. [Repository Structure](#4-repository-structure)
5. [Data Workflow](#5-data-workflow)
6. [Data Model & Schema](#6-data-model--schema)
7. [Analysis & Metrics](#7-analysis--metrics)
8. [Key Insights](#8-key-insights)
9. [Recommendations](#9-recommendations)
10. [Assumptions & Limitations](#10-assumptions--limitations)
11. [Future Enhancements](#11-future-enhancements)
12. [Deliverables](#12-deliverables)
13. [Author](#13-author)

---

## 1. Project Overview

**Context:** Final capstone project for the AnalystLab Africa Data Analytics Internship, applying the complete end-to-end analytics workflow — from raw data acquisition to a finished, interactive dashboard — to a real-world global development dataset.

**Problem Statement:** How do life expectancy and key health outcomes vary across countries and over time, and what patterns or factors are associated with better health performance?

**Approach:** The World Bank's World Development Indicators (WDI) bulk dataset was downloaded, filtered down to a set of health-focused indicators, and cleaned/transformed in Power Query (Power BI). The cleaned data was then modeled and visualized in an interactive Power BI dashboard with KPI cards, a country map, a historical trend line, and country-ranking charts.

**Outcome:**  A fully interactive Power BI dashboard and accompanying report identifying which countries lead in life expectancy, how global health outcomes have evolved since 1960, and what that suggests for health policy and investment priorities.
 
---

## 2. Objectives

- **Primary Objective:** Analyze global life expectancy and related health indicator trends using the World Bank's WDI dataset.
- **Secondary Objective 1:** Identify the countries with the highest life expectancy as of the most recent complete year (2023).
- **Secondary Objective 2:** Build an interactive dashboard that allows a user to explore different health indicators and time periods.
- **Secondary Objective 3:**  Surface actionable insights and recommendations for health investment priorities.

> 💡 *Every analysis decision in this project traces back to one of these objectives.*

---

## 3. Project Scope & Tools

### Scope

| Dimension | Details |
|-----------|---------|
| **In Scope** | Health-related indicators (life expectancy, under-5 mortality, maternal mortality, hospital beds, health expenditure, immunization) across all individual countries |
| **Out of Scope** | Non-health WDI indicators (economy, education, trade, environment, etc.); regional and income-group aggregates (e.g., World, Africa Eastern and Southern) |
| **Time Period** |1960–2023 |
| **Granularity** | Country-year level|

### Tools & Technologies

| Category | Tool(s) Used |
|----------|-------------|
| Data Storage | CSV (World Bank WDI bulk download |
| Data Processing | Power Query (Power BI |
| Analysis | Power BI (DAX, aggregations |
| Visualization | Power BI Desktop (Filled Map, Line, Bar, Donut/Pie, Card visuals) |
| Version Control | Git / GitHub |
| Documentation | [e.g., Markdown |
---

## 4. Repository Structure

```
project-root/
├── data/
│   ├── raw/                 # Original WDICSV.csv (unmodified source data)
│   └── processed/           # Cleaned, unpivoted health-indicator dataset
├── reports/
│   └── WDI_Health_Capstone_Report.pdf   # Final report (objective, methodology, findings, recommendations)
├── visuals/
│   ├── WDI_Health_Dashboard.pbix        # Power BI dashboard file
│   └── screenshots/                     # PNG exports of each dashboard view
├── docs/
│   └── indicator-reference.md           # Indicator codes/definitions used
└── README.md                            # You are here
```

---

## 5. Data Workflow

```
World Bank WDI Bulk CSV (WDICSV.csv)
        ↓
Downloaded & loaded into Power Query
        ↓
Cleaning & Transformation
        ↓
Modeling & DAX Measures (Power BI)
        ↓
Dashboard / Visualization (Power BI)

```

1. **Source:** World Bank World Development Indicators (WDI) bulk CSV download, covering 200+ countries and all WDI indicators, 1960–present.
2.**Ingestion:** Downloaded as WDI_CSV.zip, extracted, and loaded WDICSV.csv into Power BI via Power Query.
3.**Cleaning:** Filtered to 6 health indicators, removed regional/income-group aggregates, fixed a mis-typed Year column (originally read as a date serial number), unpivoted year columns into a long format.
4.**Transformation:** Converted from wide format (years as columns) to long format (Country, Indicator, Year, Value) to support time-series and filterable visuals.
5.**Analysis:** Descriptive averages (KPI cards), geospatial comparison (map), trend analysis (line chart), and ranking (bar/pie charts), all made interactive via slicers.
6.**Output:** Interactive Power BI dashboard, PDF report, and dashboard screenshots.

---

## 6. Data Model & Schema

### Dataset / Table: `WDICSV (cleaned, long format)`

| Field Name | Data Type | Description | Example Value |
|------------|-----------|-------------|---------------|
| `Country Name` | string | Full country name | "Nigeria" |
| `Country Code` | string | ISO 3-letter country code |"NGA" |
| `Indicator Name` | string| Full name of the health indicator |"Life expectancy at birth, total (years)" |
| `Indicator Code` | string | WDI indicator code | "SP.DYN.LE00.IN" |
| `Year` | whole number | Year of observation| 2023 |
| `Value` | decimal | Indicator value for that country/year | 73.79 |
> **Row count (approx.):**  ~90,000 rows (6 indicators × ~190 countries × ~64 years, with gaps for indicators lacking full historical coverage)
> **Date range:** 1960–2023
> **Key join / relationship:**Single flat table; no joins required — Country Name/Code, Indicator Name/Code, Year, and Value all live in one row per observation.

---
## 8. Analysis & Metrics
### Analytical Approach
This was primarily an exploratory and descriptive analysis: filtering a large global indicator dataset down to a health-focused subset, then summarizing, comparing, and visualizing patterns across countries and time — rather than testing a specific statistical hypothesis.

### Key Metrics Defined

| Metric | Plain-Language Definition | Why It Matters |
|--------|--------------------------|----------------|
| `Avg. Life Expectancy` | Average years a newborn is expected to live, across countries | Core measure of overall population health |
| `Avg. Under-5 Mortality Rate` | Average deaths per 1,000 live births before age 5 | Reflects child healthcare access and quality |
| `Avg. Maternal Mortality Rate` | Average maternal deaths per 100,000 live births | Reflects maternal healthcare quality |
| `Avg. Health Expenditure` | Average health spending per capital | Reflects national investment in healthcare |
### Methods Used
- Descriptive statistics — average values per indicator, by country and globally
- Trend analysis across time (1960–2023)
- Geographic/country comparison via choropleth map
- Ranking / Top-N comparison (bar chart and pie/donut chart)
- Interactive filtering by Year and Indicator via slicers

---

## 9. Key Insights

**Insight 1:** Development and longevity are closely linked. Smaller, high-income nations — Switzerland, Monaco, Luxembourg, Norway, Denmark — consistently top the 2023 life expectancy rankings, pointing to a strong association between economic development, healthcare investment, and health outcomes.

**Insight 2:** Steady historical progress, with a visible shock. Global average life expectancy has risen consistently since 1960, reflecting decades of improvement in healthcare, sanitation, and disease control — but a clear dip appears around 2020–2021, consistent with the global disruption of the COVID-19 pandemic.

**Insight 3:** Resource gaps persist. Health expenditure, hospital bed availability, and immunization coverage vary widely across countries, with lower-income regions generally reporting lower averages across all three resource indicators.

---


## 10. Recommendations

| Priority | Recommendation | Based On | Suggested Owner |
|----------|---------------|----------|-----------------|
| High | Increase investment in healthcare infrastructure (hospital beds, expenditure per capita) in lower-ranked regions | Insight 1 & 3 | Health ministries / policymakers |
| Medium | Sustain and expand immunization program funding | Insight 3 |Public health agencies | Public health agencies
| Low | Extend analysis with socioeconomic indicators (GDP per capita, education) to further validate the development–health relationship | Insight 1| Future analysts |

---

## 11. Assumptions & Limitations
### Assumptions

- Regional and income-group aggregates (e.g., "World," "Africa Eastern and Southern") were excluded to focus on individual country-level comparison.
- Missing values in earlier decades for indicators like immunization and health expenditure reflect genuine historical non-reporting, not data errors.
  
### Limitations
- 2024–2025 data was largely incomplete at the time of analysis due to standard World Bank reporting lag.
- Some indicators considered for this project (e.g., physicians per 1,000 people, basic drinking water/sanitation access) were not available in this particular WDI release and were excluded.
- This is a descriptive/exploratory analysis; no causal or statistical significance testing was performed on the development–health relationship.

> *The goal here is pre-emptive Q&A. A more rigorous follow-up could include correlation analysis against GDP per capita or education indicators..*

---

## 12. Future Enhancements

- [ ] Add GDP per capita and education indicators to statistically test the development–health relationship
- [ ] Build a Bottom 10 countries view alongside the existing Top 10
- [ ] Automate refresh from the latest WDI release via Power Query web connector
- [ ] Add regional (continent-level) roll-up comparisons

---

## 13. Deliverables
 
| Deliverable | Description | Location |
|-------------|-------------|----------|
| Final Report | PDF covering objective, methodology, findings, recommendations | reports/WDI_Health_Capstone_Report.pdf |
| Power BI Dashboard | Interactive .pbix file with KPI cards, map, trend line, bar and pie charts, slicers | `visuals/WDI_Health_Dashboard.pbix` |
| Dashboard Screenshots | PNG exports of each dashboard view | [`visuals/screenshot` |


---

## 14. Author

**Vivian Okwara**
Data Analyst | Lagos, Nigeria 

- 🔗 LinkedIn: https://linkedin.com/in/okwara-vivian
- 💼 https://Vivian-Portfolio. github.io
- 📧 Email: okwaravivian26@gmail.com
---

*Last updated: August 2026*


---

*Last updated: [Month YYYY]*
*If this template helped you, consider starring the repository.*
