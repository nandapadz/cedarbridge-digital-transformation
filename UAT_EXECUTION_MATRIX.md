# Draft UAT execution matrix | Not executed

**Status:** Draft, not business-approved, not formally executed.  
**Traceability:** [SCRUM-11 Intake](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-11) · [SCRUM-14 Ownership](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-14) · [SCRUM-17 Status](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-17).

The following is a **planning matrix** for future acceptance tests. In particular, a successful manual test in a browser-only demo is not proof of authorised access control, production persistence or stakeholder sign-off.

| Case | Story / criterion | Proposed test | Expected result | Feasible in current demo? | Formal UAT status |
| --- | --- | --- | --- | --- | --- |
| UAT-01 | US-01 AC-01 | Submit complete synthetic request | Single request and locally unique reference | Yes, narrow client behaviour | Not Run |
| UAT-02 | US-01 AC-02 | Omit mandatory description | Accessible field-specific feedback; no request created | Partly; accessibility to be reviewed | Not Run |
| UAT-03 | US-01 AC-03 | Inspect confirmation | Correct reference visible | Yes, narrow client behaviour | Not Run |
| UAT-04 | US-02 AC-01 | Coordinator assigns eligible owner | Owner persists; queue shows updated owner | Demo eligibility only | Not Run |
| UAT-05 | US-02 AC-02 | Unauthorised user attempts update via UI and API | Both rejected; data untouched | **No**, requires backend/authentication | Not Run |
| UAT-06 | US-02 AC-03 | Assign/reassign owner | Previous/new owner, actor and time durably logged | Local event only; **no** trusted actor | Not Run |
| UAT-07 | US-03 AC-01 | Open record details | Correct owner and status displayed | Yes | Not Run |
| UAT-08 | US-03 AC-02 | New → In Progress, refresh, inspect history | Valid transition is retained | v1.2 direct Start work demonstrated; original dropdown triage open | Not Run |
| UAT-09 | US-03 AC-03 | Attempt invalid state transition | Rejected with feedback; value remains | Partly via UI; no server policy | Not Run |
| UAT-10 | NFR-01 | Change role client-side, attempt direct mutation | Server enforces actor permissions | **No**, needs secure backend | Not Run |
| UAT-11 | NFR-02 | Reopen in a second authenticated account | Trusted event history and actor identity persist | **No**, needs backend | Not Run |
| UAT-12 | NFR-03 | Keyboard, contrast, screen reader, errors | Accessible navigation and feedback per agreed standard | Requires manual accessibility review | Not Run |

## Proposed entry criteria

1. Agree fictional scenario rules and acceptance criteria and record approver assumptions explicitly.
2. Specify the test build, environment and synthetic dataset; separate browser demo from server tests.
3. Assign a real, identifiable reviewer if practising a sign-off workflow; never invent a stakeholder or signature.
4. Capture actual result, evidence, date, environment, defect and disposition per case.
5. Define what constitutes UAT acceptance vs demonstration-only verification.

## Decisions / known blockers

- **SCRUM-25:** Original dropdown status-update report needs regression/triage despite v1.2 workaround.
- **SCRUM-19:** Secure persistence/authentication/RBAC not implemented.
- **SCRUM-21:** Formal accessibility assessment pending.
- This matrix is **not** evidence that any of these UAT cases passed. Earlier BV-01–BV-06 checks are documented separately in `MANUAL_QA_2026-11-13.md`.
