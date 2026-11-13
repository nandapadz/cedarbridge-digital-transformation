# Prioritised Improvement Backlog — Post-MVP BA Review

**Date:** 11 November 2026 · **Framework:** MoSCoW relative to a future shared deployment. Jira Priority uses available High/Medium; do not treat it as user-approved sprint commitment.

| Order | Jira work | MoSCoW | Jira priority | Reason | Dependency / acceptance evidence |
| --- | --- | --- | --- | --- | --- |
| 1 | [SCRUM-9](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-9) Confirm intake/urgency rules (existing) | Must | Existing | Rule ambiguity and incomplete assumptions | Owner-approved field/urgency decisions and revised criteria |
| 2 | [SCRUM-15](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-15) Approve status matrix (existing) | Must | Existing | Progression/closure rules need business decision | Role × state × transition matrix and negative tests |
| 3 | [SCRUM-19](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-19) Secure persistence and permissions | Must before real deployment | High | No server/RBAC; confidential data must not be collected | Architecture, access matrix, server-side tests |
| 4 | [SCRUM-21](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-21) Accessible feedback | Should | Medium | Error association and manual accessibility tests | Evidence of keyboard/AT checks and fixes |
| 5 | [SCRUM-20](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-20) SLA and KPI definitions | Should | Medium | Dashboard cannot claim overdue/SLA | Reviewed KPI dictionary and synthetic calculations |
| 6 | [SCRUM-22](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-22) Retention / recovery | Should | Medium | Browser storage/export limitations | Data lifecycle and recovery design |
| 7 | [SCRUM-23](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-23) GitHub case study and evidence | Should | Medium | Portfolio value depends on transparency and accessibility | Review/approve repo before publishing |
| Later | [SCRUM-8](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-8) Acknowledgement notifications | Could | Low | Not core MVP; delivery channel TBD | Message, privacy and failure handling specified |

## Sprint planning note

Sprint 1 in Jira already contains the three foundational user stories. Its story-point estimates were preliminary and are **not evidence of a real team's velocity**. This review **does not start a sprint or mark work Done**. A sensible next learning task is to refine SCRUM-9 and SCRUM-15 with simulated decision owners, then review design changes before implementation.
