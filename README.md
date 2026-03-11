# Data Portfolio: HR Workforce Analytics Dashboard

---

## Table of Contents
- [Objective](#objective)
- [Tools Used](#tools-used)
- [Dataset](#dataset)
- [Measures](#measures)
- [Dashboard Sections](#dashboard-sections)
- [Key Insights](#key-insights)
- [Repository Structure](#repository-structure)

---

## Objective

Help HR teams and management quickly understand:
- Overall workforce composition and demographics
- Labour cost breakdown by department, ethnic group, and contract type
- Headcount and cost trends over time (2016–2018)

---

## Tools Used

| Tool | Purpose |
|---|---|
| Microsoft Excel | Data cleaning, filtering, pivot tables, measures & dashboard |

---

## Dataset

**File:** `datasetcv10.xlsx` — 1,709 rows × 17 columns

| Column | Description |
|---|---|
| `Date` | Record snapshot date |
| `EmpID` | Unique employee identifier |
| `Gender` | Male / Female |
| `Department` | Employee's department |
| `Position` | Job title |
| `Age` | Employee age |
| `Age Group` | Age bracket (formula-derived) |
| `EthnicGroup` | Ethnic group classification (Group A–G) |
| `Employment Type` | Full-time (FT) / Part-time (PT) |
| `BU Region` | Business unit region (North / South / East / West) |
| `HireDate` | Date of hire |
| `EndDate` | End date (blank if still active) |
| `Status` | Active / Inactive (formula-derived from EndDate) |
| `PayType` | Salary / Hourly |
| `AgeGroup` | Alternative age grouping |
| `Date (Year)` | Year extracted from Date |
| `Income` | Employee income / labour cost |

---

## Measures

Key metrics calculated using Excel formulas and Pivot Tables:

```excel
-- Total Employees
=COUNTA(Data[EmpID])

-- Active / Inactive Employees
=COUNTIF(Data[Status], "Active")
=COUNTIF(Data[Status], "InActive")

-- Attrition Rate
=COUNTIF(Data[Status],"InActive") / COUNTA(Data[EmpID])

-- Average Income
=AVERAGE(Data[Income])

-- Total Labour Cost
=SUM(Data[Income])

-- Age Group (formula-derived column)
=IF([@Age]<25,"Under 25",IF([@Age]<35,"25–34",IF([@Age]<45,"35–44",IF([@Age]<55,"45–54","55+"))))

-- Status (formula-derived column)
=IF(ISBLANK([@EndDate]),"Active","InActive")
```

---

## Dashboard Sections

### 1. KPI Summary
Out of **1,709 employees**, 1,624 are active with only 85 inactive — an attrition rate of **5.23%**, reflecting strong retention. Average income is **21,422**.

### 2. Workforce Demographics

| Dimension | Highlight |
|---|---|
| **Gender** | Male 892 (52.2%) vs. Female 817 (47.8%) — near-balanced |
| **Age** | Under 25 dominates at **703 (41.1%)**, nearly 2× the 25–34 group (325) |
| **Top Dept** | IT leads headcount at **223**; Sales is smallest at **140** (−37%) |

### 3. Labour Cost Analysis

**By Ethnic Group:** Total labour cost is **36,610,903** — Salary accounts for **57.6%** (21,070,072) vs. Hourly 42.4% (15,540,831).

| Group | Hourly | Salary | Total |
|---|---|---|---|
| Group E | 2,680,152 | 3,343,829 | **6,023,981** |
| Group B | 2,048,088 | 3,616,489 | **5,664,577** |
| Group G | 1,801,403 ↓ | 3,818,043 ↑ | **5,619,446** |
| Group A | 2,311,927 | 2,222,005 | **4,533,932** |

> Group G has the **highest Salary** but **lowest Hourly** cost — predominantly salaried workforce.

**By Department:** IT is the costliest at **4,772,538** — 2.1× more than Sales (2,270,588). HR (4,418,918) and Logistics (4,376,141) follow closely.

### 4. Trend Analysis

**Labour Cost by Year:**

| Year | Hourly | Salary | Total | YoY Growth |
|---|---|---|---|---|
| 2016 | 4,247,408 | 6,395,210 | 10,642,618 | — |
| 2017 | 4,791,166 | 7,021,359 | 11,812,524 | +11.0% |
| 2018 | 6,502,258 | 7,653,504 | 14,155,762 | +19.8% |

Total labour cost grew **+33.0% over 3 years**. Hourly cost accelerated sharply in 2018 (+35.7% YoY) vs. Salary (+9.0%), pointing to increased part-time or contract hiring.

**Headcount vs. Income:**

| Year | Headcount | Total Income | Income/Head |
|---|---|---|---|
| 2016 | 499 | 10,642,618 | ~21,328 |
| 2017 | 553 | 11,812,524 | ~21,360 |
| 2018 | 657 | 14,155,762 | ~21,546 |

Headcount grew **+31.7%** (499 → 657) while income per head stayed flat (~21,300–21,500), meaning cost growth was driven entirely by **headcount expansion**, not salary increases.

**By BU Region:** North dominates at **755 employees (44.2%)** — nearly equal to the other three regions combined. South: 477 (27.9%), East: 281 (16.4%), West: 196 (11.5%).

### 5. Year Slicer
Filter all visuals by **2016 / 2017 / 2018** to compare trends year by year.

---

## Key Insights

-  Headcount grew **+31.7%** in 3 years (499 → 657) — the primary driver of total labour cost increase
-  **IT** has the most employees (223) and the highest labour cost (4,772,538)
-  **Hourly cost surged +35.7% in 2018**, far outpacing Salary growth (+9.0%)
-  **41.1% of employees are Under 25** — the workforce is heavily skewed young
-  **North region** holds 44.2% of total headcount (755 / 1,709)
-  Attrition at **5.23%** reflects solid employee retention

---

## Repository Structure

```
hr-workforce-dashboard/
┣ assets/
┃ ┣ images/           ← Dashboard screenshots
┃ ┗ dataset/          ← datasetcv10.xlsx
┗ README.md
```

