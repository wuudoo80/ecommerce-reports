# Ecommerce Reports

A Codex skill for turning ecommerce order spreadsheets or CSV files into CEO product-sales and logistics customer-location Excel reports. Designed for people without programming experience. It also supports inspecting inputs and validating existing reports.

**English is the default** for conversation, report headings, summaries, chart labels, and output filenames. Ask for another language to override the default. Applicable project instructions are respected.

Includes fictional teaching data and supports your own order files. This is an independent project, not an official OpenAI product. Accounts, subscriptions, and usage credits are not included. Your environment needs tools or libraries that can read and write Excel workbooks; no particular paid plugin is required.

## Install locally

Download and fully extract the repository ZIP or release archive. Copy the entire `skills/ecommerce-reports` folder into your personal skills directory:

- macOS / Linux: `~/.agents/skills/ecommerce-reports/`
- Windows: `%USERPROFILE%\.agents\skills\ecommerce-reports\`

For project-only installation, place it at `.agents/skills/ecommerce-reports/` inside that project instead. Choose one scope to avoid duplicate installations. The skill directory must directly contain `SKILL.md`; do not add an extra repository-folder layer. Back up an existing installation before updating it. If the skill does not appear, restart Codex.

See the [official skill documentation](https://learn.chatgpt.com/docs/build-skills) for local discovery locations. Other hosts supporting this skill format may use different installation procedures.

## Try it

Open an empty working folder in Codex and start a new chat. Send these prompts separately:

```text
Use $ecommerce-reports to inspect the bundled demo data. Tell me the source file, worksheets, header row, date range, and row grain. Do not create reports or read the reference answers yet.
```

```text
Use $ecommerce-reports to create a CEO product-sales Excel report from the inspected demo data. Save it in this working folder's reports directory, with an editable chart and traceable supporting detail.
```

```text
Use $ecommerce-reports to create a logistics customer-location Excel report from the same demo data. Then independently validate both reports against the source before consulting the demo answers.
```

To use your own files:

```text
Use $ecommerce-reports with my data. First list candidate files in this project's data folder, let me choose one, and confirm the field mapping and business definitions before generating reports.
```

To use another language:

```text
Use $ecommerce-reports to create the CEO report in my preferred language.
```

All bundled materials are in English, including the demo workbook, product names, worksheet notes, and reference answers. The English edition preserves the source order IDs, dates, quantities, prices, discounts, statuses, and amounts.

## Report definitions

By default, only Completed orders count; Cancelled and Refunded orders are excluded. Units come from Quantity, customers are distinct Customer ID values, and merchandise revenue excludes tax and shipping. Revenue is not profit. New inputs require confirmation where statuses, refunds, multiple order lines, or cross-state customers affect definitions.

Reports are calculation snapshots and do not refresh automatically when inputs change. Repeated runs preserve older files using `_v2`, `_v3`, and so on.

## Package contents

- `skills/ecommerce-reports/SKILL.md`: reusable workflow and language defaults.
- `skills/ecommerce-reports/agents/openai.yaml`: UI metadata.
- `skills/ecommerce-reports/references/`: calculation rules, demo structure, and post-calculation checks.
- `skills/ecommerce-reports/assets/01_mock_orders.xlsx`: fictional demo orders.

Historical reports, local configuration, and personal paths are excluded.

## Publish on GitHub

Upload this README, `.gitignore`, and the entire `skills/` directory, preserving the layout. GitHub's source ZIP then contains the complete skill. You can also attach the standalone skill ZIP to a Release. Local packaging does not create a remote repository or publish anything automatically.

The copyright owner has authorized including the demo data in this package. No open-source license has been selected. Public availability does not grant unrestricted redistribution or commercial rights; the owner can add a LICENSE reflecting their intended permissions before publication.

## Release validation

See [TEST_RESULTS.md](TEST_RESULTS.md) for the checks performed on this release and their scope.
