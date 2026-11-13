# Case Study | From an inbox problem to a service-request prototype

**Cedarbridge Community Services** · Independent fictional project · Business Analysis / Agile delivery / Digital Transformation  
**Status:** portfolio exercise, not deployed · **Current UI:** v1.3, pending owner review · **Evidence recorded:** 13 Nov 2026

## The imagined problem

In the Cedarbridge scenario, staff receive service requests through shared email and spreadsheets. The intended operational risks are familiar: incomplete requests, unclear owners and limited visibility into what is outstanding. These are **hypotheses created for a learning brief**, not measured findings from actual stakeholder interviews.

## The job to be done

Design a straightforward way for someone to raise a request and for a coordinator to take responsibility and track it through a simple workflow. The goal was to link a business problem to requirements, decisions, backlog items, tangible software behaviour and reviewable testing evidence.

## How I approached it

1. **Discovery framing.** Defined the fictional process pain, the boundaries of the MVP, user roles, assumptions and intended outcomes. Sketched As-Is and To-Be processes, with unanswered policy questions left visible.
2. **Requirements and traceability.** Translated the scenario into business outcomes, BR/FR/NFR requirements, user stories and proposed acceptance criteria. Core stories map to **US-01 / SCRUM-2 (intake), US-02 / SCRUM-3 (ownership) and US-03 / SCRUM-4 (status)**.
3. **Delivery planning.** Created a Jira epic and prioritised backlog; organised a two-week Sprint 1 (13–27 November), with 15 **provisional** story points and a goal limited to demonstrating a synthetic browser-local workflow.
4. **Prototype and iteration.** Used AI-assisted HTML/CSS/JavaScript to build a standalone request workspace with local reference generation, validation, owner selection, proposed status transitions, activity history, filtering and export. The later design uses an understated purple-and-lilac interface.
5. **Testing and a defect.** The owner created synthetic record **CBR-2026-0001** and confirmed it remained after refresh. Owner assignment worked, but status remained New in an earlier interaction. **SCRUM-25** recorded that concern. A direct **Start work** action in v1.2 was then confirmed in the user's browser: status displayed In Progress, remained after Ctrl+R, and logged the change.
6. **Review and honest scope.** Recorded user-reported results on **SCRUM-24** (Done) and an interim review on **SCRUM-26** (In Progress). Kept SCRUM-25 In Review because the original dropdown issue has no proven root cause. The purple v1.3 build is **technically checked**, not yet user-accepted.

## Functional and delivery evidence

| Question | Evidence | Boundary |
| --- | --- | --- |
| Can someone create a request and see a reference? | Native-browser user report, CBR-2026-0001 | Unique within one local browser dataset, not across users |
| Does owner assignment work? | Owner Alex Morgan and change event in screenshot | Fictional team only, not genuine account access |
| Can a request start work? | v1.2 user-reported status, refresh persistence, status activity | Alternate queue action validated; original dropdown root cause unknown |
| Does the Viewer role prevent edits? | User-reported UI restriction PASS | Not authentication, server RBAC or API-denial testing |
| Can users export records? | User-reported CSV export PASS | Local synthetic data only; no governed export policy |
| Is v1.3 ready to share? | Controlled browser test with simulated storage, visual screenshots | Owner visual review and manual Edge retest pending |

## What this exercise taught me

- A visually complete prototype is not the same as a production-ready service. Browser role switches and local activity entries cannot replace security controls or an immutable audit log.
- Acceptance criteria must cover negative and permission paths, not only the happy path. Formal UAT is **not complete**.
- A reported defect should be documented before declaring success; a workaround can pass while the original path remains under investigation.
- Small feedback loops matter: after the owner described the system as easy to use, the next request was to remove the generic 'AI-template' look and establish a more restrained visual language. That became the v1.3 UX iteration.

## Next decisions

Review v1.3 in native Edge with existing synthetic data; resolve/triage the original dropdown experience; confirm the fictional policy for required fields, valid transitions and closure; design secure persistence/RBAC only if a real shared prototype is in scope; define valid SLA and service metrics before claiming operational performance.

## How to describe this accurately in an interview

> “I built an independent, fictional BA and Agile case study around a service-request process. I mapped the problem into requirements and user stories, organised the work in Jira, and developed an AI-assisted browser prototype. I ran hands-on tests, documented a status-update issue, validated a workaround, and used feedback to refine the user experience. It isn't a live organisation rollout; the value is in the requirements traceability, testing discipline and delivery decisions.”

**Disclosure:** Cedarbridge is not a client, NHS project or commissioned engagement. No real stakeholder interviews, operational savings, implementation benefits or formal UAT are claimed. AI helped create the artefacts; the project is an independent learning exercise.


## Analytics extension — 13 November 2026

To explore *how* operational visibility might be measured without pretending to have real business data, I added a separate [interactive synthetic dashboard](analytics.html), a reproducible 160-row fictional dataset and a [KPI dictionary](KPI_DEFINITIONS.md) with explicit definitions, denominators and caveats. The dashboard includes volume, backlog, response within 24 elapsed hours, resolution within 72 hours, request-type/status breakdowns, older open records and filters/CSV export.

**Reporting evidence:** The dashboard rendered in controlled Chromium without script errors, and its visible default totals matched the supplied CSV/JSON. All values are **illustrative only** and unconnected to the service-request app's localStorage. This is an HTML/JavaScript demonstration; the optional Power BI DAX guide is a draft learning exercise, not a completed `.pbix` or deployed BI solution. Jira SCRUM-20 tracks the measurement design, while SCRUM-7 remains a broader proposed dashboard user story.

## Portfolio presentation status

The recruiter-facing offline package now includes `index.html` as the site landing page, `app.html` as the runnable prototype and `analytics.html` as the separate reporting concept. This is a **complete portfolio submission package**, not an assertion that the fictional Sprint 1, formal UAT or the secure production roadmap is completed.
