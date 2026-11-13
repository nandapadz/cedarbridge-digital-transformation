# Cedarbridge / Digital Service Request Transformation

**Independent fictional portfolio project | November 2026**

This repository contains a working offline front-end prototype, an interactive synthetic analytics dashboard (with a fictional event log and indicative due dates), BA / Agile delivery case study documentation and transparent verification notes. **It is not a real client or NHS deployment.** The portfolio owner set the scope, directed iterations and performed the reported manual browser checks; tools were used to support implementation and documentation.

## Open in this order

| File | What it opens |
| --- | --- |
| **[`index.html`](index.html)** | Professional portfolio landing page (suitable as GitHub Pages home) |
| **[`app.html`](app.html)** | Working browser-local Cedarbridge request MVP v1.3 (synthetic details only) |
| **[`analytics.html`](analytics.html)** | Interactive reporting concept, 160 wholly fictional requests, no external services |
| [`Cedarbridge_Case_Study_Portfolio.pdf`](Cedarbridge_Case_Study_Portfolio.pdf) | Four-page, recruiter-ready case study PDF |
| [`CASE_STUDY.md`](CASE_STUDY.md) | Full BA / Agile project narrative |
| [`FINAL_PORTFOLIO_SUMMARY.md`](FINAL_PORTFOLIO_SUMMARY.md) | What was built, proved and not proved |
| [`KPI_DEFINITIONS.md`](KPI_DEFINITIONS.md) | Metric calculations and measurement caveats |
| [`POWER_BI_BUILD_GUIDE.md`](POWER_BI_BUILD_GUIDE.md) | Draft DAX measures for optional future practice, not a delivered Power BI report |
| [`MANUAL_QA_2026-11-13.md`](MANUAL_QA_2026-11-13.md) | User-reported Edge checks against v1.2 |
| [`V1_3_MANUAL_REVIEW.md`](V1_3_MANUAL_REVIEW.md) | Pending v1.3 manual review checklist |
| [`HOW_TO_PUBLISH.md`](HOW_TO_PUBLISH.md) | How to publish, after reviewing public scope and GitHub settings |
| [`FINAL_QA_AND_RELEASE_NOTES.md`](FINAL_QA_AND_RELEASE_NOTES.md) | Exact checks and known limitations |

## Portfolio scope and release status

The **career presentation package is complete locally**. The prototype v1.3 and dashboard have passed controlled technical checks, but manual owner sign-off of v1.3 is still outstanding; the previous v1.2 workflow was owner-reported as passed. Jira Sprint 1 remains in progress (13–27 November 2026) and formal business UAT, secure RBAC, shared persistence and a production release are **not** complete. Do not use real data.

## Storage model

The service-request prototype `app.html` keeps records only in your browser's localStorage. It is a single-user teaching demo, **not a backend**. Use Export JSON to back up synthetic records before swapping HTML files; importing restores fictional records if the browser file origin changes. The separate `analytics.html` dashboard uses its own fixed synthetic dataset under `data/`; it does not show the app's live/local records.

## Artefacts

The Jira Epic is [SCRUM-1](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-1) (may require access). Documentation includes `REQUIREMENTS_TRACEABILITY.md`, `PRIORITISED_BACKLOG.md`, `DECISION_LOG.md`, `SPRINT_1_REVIEW.md`, `UAT_EXECUTION_MATRIX.md`, `UX_ITERATION.md`, `TEST_REPORT.md` and the other dated snapshots. Automated tests using mocked browser storage are separate from user-reported manual tests; **none is formal UAT**.

## Publishing

See [`HOW_TO_PUBLISH.md`](HOW_TO_PUBLISH.md). If the GitHub Pages site is enabled, verify its live URLs before sharing them on a CV or LinkedIn. Keep personal CV and contact information out of this public repository.
