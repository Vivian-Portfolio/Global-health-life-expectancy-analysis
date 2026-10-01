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
- [ ] End-to-End (multiple of the above)
- [ ] Other: ___________

---

## Table of Contents
1. [Project Overview](#1-project-overview)
2. [Objectives](#2-objectives)
3. [Project Scope & Tools](#3-project-scope--tools)
4. [Repository Structure](#4-repository-structure)
5. [Data Workflow](#5-data-workflow)
6. [Data Model & Schema](#6-data-model--schema)
7. [ERD - Entity Relationship Diagram](#7-erd--entity-relationship-diagram) *(SQL projects)*
8. [Analysis & Metrics](#8-analysis--metrics)
9. [Key Insights](#9-key-insights)
10. [Recommendations](#10-recommendations)
11. [Assumptions & Limitations](#11-assumptions--limitations)
12. [Future Enhancements](#12-future-enhancements)
13. [Deliverables](#13-deliverables)
14. [Author](#14-author)

---

## 1. Project Overview
 
 1. Project Overview
**Context:** Final capstone project for the AnalystLab Africa Data Analytics Internship, applying the complete analytics workflow to a real-world global dataset.

**Problem Statement:** How do life expectancy and key health outcomes vary across countries and over time, and what factors are associated with better health performance?

**Approach:** Cleaned and transformed World Bank WDI health indicators in Power Query, then built an interactive Power BI dashboard with KPIs, a map, trend analysis, and country rankings.

**Outcome:** A fully interactive dashboard and report identifying which countries lead in life expectancy and how global health outcomes have evolved since 1960.

---

## 2. Objectives

- **Primary Objective:** Analyze global life expectancy and health indicator trends using WDI data.
- **Secondary Objective 1:** Identify the countries with the highest and lowest life expectancy as of 2023.
- **Secondary Objective 2:** Build an interactive dashboard allowing users to explore different health indicators and years.

> 💡 *Every analysis decision in this project traces back to one of these objectives.*

---

## 3. Project Scope & Tools

### Scope

| Dimension | Details |
|-----------|---------|
| **In Scope** | Health indicators (life expectancy, mortality, expenditure, immunization) across all available countries, 1960–2023 |
| **Out of Scope** | Non-health WDI indicators (economy, education, trade) |
| **Time Period** |1960–2023 |
| **Granularity** | Country-year level|

### Tools & Technologies

| Category | Tool(s) Used |
|----------|-------------|
| Data Storage | CSV (World Bank WDI bulk download |
| Data Processing | Power Query (Power BI |
| Analysis | Power BI (DAX, aggregations |
| Visualization | Power BI Desktop |
| Version Control | Git / GitHub |
| Documentation | [e.g., Markdown |

---

## 4. Repository Structure

```
[project-root]/
│
├── data/
│   ├── raw/                  # Original, unmodified source data - never edited
│   ├── processed/            # Cleaned and transformed data
│   └── external/             # Reference data, lookup tables, third-party files
│
├── notebooks/                # Jupyter, R Markdown, or Colab notebooks
│
├── scripts/                  # Reusable .py, .R, or .sh processing files
│
├── queries/                  # SQL files (retain this folder for SQL-heavy projects)
│   ├── exploratory/          # Ad-hoc or investigative queries
│   ├── transformations/      # Cleaning and reshaping logic
│   └── final/                # Production-ready or presentation queries
│
├── reports/                  # Final outputs: PDFs, slide decks, Word docs
│
├── visuals/                  # Exported charts, dashboard screenshots, ERD diagrams
│
├── docs/                     # Data dictionaries, schema notes, reference material
│
├── project_metadata.yml      # Machine-readable metadata (optional)
└── README.md                 # You are here
```

> ⚠️ *Delete folders you didn't use. An empty folder is worse than no folder.*
> SQL-heavy projects: keep `queries/`. Analysis-only projects: keep `notebooks/`. Both? Keep both.

---

## 5. Data Workflow

```
[Data Source(s)]
      ↓
[Ingestion / Collection Method]
      ↓
[Cleaning & Transformation]
      ↓
[Analysis / Modelling / Querying]
      ↓
[Output / Visualisation / Reporting]
```

1. **Source:** [Where did the data come from? Format, size, access method.]
2. **Ingestion:** [How was it brought in?]
3. **Cleaning:** [What issues did you find and fix?]
4. **Transformation:** [What new fields, aggregations, or structures did you create?]
5. **Analysis:** [What methods - statistical, visual, query-based, model-based?]
6. **Output:** [What form do the results take?]

---

## 6. Data Model & Schema

### Dataset / Table: `[name]`

| Field Name | Data Type | Description | Example Value |
|------------|-----------|-------------|---------------|
| `[field_1]` | [string / int / date / float / boolean] | [What this field represents] | [Non-sensitive example] |
| `[field_2]` | [string / int / date / float / boolean] | [What this field represents] | [Non-sensitive example] |
| `[field_3]` | [string / int / date / float / boolean] | [What this field represents] | [Non-sensitive example] |

> **Row count (approx.):** [X rows]
> **Date range:** [Start] – [End]
> **Key join / relationship:** [e.g., `orders.customer_id` → `customers.id`]

*Add additional table blocks as needed for multi-table projects.*

---
## 8. Analysis & Metrics
### Analytical Approach

[Describe how you approached the analysis. Were you exploring patterns? Testing a hypothesis? Building and validating a pipeline? Be honest about your method - exploratory work is valid, just call it that.]

### Key Metrics Defined

| Metric | Plain-Language Definition | Why It Matters |
|--------|--------------------------|----------------|
| `[Metric 1]` | [What it measures, in one sentence] | [What decision or question it answers] |
| `[Metric 2]` | [What it measures, in one sentence] | [What decision or question it answers] |
| `[Metric 3]` | [What it measures, in one sentence] | [What decision or question it answers] |

### Methods Used

- [e.g., Descriptive statistics - distribution, central tendency, outlier detection]
- [e.g., Trend analysis across [time period]]
- [e.g., Segmentation / group comparison by [dimension]]
- [e.g., Correlation analysis between [variable A] and [variable B]]
- [e.g., SQL window functions for [specific aggregation]]
- [e.g., Custom aggregation or transformation logic in [tool]]

---

## 9. Key Insights

**Insight 1:** Development and longevity are closely linked — smaller, high-income nations (Switzerland, Monaco, Luxembourg, Norway) consistently top the life expectancy rankings.
**Insight 2:** Steady historical progress — global average life expectancy has risen consistently since 1960, reflecting long-term gains in healthcare and sanitation.
**Insight 3:** Pandemic impact is visible in the data — a clear dip appears around 2020–2021, aligning with COVID-19's global disruption.
10. Recommendations

**Insight 1: [Short descriptive headline]**
[What you found + what it suggests. One short paragraph.]

**Insight 2: [Short descriptive headline]**
[What you found + what it suggests.]

**Insight 3: [Short descriptive headline]**
[What you found + what it suggests.]

**Insight 4 (if applicable): [Short descriptive headline]**
[What you found + what it suggests.]

---

## 10. Recommendations

| Priority | Recommendation | Based On | Suggested Owner |
|----------|---------------|----------|-----------------|
| High | Increase healthcare infrastructure investment in lower-ranked regions | Strong link between development and life expectancy| Health ministries/policymakers |
| Medium | Sustain immunization program funding |Low-cost, high-impact intervention |Public health agencies |
| Low | Expand analysis with GDP/education data | To validate development–health relationship further | Future analysts |

---

## 11. Assumptions & Limitations
### Assumptions

- Assumptions: Regional/income-group aggregates were excluded to focus on individual country comparisons; missing early-year data for some indicators reflects genuine reporting gaps, not errors.
Limitations: 2024–2025 data was largely incomplete due to WDI reporting lag; some indicators (e.g., physicians per capita) were unavailable in this dataset release.
- [What did you treat as true without being able to verify?]
- [What simplifications did you make for scope or feasibility?]
- [What domain rules or definitions did you accept as given?]

### Limitations
- Limitations: 2024–2025 data was largely incomplete due to WDI reporting lag; some indicators (e.g., physicians per capita) were unavailable in this dataset release.
- [What analysis was out of scope but could affect interpretation?]
- [What would a more rigorous version of this project include?]
- [Are there known biases in the data source or collection method?]

> *The goal here is pre-emptive Q&A. What would a thoughtful skeptic push back on? Document the answer here, before they ask.*

---

## 12. Future Enhancements
- [ ] [Enhancement 1 - specific and traceable to a real gap in this project]
- [ ] [Enhancement 2]
- [ ] [Enhancement 3]
- [ ] [Enhancement 4]

---

## 13. Deliverables

Final Report

/reports/


/visuals/

PNG exports of each dashboard view
/visuals/

| Deliverable | Description | Location |
|-------------|-------------|----------|
| Final Report | PDF covering objective, methodology, findings, recommendations | [`/path/to/file`] |
| Power BI Dashboard | Interactive .pbix file | [`/path/to/file`] |
| Dashboard Screenshots | PNG exports of each dashboard view | [`/path/to/file`] |

---

## 14. Author

**[Your Name]**
[Your role or title - current or target]

- 🔗 [LinkedIn URL]
- 💼 [Portfolio or GitHub profile URL]
- 📧 [Email - optional]

---

*Last updated: [Month YYYY]*
*If this template helped you, consider starring the repository.*
