# Restaurant Sales Analysis (Excel)

An end-to-end Excel data analysis project exploring 1,000 transaction-line records from a multi-location restaurant business, built to practice and demonstrate a full analyst workflow, from raw data to a decision-ready dashboard.

## Problem Statement

This dataset contains 1,000 restaurant transaction line items collected between January 2024 and December 2025, where each row represents an individual menu item transaction with details on location, order type, category, quantity, revenue, and customer rating. The Restaurant Owner/Executive Manager uses these insights to make strategic decisions around branch performance and resource allocation, while the Marketing Manager uses them to develop targeted promotions. This analysis answers questions around location performance, revenue drivers by menu category and item, revenue trends over time, and customer satisfaction patterns across locations and order types. The dataset does not include customer-level information or cost data, which limits deeper analysis of customer behaviour and profitability.

## What's in the Workbook

| `Summary` | Problem statement, dataset overview, data quality process, key findings, recommendations, and limitations
| `Dashboard` | KPI scorecard + 4 charts (revenue by location, by month, by category, top menu items) |
| `Analysis_WorkingData` | Live SUMIFS/COUNTIFS/AVERAGEIFS summary tables powering the dashboard |
| `Restaurant Sales-Raw_Data` | Untouched source data as a structured Excel Table, with enrichment columns (Month, Month Number, Day of Week, Day Number) |

## Tools & Techniques

- **Data validation:** verified Transaction ID uniqueness, checked `Order Total = Quantity × Unit Price` across all 1,000 rows using a `ROUND`-based comparison formula (0 mismatches found), checked for blanks and inconsistent categorical spelling
- **Data structuring:** raw data converted to a named Excel Table (`tbl_RawSales`) to keep a single, untouched source of truth; all downstream formulas reference it via structured references
- **Data enrichment:** `TEXT()`, `MONTH()`, `WEEKDAY()` used to build time-based helper columns, with numeric sort-helper columns to control chart/table ordering independent of display text
- **Analysis:** `SUMIFS`, `COUNTIFS`, `AVERAGEIFS` for all KPI and summary tables (used in place of PivotTables for the final deliverable, since they recalculate live without a manual refresh)
- **Exploration:** PivotTables used during the exploratory phase to quickly test hypotheses before committing to formula-based final tables
- **Visualization:** chart type chosen deliberately per question (horizontal bar for rankings, line for trend over time, bar instead of pie for an unbalanced category split), with axes, sort order, and scale checked for honesty, not just appearance

## Key Findings

- **Coral Gables** generated $3,093.50 in revenue from 117 transaction lines (2nd-highest volume), but carries the lowest average customer rating (3.7). Drilling into order type shows the issue is concentrated in **Dine-In specifically** (3.6 vs. a 3.9 company-wide Dine-In average), Delivery and Takeaway at that location are in line with the rest of the business.
- **Seasonality is real and sizeable:** September ($2,575.18) generates roughly **1.8x** February's revenue ($1,403.96), pooled across both years in the dataset. July is the second-weakest month.
- **The Main category drives ~66% of total revenue** ($17,125.84 of $25,799.45) — a significant concentration in one category.
- **NY Strip Steak is the top-revenue item** ($3,496.94) despite selling *fewer units* than the second-place item, BBQ Ribs (106 vs. 113), its lead is price-driven ($32.99 vs. $22.99 average unit price), not volume-driven.

## Recommendations

See the `Summary` sheet in the workbook for the full recommendations, each tied to a specific owner, action, and success metric.

## Limitations

- No customer-level data - repeat-purchase behaviour and customer segmentation cannot be analyzed.
- No cost or margin data - revenue findings (e.g., Main category's 66% share) describe revenue concentration, not profitability.
- Monthly findings are pooled across 2024–2025; within-year seasonality was not separately confirmed.

## Author

Lithemba Jan - built as a portfolio project to demonstrate practical Excel-based data analysis skills.
