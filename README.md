# S01E03 — what it shows

Triage for the support desk's date reports merged into ticket #4471.

## Findings

- 379 unique reports concern the shared month-first parser in day-first locales.
- 33 unique reports concern the booking-v3 date hint and parse-order mismatch.
- The export has 427 rows; deduplicating by report ID leaves 412 reports.
- The five one-day-move notes are part of the parser group.

## GitHub issues

- [Shared parser — 379 reports](https://github.com/robertziolkowski/s01e03-what-it-shows/issues/1)
- [Booking-v3 hint — 33 reports](https://github.com/robertziolkowski/s01e03-what-it-shows/issues/2)

## Knowledge base page

The signed KB source is at `support-kb/src/routes/kb/incidents/4471/+page.svx`; `preview/4471.html` is the desk-view rendering. Aggregate counts are in `support-kb/src/lib/data/report-4471-summary.json`. Raw report bodies are not included.
