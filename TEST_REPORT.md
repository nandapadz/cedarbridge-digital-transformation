# Cedarbridge MVP — Browser Smoke Test Report

**Date:** 10 November 2026  
**Application:** Service Request Workspace v1.0  
**Environment:** Headless Chromium, Playwright (Python), HTML injected into a controlled test page because local file and localhost navigation were restricted. localStorage behaviour was simulated using an in-memory implementation.  
**Dataset:** Synthetic inputs only.

| ID | Test | Result | Notes |
| --- | --- | --- | --- |
| SM-01 | Empty initial queue displays | PASS | Count = 0 |
| SM-02 | Required fields block invalid submit | PASS | Correct error shown |
| SM-03 | Urgency explanation required when same-day impact Yes | PASS | Conditional validation |
| SM-04 | Valid request creates High Priority local record | PASS | Reference CBR-2026-0001 on test dataset |
| SM-05 | State survives app reinitialisation | PASS (mock) | **Simulated** storage only; browser restart not tested |
| SM-06 | Owner and status change records an audit trail | PASS | Local update saved |
| SM-07 | Read-only role disables edit controls | PASS | UI only, not secure RBAC |
| SM-08 | Second request gets a distinct reference | PASS | Within single local dataset only |
| SM-09 | Priority filter and text search | PASS | Matching row count |
| SM-10 | JSON export browser download | PASS | Filename verified |
| SM-11 | CSV export browser download | PASS | Filename verified |
| SM-12 | Local descriptive insights render | PASS | Five status rows |
| SM-13 | Mobile 390px layout prevents page-level overflow | PASS | Table scrolls within its container |

## Not tested

Production or real browser file-origin persistence across browser restarts; database uniqueness under concurrency; true login/role-based access control; backend save failures/retries; multi-user permissions; real Power BI/Jira integration; SLA accuracy; end-user acceptance or sign-off. These remain explicitly outside the MVP scope.

**Conclusion:** 13 automated local browser smoke checks passed under the stated test setup. This is evidence for a functional demonstration, **not formal UAT or release approval**.
