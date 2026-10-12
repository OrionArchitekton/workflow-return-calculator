# Workflow Return calculator

An inspectable, browser-local calculator for the labor-capacity case behind one AI workflow. Built by Dan Mercede and Codex as part of Workflow Return.

[Use the hosted calculator](https://workflow-return.orionapex.chatgpt.site/)

## Run locally

Download `calculator.html` and open it in a modern browser. No install, server, API key, account, or model call is required. This local copy has no analytics beacon and sends no input data to a server. Links to the hosted site open that site; copying a scenario creates a hosted URL whose fragment contains your numeric assumptions.

## Model

Inputs: weekly runs, current manual minutes, review minutes, exception rate, recovery minutes per exception, loaded hourly cost, setup cost, and monthly operating cost.

```text
weekly hours freed = runs × (manual − review − exception rate × recovery) / 60
annual capacity value = weekly hours freed × 52 × loaded hourly cost
first-year net capacity value = annual capacity value − setup − 12 × monthly cost
payback months = setup / (annual capacity value / 12 − monthly cost)
```

The UI accepts exception rate as a percentage. Payback is shown only when monthly net capacity value is positive. Review/recovery can exceed manual handling time, producing a negative estimate.

Default illustrative inputs produce about 11.3 hours freed per week, $32,413 annual capacity value, and $27,613 first-year net capacity value. These are invented assumptions, not a customer result.

Freed time is not automatically cash saved. This simple model cannot price downstream harm, prove output quality, or certify security/compliance. Include maintenance labor in your operating-cost assumption and validate inputs with representative pilot cases before making a decision.

## From assumptions to measured cases

- [Free pilot-readiness checklist](https://workflow-return.orionapex.chatgpt.site/checklist/)
- [Free pilot guide](https://workflow-return.orionapex.chatgpt.site/guide/)
- [Completed hypothetical case log and memo](https://workflow-return.orionapex.chatgpt.site/workbook/preview/)

**Commercial disclosure:** Workflow Return also sells a separate $29 USD, one-time Pilot Workbook through Orion Apex Capital. It logs observed cases, checks a predefined quality threshold, and exports a CSV and decision memo. The calculator in this repository is free; the paid workbook is not included. [Inspect the offer](https://workflow-return.orionapex.chatgpt.site/workbook/).

Please use GitHub issues for specific calculation errors or reproducible bugs. No customer, personal, or confidential case records.
