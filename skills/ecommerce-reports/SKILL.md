---
name: ecommerce-reports
description: Create or validate CEO product-sales and logistics customer-location Excel reports from ecommerce order spreadsheets or CSV files. Use for input checks, product-level sales analysis, and regional customer analysis with editable charts; not for store administration.
---

# Ecommerce Reports

Use plain English by default, including conversation, report headings, conclusions, chart labels, and output filenames. Follow the user's requested language and applicable project instructions when they specify otherwise. Explain results for people without programming experience. Complete only the requested task: inspect data, produce a CEO report, produce a logistics report, or validate reports. Do not generate every report by default.

## Inputs and outputs

- Follow the working project's AGENTS.md. Prefer the user's chosen input. If the user wants their own data but has not chosen a file, list candidates and ask them to choose; do not fall back to demo data.
- For an explicitly requested demo without another input, use `assets/01_mock_orders.xlsx`, resolving the path relative to this SKILL.md rather than the working directory. Read [references/demo-data.md](references/demo-data.md) when using this asset.
- Confirm the actual file, worksheets, header row, fields, date range, and row grain. Read [references/report-rules.md](references/report-rules.md) before calculating.
- Use spreadsheet tools or libraries actually available in the environment. Follow an available spreadsheet-specific workflow; otherwise use a suitable available library. Do not claim unavailable tools exist. Explain the specific limitation if Excel files or charts cannot be created.
- Preserve source files, skill assets, and reference answers. Write results to `reports/` in the user's working directory or their chosen destination, not the skill installation folder. Use `_v2`, `_v3`, etc. to preserve earlier files.

## Calculations and deliverables

- By default include only Completed orders, excluding Cancelled and Refunded. Sum Quantity for units sold and Item Net USD for discounted merchandise revenue, excluding tax and shipping. Count distinct Order ID values for orders.
- Group product variants by Product ID, displaying Product names. Group locations by State by default. Count distinct Customer ID values with at least one valid order.
- Explain the impact and confirm necessary definitions for duplicate order IDs, multiple lines per order, customers across states, missing key fields, or unclear statuses. Do not silently delete rows, invent values, or assume demo conventions apply.
- CEO report: sort by units descending, breaking ties by Product ID. Include product, units, order count, merchandise revenue, unit share, and totals. Identify the leaders by units and revenue separately. Include an editable product-units chart.
- Logistics report: sort by distinct valid customers descending, breaking ties by State. Include customers, customer share, orders, units, and totals, plus an editable customer-by-state chart. Distinguish customer coverage from delivery workload. Do not infer profit, shipping savings, or warehouse benefits without cost, shipping, and timing evidence.
- State the actual reporting period, definitions, source file and worksheet, conclusions, and currency (USD for the demo). Keep numbers numeric and dates sortable; show money with two decimal places and shares with one decimal place. Name files using the actual period, such as `CEO_Product_Sales_<period>.xlsx` or `Logistics_Customer_Locations_<period>.xlsx`; do not reuse an old month.
- Keep necessary supporting detail or calculations traceable to source rows or orders. Preserve source identifiers and names. If translating product labels for presentation, retain original names and a translation mapping. State that exported reports are snapshots and do not refresh automatically when inputs change.
- Independently reconcile orders, units, revenue, and distinct customers against source data. Check ranking, shares, formula errors, chart references, and saved files. When rendering is available, inspect clipping and chart appearance; otherwise disclose that visual checks were not completed.
- Before comparing two reports, identify their versions. Valid order and unit totals must agree between both reports. Only after independent calculation, and only for the unchanged demo asset, read `references/demo-expected.json` for cross-checking; never substitute its answers for calculation.

Provide openable result paths, brief findings, and checks actually performed. Configure automation, publish, or send reports only when requested.
