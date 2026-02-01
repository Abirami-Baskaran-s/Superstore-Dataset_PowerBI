# Coffee Shop Sales — Power BI Interactive Dashboard

## Project Overview

This project presents an interactive Power BI dashboard built from a transactional dataset of over 149,000 coffee shop sales records spanning three New York City locations. The dashboard is designed as an executive-level decision-support tool, enabling stakeholders to monitor key performance indicators, investigate revenue trends through drill-down functionality, and filter operations data in real time by store and product category.

The work progresses from foundational data modelling and calculated columns through to advanced visualisation techniques, culminating in a production-ready dashboard with KPI tracking, target benchmarking, and cross-filtered interactivity.

---

## Dataset

| Attribute | Detail |
|---|---|
| Source File | `Coffee_Shop_Sales.xlsx` |
| Sheet | Transactions |
| Total Records | 149,116 |
| Date Range | January 2023 — June 2023 |
| Store Locations | Astoria, Hell's Kitchen, Lower Manhattan |
| Product Categories | Coffee, Tea, Bakery, Branded, Coffee Beans, Drinking Chocolate, Flavours, Loose Tea, Packaged Chocolate |
| Columns | transaction_id, transaction_date, transaction_time, transaction_qty, store_id, store_location, product_id, unit_price, product_category, product_type, product_detail |

---

## DAX Measures and Calculated Columns

The following calculated columns were added in Data View to support the dashboard logic.

| Column | DAX Formula |
|---|---|
| Revenue | `[transaction_qty] * [unit_price]` |
| Hour | `HOUR([transaction_time])` |
| Day of Week | `FORMAT([transaction_date], "dddd")` |
| Month Name | `FORMAT([transaction_date], "MMMM")` |

The following measures were created in Modeling View to drive the KPI cards and gauge.

| Measure | DAX Formula |
|---|---|
| Total Revenue | `SUM([Revenue])` |
| Transaction Count | `COUNTROWS(Transactions)` |
| Avg Transaction Value | `[Total Revenue] / [Transaction Count]` |
| Monthly Target | `120000` |
| Target Variance | `[Total Revenue] - [Monthly Target]` |

---

## Dashboard Components

### KPI Cards

Three summary cards sit at the top of the dashboard to give immediate visibility into operational performance without scrolling or filtering.

The **Total Revenue KPI** card displays cumulative revenue alongside the monthly target of $120,000 per store, with a trend indicator driven by the Month Name field. The **Transaction Count** card shows the total number of completed transactions, formatted in thousands for quick scanning. The **Average Transaction Value** card reports the mean spend per visit, formatted to two decimal places with a dollar prefix.

### Gauge Chart — Revenue vs Target

A gauge visual provides a proportional view of total revenue against a six-month aggregate target. The minimum is set to zero, the maximum to 800,000, and the target line sits at 720,000. Colour-coded zones indicate whether performance is below, approaching, or exceeding expectations.

### Revenue Trend — Drill-Down Line Chart

A line chart plots Total Revenue across the date hierarchy created automatically by Power BI. Users can drill from monthly view down to weekly and then daily granularity by clicking the drill-down icon. This allows anomaly investigation without leaving the dashboard. The title explicitly prompts users to interact with the visual.

### Slicers

Two slicers sit in the top-right region. The **Store Location** slicer is configured in dropdown style to conserve space. The **Product Category** slicer uses list style with a "Select All" option enabled, supporting multi-select via Ctrl+Click. Both slicers drive cross-filtering across every visual on the page.

### Revenue by Product Category — Donut Chart

A donut chart displays the revenue share of each product category. Coffee leads at 38.92%, followed by Tea at 27.78%. Clicking any segment filters the remaining visuals to isolate that category's contribution across stores and time.

### Revenue by Store Location — Bar Chart

A horizontal clustered bar chart compares total revenue across the three locations. Custom tooltips are attached to each bar, surfacing Transaction Count and Average Transaction Value on hover. This provides context beyond the headline revenue figure without cluttering the visual itself.

---

## Key Findings

Total revenue across the six-month period reached approximately 166.49K against a gauge target of 720K, reflecting the partial-period scope of the dataset. Hell's Kitchen recorded the highest store-level revenue, followed closely by Astoria and Lower Manhattan. Coffee and Tea together account for over two-thirds of all revenue. The average transaction value across all locations sits at $4.71.

---

## How to Open

1. Install Power BI Desktop from the Microsoft Store or the official Power BI website.
2. Clone or download this repository.
3. Open the `.pbix` file in Power BI Desktop.
4. If prompted, reconnect the data source to the local path of `Coffee_Shop_Sales.xlsx`.
5. Interact with the slicers, drill-down controls, and cross-filters on the dashboard page.

---

## Tools and Technologies

- **Power BI Desktop** — primary visualisation and modelling tool
- **DAX (Data Analysis Expressions)** — measure and column logic
- **Excel (.xlsx)** — source data format


---
## Contact 

Linkdln : https://www.linkedin.com/in/abiramihi/

