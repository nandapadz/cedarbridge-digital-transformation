# Interview Preparation — Cedarbridge Business Analysis Case Study

**Purpose:** Answer interview questions accurately about what was practised, built and not built. Present this as an *independent fictional training case study*, not a professional customer implementation.

## Short introduction (30–45 seconds)

> I built an independent fictional service-operations improvement case study to deepen my digital BA skills. I used a hypothetical inbox-and-spreadsheet process to practise requirements definition, user stories and acceptance criteria in Jira, and supported those with a browser-local demonstration. I then reviewed the solution against the intended requirements, identified the gaps, and created a prioritised improvement backlog. All data are synthetic and the work is a portfolio simulation.

## Evidence to show

| Competency | Evidence | Important limitation |
| --- | --- | --- |
| Requirements analysis | `REQUIREMENTS_TRACEABILITY.md`, Jira SCRUM-2 to SCRUM-8 | Stakeholder decisions are hypothetical and not signed-off |
| Agile and prioritisation | `PRIORITISED_BACKLOG.md`, Sprint 1 stories and provisional estimates | No actual development team's velocity or sprint acceptance |
| Process improvement | `BA_REVIEW.md`, `DECISION_LOG.md` | Business problem is fictional |
| Quality & testing | `TEST_REPORT.md`, Jira SCRUM-11 | 13 smoke checks documented under a simulated storage harness; not formal UAT |
| Technical awareness | `index.html`, security gap SCRUM-19 | No backend, secure auth or multi-user deployment |
| KPI analysis | KPI task SCRUM-20 | No validated SLA clock or realised operational benefit |

## Practice questions

**What was the most important requirement?**  
Reliable standardised intake (BR-01 / FR-01), because downstream allocation and reporting depend on consistent request records. But the proposed exact validation rules still need business approval.

**What would you change before production?**  
Agree the underlying business rules and data classification, then introduce a secure backend with server-enforced permissions, persistent IDs and audit trail, accessibility verification, and documented information governance. I'd run formal UAT with suitable business participants before approval.

**How did you handle change requests?**  
I documented draft rules separately from confirmed scope, traced them to stories/tests, and would assess impacts on priority, dependencies, acceptance criteria and reporting before taking any proposed change through the appropriate approval.

**Did this deliver financial savings?**  
No; no real organisation used this prototype. It is a training exercise demonstrating the BA process and evidence of technical exploration. Avoid claiming ROI, savings or operational improvement.

**Did you code the app yourself?**  
This was an AI-assisted build. I focused on the requirements, traceability, prioritisation, review and acceptance logic, and used the generated prototype to learn how a digital workflow could operate. I can explain the design, limitations and planned refinements.

## Next learning steps

1. Walk through each linked Jira issue until you can explain the need, acceptance criteria and dependency without notes.
2. Revise one requirement and show the linked impact on UI, test case and Jira backlog.
3. Build the synthetic Power BI dashboard only after agreeing an exact KPI dictionary.
4. Perform a new reproducible test run and document actual evidence separately from the original smoke report.
5. Publish to a public GitHub repository only after a final safety and quality check and your explicit decision about visibility.
