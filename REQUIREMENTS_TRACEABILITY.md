# Requirements Traceability Matrix — Cedarbridge

**RTM ID:** RTM-001 · **Date:** 11 November 2026 · **Reference:** Fictional portfolio project  
**Legend:** Demo = local browser behaviour, not production; Planned = backlog only; UAT NR = formal user-acceptance test not run.

| Business requirement / rule | Functional / nonfunctional requirement | Jira story | Evidence / verification | State | Gap / next action |
| --- | --- | --- | --- | --- | --- |
| BR-01 Standardise request intake | FR-01 Form submission | [US-01 SCRUM-2](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-2) | `formSubmission`, SM-02/03/04; UAT pack SCRUM-11 | Demo; UAT NR | Confirm fields and business rules, SCRUM-9 |
| BR-01 Enable reference tracking | FR-02 Local request reference | [US-01 SCRUM-2](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-2) | `nextReference`, SM-04/08 | Demo; UAT NR | Implement shared uniqueness only if backend added, SCRUM-19 |
| BR-02 Clarify responsibility | FR-03 Assign owner | [US-02 SCRUM-3](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-3) | `saveDetail`, SM-06/07 | Demo; UAT NR | Approve owner roles, SCRUM-12; server RBAC SCRUM-19 |
| BR-03 Track progress | FR-04 Request status | [US-03 SCRUM-4](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-4) | `TRANSITIONS`, SM-06 | Demo; UAT NR | Validate transition matrix SCRUM-15 |
| BR-04 Acknowledge receipt | FR-05 Notification | [US-07 SCRUM-8](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-8) | No external notification implementation | Planned | Confirm channels and message rules |
| BR-05 Operational visibility | FR-06 Dashboard | [US-06 SCRUM-7](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-7) | `renderInsights`, SM-12 | Descriptive local counts only | KPI dictionary and SLA definition SCRUM-20 |
| BRU-01 Proposed same-day priority | FR-07 Urgency classification | [US-04 SCRUM-5](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-5) | `formSubmission`, SM-03/04 | Demo of draft rule | Confirm decision policy SCRUM-9 |
| BRU-02-04 Priority approval/audit | FR-08 Manager approval | [US-05 SCRUM-6](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-6) | Not built | Planned | Specify approver controls and rejection outcomes |
| Access control | NFR-01 Authorisation | [SCRUM-19](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-19) | `currentRole` UI toggle, SM-07 | **Simulated only** | Server-enforced RBAC in future release |
| Traceability & history | NFR-02 Audit trail | [SCRUM-3](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-3) / [SCRUM-19](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-19) | `audit` array / SM-06 | Local demo only | Server audit immutability to be designed |
| Inclusive workflow | NFR-03 Accessibility | [SCRUM-21](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-21) | SM-13 responsive smoke test only | Not audited | Keyboard/AT evaluation and error association |
| Synthetic-only project | NFR-04 No real sensitive data | [SCRUM-18](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-18) | Fictional sample requests | Design intent; caution applies | Enforce usage restrictions and publishing review |

## UAT gate

`SCRUM-11` has planned intake UAT cases, but a prototype smoke check does not transform its formal execution status. Treat all formal UAT as **Not Run**, including cases requiring a real backend, until a documented environment and approved criteria are available.
