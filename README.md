# Task-9-KPI-Tacking-Sheet
# Simple KPI Tracking Sheet (Excel)

A one-page KPI summary that updates automatically from raw order data. Built in Excel as part of my Data Analytics practice track (Task 10).

## Objective
Translate raw transactional data into a small set of business-ready KPIs that recalculate as new rows are added.

## Dataset
Sample Superstore dataset: 9,994 order records with order ID, dates, region, category, product, sales and quantity.

## KPIs Tracked
| KPI | Value |
|---|---|
| Total Revenue | $2,297,200.86 |
| Units Sold | 37,873 |
| Total Orders | 5,015 |
| Average Order Value | $458.07 |
| Top Product | Canon imageCLASS 2200 Advanced Copier |

Also included: revenue, units and % share by Category, with a column chart.

## How It Works
The workbook has two tabs:
- **Orders**: raw data, plus one helper column (`Product Sales Total`) used to find the top product
- **KPI Summary**: the one-page dashboard, driven only by formulas

| KPI | Formula approach |
|---|---|
| Total Revenue / Units Sold | `SUM` |
| Total Orders (unique) | `SUMPRODUCT` with `COUNTIF` |
| Average Order Value | Revenue / Total Orders |
| Top Product | `INDEX` + `MATCH` + `MAX` on the helper column |
| Category breakdown | `SUMIFS` |

Formulas cover rows up to 12,000 on the Orders tab, so new orders added below the data are picked up automatically.

## Key Learnings
- Choosing few, meaningful KPIs is better than showing everything
- Average Order Value must use unique orders, not rows, because one order can have many product lines
- `SUMIFS` over full columns keeps the sheet accurate as data grows
- Cross-checked results with Python (pandas) to confirm the numbers

## Tools
Excel (works in Google Sheets too), Python (pandas) for validation

## Files
- `KPI_Tracking_Sheet.xlsx`: the workbook
- `screenshot.png`: preview of the KPI Summary tab

## Author
Sandhya Namburi
