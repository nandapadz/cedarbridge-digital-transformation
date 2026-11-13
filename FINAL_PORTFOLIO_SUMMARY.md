# Cedarbridge | Final portfolio release summary

**Independent BA & digital delivery portfolio project (fictional)**  
**Prepared by:** Fernanda Moreno Padula | **Bundle release:** 13 November 2026  
**Project tracking:** [Jira SCRUM-1](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-1)  
**Status:** Finished *portfolio presentation package*; active learning and review backlog. Not a completed client engagement or production deployment.

## Elevator pitch

Cedarbridge is a self-directed fictional service-transformation case study. I translated an imagined email/spreadsheet request workflow into business requirements, a traceable Jira backlog and a functional browser-based MVP. I tested the flow in iterations, documented a status-change problem and its verified workaround, then introduced an understated purple UX refresh and an interactive reporting demonstration backed by a reproducible synthetic dataset.

## Delivered items

1. **Business analysis:** fictional problem statement, As-Is/To-Be framing, BR/FR/NFR, user stories, proposed acceptance criteria, traceability, prioritisation and documented decisions.
2. **Agile/PMO:** Jira Epic, Sprint 1 plan, tasks, manual QA record (SCRUM-24), defect lifecycle (SCRUM-25), interim review (SCRUM-26) and UX improvement (SCRUM-27).
3. **Functional software:** offline HTML/CSS/JS service request app `app.html`; intake validation, local unique references, owner assignment, status transitions, local history, search, Viewer UI mode and CSV/JSON export.
4. **Analytics concept:** `analytics.html` with filters and dynamic KPIs; 160 simulated requests in `data/synthetic_service_requests.csv` and JSON; transparent denominator and timestamp caveats in `KPI_DEFINITIONS.md`.
5. **Career assets:** portfolio landing `index.html`, polished PDF case study, ready-to-use CV bullets and LinkedIn text (separate personal files are not part of this public-safe repository).

## Evidence scale

- Manual native-browser checks in v1.2 were **reported PASS by the portfolio owner**: intake/refresh, owner/history, In Progress after Ctrl+R using Start work, Viewer UI restriction and CSV export (SCRUM-24 Done). This is not an independent lab or formal UAT.
- v1.3 purple build passed automated **technical smoke/regression tests with injected mock localStorage**. The newer build has **not** been manually accepted by the owner in their Edge, so original modal status root cause remains unproven (SCRUM-25 In Review).
- The interactive analytics page was technically checked for script errors, filter/reset operation, counts against the source dataset and desktop/mobile overflow; its numbers are entirely fabricated example data.

## No exaggerated outcomes

Cedarbridge is a **portfolio simulation**, not a commissioned client project or NHS implementation. There are no real beneficiaries, service-level gains, savings, deployment, formal stakeholder interviews, clinical use or production acceptance. Viewer mode is not server RBAC; browser localStorage is not a secure database or cross-user service; draft UAT test packs have not been executed as formal UAT. AI assisted with code, artefacts and drafting; the portfolio owner set direction and provided manual test results.

## Public navigation

`index.html` → project overview; `app.html` → functional synthetic prototype; `analytics.html` → synthetic analytics; `CASE_STUDY.md` / portfolio PDF → full narrative; `KPI_DEFINITIONS.md` → exact metric rules; `SPRINT_1_REVIEW.md` and `MANUAL_QA_2026-11-13.md` → scoped evidence.
