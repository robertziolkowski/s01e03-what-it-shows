# S01E03 work package

Public deliverables for the MEGA.dev challenge “what it shows”. The repository contains only aggregate counts; raw report bodies remain local and are not included.

## Findings

- The export has 427 rows and 412 unique report IDs; 15 rows repeat an ID.
- 379 unique reports fit the shared parser issue.
- 33 unique reports fit the booking-v3 date-hint issue.
- All 412 unique reports were merged into support ticket #4471.
- The five one-day-move notes fall within the parser group.
- The 2026-10-05 engineering update marks the parser fixed and the retired booking-v3 hint won't fix; the matching issues are closed as done and not planned.

## GitHub issues

- [Shared parser — 379 reports](https://github.com/robertziolkowski/s01e03-what-it-shows/issues/1)
- [Booking-v3 hint — 33 reports](https://github.com/robertziolkowski/s01e03-what-it-shows/issues/2)

## Knowledge base

- Canonical signed page: [src/routes/kb/incidents/4471/+page.svx](https://github.com/robertziolkowski/s01e03-what-it-shows/blob/main/src/routes/kb/incidents/4471/%2Bpage.svx)
- Desk-view preview: [preview/4471.html](https://github.com/robertziolkowski/s01e03-what-it-shows/blob/main/preview/4471.html)
- Aggregate data and required KB components live under src/lib. The support-kb directory also keeps an export-shaped copy.

Raw report bodies are not included.
