# KPI dictionary | Cedarbridge (synthetic demonstration)

**Release:** portfolio package v1.4 | **As-of snapshot:** 13 November 2026, 12:00 UK | **Scope:** 160 fictional requests | **Owner:** portfolio case study

This dictionary defines a *proposed* reporting approach for a fictional service. The separate `analytics.html` page is an interactive **HTML/JavaScript prototype**, not an actual Power BI report and not production reporting. The data in `data/synthetic_service_requests.csv` is AI-generated, fictional and unrelated to the user's NHS employment or patient information.

## Core KPIs

| Metric | Definition | Calculation | Decision supported | Limitation |
|---|---|---|---|---|
| Request volume | Number of records in current filters | COUNTROWS(requests) | Capacity and service demand | Not a measure of work complexity |
| Open backlog | Records in New, In Progress, Awaiting Information | Count rows by current status | Triage pending work | Snapshot model: no dated state-transition history |
| First response within 24 hours | Share of records with a response timestamp where response minus creation is <=24 elapsed hours | COUNT(responded within 24h)/COUNT(records with response) | Identify responsiveness of answered requests | Excludes unanswered records; also show missing response count; 24 clock hours, not business hours |
| Resolution within 72 hours | Share of Resolved/Closed records where resolution minus creation <=72 elapsed hours | COUNT(completed within 72h)/COUNT(completed) | Find throughput issues in completed work | Completion-only denominator can hide old backlog |

## Diagnostic metrics and guardrails

- **Ageing open (>72h):** Open items older than 72 clock-hours as of the 13 November 2026 snapshot. Use alongside completed resolution rate, to avoid hiding unresolved cases.
- **Beyond indicative due:** Open records with `proposed_due_at` before the snapshot. The **fictional scenario rule** is 24 clock-hours after creation for High priority and 72 for Standard. This is an assumption for practising due-date reporting, **not an approved SLA**.
- **Status breakdown:** Distribution of New, In Progress, Awaiting Information, Resolved and Closed; clarifies where work accumulates.
- **Request type mix:** Counts by Facilities, IT Support, Administration, Estates, and Finance Support; avoid interpreting as staffing needs without effort weights.
- **Missing first response:** Count requests with blank first_response_at; never imply that excluding them means they met response targets.
- **Median resolution time:** Median actual elapsed hours for completed records with a resolution timestamp; more robust than mean for outliers.

## Measurement contract and quality gates

1. Grain: one row per fictional request reference. De-duplicate by reference before any reporting.
2. Timestamp convention: local UK wall-clock demonstration times, formatted `YYYY-MM-DD HH:MM`. The example omits DST offsets and holidays; it is unsuitable for contractual service-hour calculations.
3. Denominators must be displayed. If a filtered denominator is zero, display `—`, not 0%.
4. No record created after the snapshot; response/resolution timestamps must not precede creation or exceed snapshot. Indicative due dates **may be after the snapshot** for recent items.
5. Open status must not have a resolved timestamp. Resolved/Closed must have one.
6. Source and scenario classification: `SYNTHETIC / NOT REAL OPERATIONS`; do not join to clinical or employee datasets.
7. The synthetic event file `data/synthetic_request_events.csv` records illustrative event timestamps by reference (created, owner assigned, first response and status changes). For a real reporting model, use this as a separate related table rather than inventing prior states from a current snapshot.
8. Proposed targets (e.g. 90% first response within 24h or 80% resolution within 72h) are **illustrative only**, not grounded in a baseline or approved service agreement. No target is scored as achieved or missed without stakeholder agreement and baseline data.

## How to use this in a portfolio

The central achievement is the **design of a measurement framework** with transparent definitions, a reproducible test dataset and an exploratory dashboard, not improved service performance. Business requirements BO-01/BR-03/FR-06 correspond to Jira SCRUM-7 and SCRUM-20. A real reporting rollout needs an approved data model, event capture, SLA definitions, ownership and data-quality monitoring.
