# Release validation: v1.2

Tested on October 29, 2026.

## Passed checks

- All published Markdown, UI metadata, reference JSON, workbook XML, worksheet names, product names, and workbook notes are English. No CJK text or full-width punctuation remains in the published package.
- The English edition retains all 200 original orders. IDs, dates, quantities, prices, discounts, statuses, and monetary values match the original input exactly. Only presentation text and product names were translated.
- Independently calculated all line amounts, parent-product totals, state totals, and distinct customer counts before consulting reference answers.
- Generated CEO and logistics Excel reports from the exported English workbook, then reopened them with a separate reader and checked all summary rows, rankings, percentages, totals, typed dates, and numeric quantities.
- Both reports contain one native editable chart with worksheet-backed series. Exported series references and colors were checked.
- Rendered and visually reviewed all three demo worksheets, both report summaries, and supporting detail. Tables and charts were populated and readable.
- Formula-error scans returned no matches. A second CEO run produced a new _v2 file while preserving the first report.
- Required skill frontmatter, resource links, package contents, and release archive integrity were checked.

## Independently reconciled results

| Metric | Result |
| --- | ---: |
| Source period | September 1-30, 2026 |
| Raw orders | 200 |
| Valid orders | 185 |
| Valid units | 316 |
| Valid customers | 141 |
| Merchandise revenue (USD) | 11,022.70 |

Classic Cotton T-Shirt leads units with 92. Hoodie leads revenue with USD 4,324.80. California has the most valid customers, 43.

## Test scope

This was a manual execution of the skill workflow with programmatic reconciliation and rendered workbook review. It does not establish automatic skill discovery or selection in a separate installed Codex session, or native Microsoft Excel UI behavior. Reports are snapshots, not automatic data-refresh pipelines. No live shop data, external publishing, messaging, or scheduling was tested.

The bundled skill-creator quick_validate.py requires PyYAML, which is absent in this runtime. It could not run. The required frontmatter fields, delimiters, name syntax, description limits, unfinished placeholders, and relative links were checked independently instead.

Temporary builders, test workbooks, rendering previews, and local dependency links are excluded from the GitHub repository and release ZIPs.
