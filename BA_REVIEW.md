# Business Analyst Desk Review — Cedarbridge MVP v1.0

**Review ID:** BAR-001 · **Date:** 11 November 2026 · **Authoring context:** Independent portfolio simulation  
**Review approach:** Source-code inspection of `index.html` + original smoke-test record `TEST_REPORT.md` + existing Jira stories.  
**Not performed:** Stakeholder workshop, browser accessibility audit, security penetration test, real multi-user test, production readiness assessment, formal UAT.

## Executive assessment

The prototype demonstrates the core *concept* of a more structured service-request pathway. Intake, ownership, simple tracking, local activity history and descriptive reporting are implemented as client-side interactions. These demonstrate a valid portfolio learning pathway, but **must not be confused with a deployable healthcare or enterprise product**. Secure access, durable shared records, validated service-level definitions and sign-off remain absent.

**Recommended disposition:** Continue as a **synthetic-data portfolio MVP**; do not approve operational use. Validate business rules and scope before changing the workflow.

## Current state versus intended state

| Area | Expected outcome | Evidence available in v1.0 | BA assessment / gap | Follow-up |
| --- | --- | --- | --- | --- |
| Intake & data quality | Standard request details, clear errors | `formSubmission`, `fieldError`, `toggleUrgency`; smoke checks SM-02/03/04 | Demonstrated locally. Field categories, date applicability and length limits remain unapproved | SCRUM-9 |
| Reference | Unique ID after successful save | `nextReference`; SM-04/08 | Unique in one local browser dataset, not across devices/users | SCRUM-19 |
| Ownership | Visible owner and change history | `saveDetail`; SM-06 | Demonstrated locally; role toggle is not security | SCRUM-12 / SCRUM-19 |
| Status tracking | Valid transitions and closure | `TRANSITIONS`, `safeStatusTransitions`; SM-06 | Proposed transition rules not business-approved; conditions for ownership/closure not specified | SCRUM-15 |
| Urgency | High priority when same-day impact is confirmed | `formSubmission`, `seed`; SM-03/04 | Currently accepts user-declared Yes; authorisation and exceptions pending | SCRUM-9 / SCRUM-5 / SCRUM-6 |
| Reporting | Operational visibility, validated KPIs and overdue work | `renderInsights`, `updateStats`; SM-12 | Only local counts. No due timestamps, SLA/overdue calculation, business-day calendar or approved KPI dictionary | SCRUM-20 |
| Accessibility | Consistent keyboard and assistive-technology use | Labels, `aria-invalid` for many fields, dialog and browser responsive smoke check SM-13 | Error association and radiogroup semantics need specific review. Formal accessibility conformance not tested | SCRUM-21 |
| Data lifecycle | Appropriate retention, export and recovery | `load`, `persist`, `exportCSV`, `exportJSON`, `clearLocalData` | LocalStorage data can be lost and has no retention or controlled export policy. CSV formula-prefix guard is present; this is not a privacy certification | SCRUM-22 |
| Security | Server-enforced identity, least privilege and audit controls | Local `currentRole` UI switch, `state`, `audit` | Not implemented by design. Do not use with personal or operational data | SCRUM-19 |
| Portfolio | Transparent evidence and reproducibility | `index.html`, Jira issues, smoke report | Local demo available; GitHub publication not yet approved or executed | SCRUM-23 |

## Quality and control observations

1. **Draft rules vs confirmed requirements:** The code currently imposes a service date and 10–120 character summary and 20–2,000 character description. These values are scenario assumptions, not signed-off stakeholder requirements.
2. **Priority governance gap:** Same-day impact automatically marks requests High. The prior story for managerial approval of priority changes is *not* implemented. Classify it as a planned requirement rather than a defect against the MVP's limited scope.
3. **Access-control distinction:** Viewer and coordinator role choices are freely selectable in the browser. They demonstrate UI states but are **not** proof of RBAC or secure auditability.
4. **SLA/benefits limitation:** Present counts as descriptive outputs only; do not call them service-level performance or measurable savings without definitions, baseline and observed measurements.
5. **Testing evidence boundaries:** Original report claims 13 browser smoke checks under a simulated localStorage test harness. This review does **not independently re-run those tests**, and formal UAT remains Not Run.
6. **Accessibility improvement:** Several form errors have visible spans and `aria-invalid` attributes, but error IDs are not explicitly associated to their fields using `aria-describedby` in the inspected HTML. The same-day impact group has no standalone element ID for `fieldError('impact', ...)`; test for assistive technology feedback.
7. **Synthetic-only safety:** All demonstration examples must remain fictional. `localStorage` and exports are not protected storage for confidential records.

## Prioritisation principles

- **Must Have before any real deployment:** Approved rules, durable secure persistence, server-side RBAC, audit controls and information governance assessment.
- **Should Have for next portfolio iteration:** Clear validation/accessibility, data dictionary decisions, KPI definitions, synthetic Power BI dataset, and structured test evidence.
- **Could Have later:** Notifications, automated reminders, live integrations, richer dashboards.

## Evidence classification

| Category | Evidence threshold | Status |
| --- | --- | --- |
| Proposed BA requirement | Documented assumption and acceptance criteria | Available, approval pending |
| Functioning demonstration | Code and existing smoke-check report | Available at browser-local scope |
| Real production capability | Hosted authenticated integration with verified operations | **Not available** |
| Formal UAT passed | Executed approved tests with business user sign-off | **Not available** |
| Measurable business benefit | Baseline, actual measurements, methodology | **Not available** |

**Recommended BA sign-off for this desk review:** Findings recorded and triaged for the *portfolio demonstration*; no acceptance or release authority claimed.
