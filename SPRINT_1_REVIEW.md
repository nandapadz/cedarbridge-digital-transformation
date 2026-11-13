# Sprint 1 | Interim review record

**Review type:** Independent portfolio-owner self-review, not a stakeholder sign-off  
**Date:** 13 November 2026  
**Sprint dates:** 13–27 November 2026 (active; not yet closed)  
**Tracked in Jira:** [SCRUM-26](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-26)

## Sprint goal

Demonstrate and verify a synthetic browser-local service-request flow covering intake (US-01), assignment (US-02) and status (US-03). Capture evidence and gaps without implying production readiness or formal UAT.

## What was demonstrated

| Story | Evidence recorded | Interim decision |
| --- | --- | --- |
| [US-01 / SCRUM-2](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-2) | Owner reports creation of CBR-2026-0001, queue display, same reference retained on Ctrl+R | Core local flow works; broader validation and UAT pending; **In Progress** |
| [US-02 / SCRUM-3](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-3) | Fictional owner Alex Morgan selected and saved; log shows Owner changed; Viewer UI blocks editing | Local flow demonstrated, actual RBAC not present; **In Progress** |
| [US-03 / SCRUM-4](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-4) | Original status behaviour confused/failed in owner test; v1.2 Start work shows In Progress, persists after Ctrl+R, logs Status changed | Alternate local path validated; initial dropdown issue unknown; **In Progress** |

**QA-02 / [SCRUM-24](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-24): Done** for its narrowly scoped manual prototype checks, per owner-reported results.  
**BUG-01 / [SCRUM-25](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-25): In Review** pending regression/root-cause triage.  
**UX-02 / [SCRUM-27](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-27): Prepared locally** as v1.3 purple UI; owner feedback and manual Edge recheck pending.

## What is still open

- Confirm/approve scenario business rules, fields, validation and transition matrix (**SCRUM-9**, **SCRUM-15/16**).
- Execute formal UAT with recorded evidence and agreed acceptance criteria (**SCRUM-11**, **SCRUM-14**, **SCRUM-17**). Existing browser checks do **not** constitute formal UAT.
- Security requirements such as real identity, trusted server-side access control, immutable audit trails and shared persistence (**SCRUM-19**) are absent by design.
- Agree KPI/SLA definitions (**SCRUM-20**), accessibility review (**SCRUM-21**) and data lifecycle rules (**SCRUM-22**).
- Confirm v1.3 design/interaction with the owner and keep synthetic data only.

## Learnings / retrospective seed

**Went well:** The synthetic intake/assignment/status workflow could be demonstrated; owner ran real-browser tests and identified a status issue early; a revised path improved the experience.

**Needs improvement:** The original dropdown path produced an unresolved failure report; the first labels and UI styling were less clear/distinctive than desired. The owner described the workflow as easy to use and specifically requested a less generic purple design.

**Improvement chosen:** v1.3 visual cleanup and a more explicit **Create request** navigation label. Do not infer wider user satisfaction from this single owner's feedback.

**Review outcome:** Local MVP demonstration achieved for tested paths. This is **not** completion/closure of Sprint 1, real business acceptance, stakeholder approval or a deployable product.
