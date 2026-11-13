# UX iteration | From basic MVP to a more deliberate interface

**Feedback:** Portfolio owner described the basic workflow as **easy to use**. They later asked for a purple/lilac palette and a look that felt less like a generic AI-made template.  
**Tracking:** [SCRUM-27](https://cedarbridge-portfolio.atlassian.net/browse/SCRUM-27) · **Build:** v1.3, created 13 Nov 2026, **owner review pending**.

## What changed

- Replaced green accent and sidebar with deep aubergine navigation and quiet lavender focus states.
- Reduced unnecessary ornamentation and visual hierarchy changes; introduced a more restrained metrics strip and straightforward request table.
- Regularised spacing, control sizes, typography and desktop action placement.
- Changed the navigation label **New request** to **Create request** to distinguish navigation from request state **New**.
- Refined mobile scrolling behaviour and maintained visible keyboard focus styling.
- Retained fictional data labels and clear notice that no backend, authentication or genuine RBAC exists.

## What deliberately did not change

- Business workflow, proposed transitions, local audit data structure, JSON/CSV export and same browser localStorage key.
- Existing synthetic request data must still be backed up/exported before changing HTML files; file-origin storage may vary.
- The server/security restrictions and formal UAT status.

## Evidence and evaluation boundary

Controlled Chromium checks with mocked storage passed for intake → owner → Start work → status log, Viewer UI, exports, insights and mobile width. The screenshots in `assets/` show the v1.3 visual treatment, but do **not** show formal user approval. Native Edge retest and owner visual feedback are the next acceptance steps.

## Rationale

The design goal was not to add more features or decoration. It was to make the same work easier to scan: recognisable navigation, obvious actions, legible states and less ambiguity between a page name and a request's status.
