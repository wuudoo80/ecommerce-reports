# Calculation rules

Identify Order ID, the date field, Customer ID, Product ID, Product, SKU, Quantity, Unit Price USD, Discount Rate, Item Net USD, Order Status, and State. For new inputs, map equivalent fields and disclose the mapping. Use the actual currency.

- Include only Completed by default. Sum quantities rather than counting rows. Count distinct Order ID values.
- Merchandise revenue is Item Net USD. Check each line against `Quantity × Unit Price USD × (1 − Discount Rate)`, rounded to two decimal places. Decimal arithmetic can avoid binary floating-point rounding problems. Investigate discrepancies without changing source values.
- Group by Product ID and verify its name mapping. Combine colors and sizes under the same parent product.
- Unit share = a product's valid units / all valid units.
- State customer share = distinct valid customers in that state / all distinct valid customers. If order share is shown, divide by all distinct valid orders instead; do not mix denominators.
- Record the full source date range, selected reporting period, and valid-order date range if different. For zero denominators or no valid orders, explain the absence of data; do not invent leaders, create empty charts, or generate divide-by-zero formulas.
- Duplicate Order ID values may represent multiple SKUs or duplicate records. Confirm row grain and whether order-level amounts repeat across lines before aggregating. Do not silently delete rows. Confirm the business meaning of partial refunds, payment statuses, and fulfillment statuses.
- For customers appearing across states, confirm attribution. If counting a customer in multiple states is intended, explain that summed counts and shares may exceed the nationwide distinct total and 100%. Do not force them to match. Each demo customer belongs to one state.
- With missing fields, continue only authorized metrics whose definitions are clear and disclose limitations. Do not substitute orders for customers, fill historical prices with current prices, or add currencies without an agreed conversion rule.
- Revenue is not profit. Without costs, shipping charges, and delivery timing, do not infer profit or warehouse benefits.

# Reconciliation and traceability

Calculate benchmarks independently from the input. Order and unit totals must respectively agree across both reports. CEO revenue must match valid source merchandise revenue; display-rounding differences are acceptable, omitted records are not. Independently deduplicate regional customers using sets. State customer totals equal nationwide distinct customers only when each customer belongs to one state.

Record the source file, worksheet, header row, filters, and generation time. Supporting detail should include a source row number or order ID. A source SHA-256 hash can identify the input version. Check formula errors, chart ranges, actual saved outputs, and visual appearance when tools permit. Report only checks actually performed.
