# Power BI Executive Storytelling (IEP) — Superstore Profitability Deep-Dive (2017)

## Overview
This repository contains a **Power BI dashboard** and an **executive-ready storytelling deck (max 10 slides)** created as part of the IEP “Storytelling del Dato” module.

The objective is to move from raw transactional data to **actionable insights** by:
- defining a clear KPI layer,
- exploring patterns and drivers,
- and communicating findings in a concise, decision-oriented narrative.

> Focus: **2017 (last full year)**, with **2014–2017** used as historical context.

## Dataset
- Source: Kaggle — Superstore Dataset (Final): https://www.kaggle.com/datasets/vivek468/superstore-dataset-final  
- Granularity: **order line level** (product, customer, dates, geography, shipping).
- Key fields:
  - Time: `Order Date`, `Ship Date`, derived `Order Month Start`, `Order Year`
  - Product: `Category`, `Sub-Category`, `Product Name`
  - Geography: `Region`, `State`, `City`
  - Commercial/Operations: `Discount`, `Ship Mode`
  - Metrics: `Sales`, `Profit`, `Quantity`

> Monetary amounts: currency not specified in the dataset (assumed **USD** by context).

## What I built

### 1) Data ingestion & preparation (Power Query)
- Imported the dataset into Power BI and applied basic transformations:
  - data type fixes (dates, numeric fields with decimal separator),
  - trimming text fields,
  - handling duplicated records where applicable,
  - derived date fields (Month/Year) to support time-series analysis.

### 2) KPI layer (DAX)
Base measures:
- **Sales**, **Profit**, **Orders**, **Customers**, **Quantity**

Derived measures (examples):
- **Profit Margin %**
- **Average Order Value (Ticket Medio)**
- **Profit per Order**
- **Weighted Discount (by Sales)**

### 3) Dashboard & storytelling outputs
- Power BI report pages for exploration and insight validation
- A concise **executive deck** summarizing the analysis and recommendations

## Key insights (final)
### Insight 1 — November margin decoupling (2016–2017)
Sales and profit generally follow a similar pattern over 2014–2017, **except in November 2016–2017**, where profit underperforms versus sales, reducing margin.

### Insight 1 (driver) — Machines drives November losses
In both **Nov-2016** and **Nov-2017**, **Machines** is the sub-category with the strongest negative contribution to profit, coinciding with **high weighted discounts (~40%+)**.

### Insight 1 (root cause example) — Losses concentrated in few products (Machines, Nov-2017)
Machines losses in Nov-2017 are explained by **very few products**, with a clear pattern:
- loss-making items use **very high discounts (50–70%)**,
- profitable items sit around **0–20%** discounts.
A similar pattern appears in Nov-2016.

### Insight 2 — 2017 focus: Tables is the main annual loss contributor
In 2017, **Tables** is the sub-category with the largest negative contribution to profit, despite relevant sales volume (profitability issue, not only volume).

### Insight 2 (driver) — Losses concentrated geographically (Tables, 2017)
~**75%** of the annual Tables loss is concentrated in **4 states**, which also show a **high weighted discount**. Prioritizing actions in these states maximizes impact.

### Insight 3 — Shipping type: Same Day = high discount, low margin (2017)
In 2017, **Same Day** combines:
- the **lowest profit margin** and **lowest profit per order**,
- with the **highest weighted discount (20.43%)**.
By category, margin is ~**1%** in **Technology** and **Furniture**, while **Office Supplies** remains strong — suggesting category-specific commercial guardrails for Same Day.

## Recommendations (executive)
- **November / Machines:** set discount limits so margin does not turn negative during November campaign periods.
- **Tables (2017):** prioritize actions in the top loss states (review commercial conditions/discounts) before broad measures.
- **Same Day (2017):** define **minimum margin thresholds by category** and adjust discounts/conditions when thresholds are not met.

## Repository structure
- `/images/` — Power BI dashboard screenshots used in the deck
- `/docs/` — `slides.pdf` (executive presentation) and optional notes
- `report.pbix` — Power BI report file (deliverable)
- `/images/tableau/` — selected Tableau replicas

## How to run
1. Download the dataset from Kaggle (link above).
2. Open `report.pbix` with Power BI Desktop.
3. If Power BI asks for the data source path, point it to the downloaded CSV file.
4. Click **Refresh** and navigate the report pages.
   
## Tools & skills
- **Power BI**
- **Power Query**
- **DAX**
- KPI design & executive storytelling
- **Tableau Public** (selected visual replicas)

## Author
**Jorge David Aranda Arroyo**

