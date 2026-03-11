# HR Workforce Analytics Dashboard

> An interactive Power BI dashboard analyzing workforce demographics, labor costs, and headcount trends across a 3-year period (2016–2018).

---

## Overview

This project visualizes key Human Resources metrics for a company of **1,709 employees**, providing insights into workforce composition, compensation structure, and attrition — enabling data-driven HR decisions.

| Metric | Value |
|---|---|
| Total Employees | 1,709 |
| Attrition Rate | 5.23% |
| Average Salary | 21,422 |
| Data Period | 2016 – 2018 |

---

## Dataset

**File:** `datasetcv10.xlsx`  
**Sheet:** `Data`  
**Records:** 1,709 rows × 17 columns

### Columns

| Column | Description |
|---|---|
| `Date` | Snapshot date of the record |
| `EmpID` | Unique employee identifier |
| `Gender` | Male / Female |
| `Department` | Employee's department |
| `Position` | Job title |
| `Age` | Employee age (numeric) |
| `Age Group` | Grouped age bracket (formula-derived) |
| `EthnicGroup` | Ethnic group classification (Group A–G) |
| `Employment Type` | Full-time (FT) / Part-time (PT) |
| `BU Region` | Business unit region (North, South, East, West) |
| `HireDate` | Date employee was hired |
| `EndDate` | Date employment ended (blank if still active) |
| `Status` | Active / Inactive (formula-derived from EndDate) |
| `PayType` | Salary / Hourly |
| `AgeGroup` | Alternative age grouping (`<25`, `25–34`, etc.) |
| `Date (Year)` | Year extracted from Date |
| `Income` | Employee income / labour cost |

### Key Dimensions

- **Departments (10):** IT, HR, Logistics, Finance, Marketing, Technical, Operations, CS, Legal, Sales
- **BU Regions (4):** North (755), South (477), East (281), West (196)
- **Pay Types:** Salary (744 employees), Hourly (965 employees)
- **Employment Types:** Full-time (744), Part-time (965)
- **Ethnic Groups:** Group A through Group G

---

## Dashboard Sections

### 1. KPI Summary (Top Row)
- **Total Employees** — headcount snapshot
- **Attrition Rate** — percentage of employees who left
- **Average Salary** — mean compensation across all employees

### 2. Workforce Demographics (Left Panel)
- **Gender Distribution** — donut chart: 892 Male vs. 817 Female
- **Age Distribution** — horizontal bar chart by age group (Under 25, 25–34, 35–44, 45–54, 55+); largest group is Under 25
- **Total Employees by Department** — bar chart across 10 departments; IT leads with 223 employees

### 3. Labour Cost Analysis (Center)
- **Total Labour Cost by Ethnic Group & Contract Type** — grouped bar chart comparing Hourly vs. Salary costs across Groups A–G; Group G has the highest salary cost (3.818M)
- **Total Labour Cost by Department** — horizontal bar chart; IT leads at 4.773M, Sales lowest at 2.271M

### 4. Trend Analysis (Right Panel)
- **Trending Total Labor Cost by Year** — line chart (2016–2018) showing Hourly and Salary cost trends; both grow steadily with Salary costs higher overall
- **Total Labour Cost & Headcount** — combo chart; headcount grew from 499 (2016) → 553 (2017) → 657 (2018); total income grew from 10.643M → 11.813M → 14.156M
- **Total Headcount by BU Region** — treemap showing regional distribution: North dominates (755), followed by South (477), East (281), West (196)

### 5. Year Filter (Left Sidebar)
- Slicer buttons for **2016**, **2017**, **2018** enabling year-by-year analysis

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Microsoft Excel | Data storage and formula-based column derivation |
| Power BI | Dashboard design and interactive visualization |

---

## Key Insights

-  **Headcount grew 31.7%** from 2016 to 2018 (499 → 657 employees)
-  **IT department** has both the most employees and the highest labour cost
-  **North region** accounts for ~44% of total headcount
-  **Hourly workers outnumber salaried** employees (965 vs. 744)
-  **Under-25s are the largest age group**, suggesting a young workforce
-  **Attrition is relatively low** at 5.23%, indicating good retention

---

## How to Use

1. Open `datasetcv10.xlsx` to explore or update the raw data
2. Open the Power BI `.pbix` file and refresh the data source if needed
3. Use the **year slicer** (2016 / 2017 / 2018) on the left panel to filter all visuals
4. Hover over charts for detailed tooltips and drill-through options
