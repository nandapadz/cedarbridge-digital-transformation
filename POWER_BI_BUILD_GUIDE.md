# Optional Power BI build guide | Training dataset only

**Important:** This is a draft DAX reference for future Power BI practice. The portfolio package includes an **HTML analytics dashboard**, not a published or independently tested `.pbix` dashboard. DAX below requires importing `data/synthetic_service_requests.csv` as a table named `Requests` and setting `created_at`, `first_response_at`, `resolved_at` to Date/Time (UK-local training timestamps).

```dax
Total Requests = COUNTROWS('Requests')

Open Backlog =
CALCULATE(
    COUNTROWS('Requests'),
    'Requests'[status] IN {"New", "In Progress", "Awaiting Information"}
)

Responded Requests =
COUNTROWS(FILTER('Requests', NOT ISBLANK('Requests'[first_response_at])))

First Response Within 24h =
COUNTROWS(
    FILTER('Requests',
        NOT ISBLANK('Requests'[first_response_at]) &&
        ('Requests'[first_response_at] - 'Requests'[created_at]) * 24 <= 24
    )
)

First Response Within 24h % =
DIVIDE([First Response Within 24h], [Responded Requests])

Completed Requests =
CALCULATE(COUNTROWS('Requests'), 'Requests'[status] IN {"Resolved", "Closed"})

Completed Within 72h =
COUNTROWS(FILTER('Requests',
    'Requests'[status] IN {"Resolved", "Closed"} &&
    NOT ISBLANK('Requests'[resolved_at]) &&
    ('Requests'[resolved_at] - 'Requests'[created_at]) * 24 <= 72
))

Completed Within 72h % =
DIVIDE([Completed Within 72h], [Completed Requests])

Ageing Open (72h) =
VAR Snapshot = DATE(2026,11,13) + TIME(12,0,0)
RETURN COUNTROWS(FILTER('Requests',
    'Requests'[status] IN {"New", "In Progress", "Awaiting Information"} &&
    'Requests'[created_at] < Snapshot - 3
))

Beyond Indicative Due =
VAR Snapshot = DATE(2026,11,13) + TIME(12,0,0)
RETURN COUNTROWS(FILTER('Requests',
    'Requests'[status] IN {"New", "In Progress", "Awaiting Information"} &&
    'Requests'[proposed_due_at] < Snapshot
))
```

**Additional event data:** `data/synthetic_request_events.csv` is an optional second table keyed by `reference` (one-to-many from Requests to Events), with an event timestamp and event type. The records and `proposed_due_at` are **invented to demonstrate modelling**. Validate Date/Time types and one-to-many relationship if using Power BI.

**Suggested pages:** 1. Service overview: 4 metric cards and two breakdowns. 2. Backlog diagnostic: open-age distribution, priority and owner. 3. Data quality: duplicate references, missing response fields and timestamp anomalies. Format rate measures as Percentage and include denominators in tooltips.

**Important modelling note:** For a real system, a status history/events table is needed to reconstruct backlog trends over time. This flat snapshot can describe current backlog, not historical backlog at previous dates. For production SLA reporting, calculate business time in an approved service calendar rather than relying only on simple Date/Time subtraction.
