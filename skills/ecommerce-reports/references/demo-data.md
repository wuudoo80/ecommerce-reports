# Demo input

`../assets/01_mock_orders.xlsx` contains fictional orders. Prices are in USD.

- In Orders, row 1 is explanatory text, row 3 contains headers, and rows 4–203 contain demo orders.
- There are 200 unique orders. Each row is one order with one SKU; Quantity can exceed 1.
- There are 150 original customers, 7 parent products, and 28 SKUs. Each customer has a fixed State.
- The SKUs worksheet provides the SKU catalog.
- The bundled workbook is fully in English, including product names, the SKU catalog, and the Notes worksheet. Numeric values, dates, IDs, and order statuses retain the original teaching data.

These structural facts apply only to the unchanged demo asset. Reinspect new files rather than assuming 200 rows or an old month. Read `demo-expected.json` only after independent calculation for cross-checking, never as a substitute for analysis. Its product names match the original source.
