Split from support desk ticket #4471 ("dates parse mm/dd in eu locales", 412 reports, marked known).

**Reports: 5** of the 412 in #4471 · 5 tenants · received 2026-04-02 → 2026-10-04

These reports are not a day/month swap. The date lands one day off: "Tuesday 12 May… Calendar says Monday 11 May", "Every booking in June is one day off", "Client in Lisbon got Tuesday. Client in Toronto got Monday."
This looks like a time zone problem (a date turned into a time and back in another zone). Not verified: we have no logs, only the reports.

The desk noted them as a one-day move (desk-notes.json). It files them by tenant, so they also count in the parser ticket (#1, 379). Fixing the parser does not fix them.

How we counted: the 412 unique reports in `reports-4471.json` (427 rows, 15 duplicates), split by `causeOf` in `src/lib/kb/causes.ts`, by tenant, channel and form. Counts are on the kb page `/kb/incidents/4471-split`.

<details><summary>All 5 report ids</summary>

R-41202, R-41209, R-41236, R-41344, R-41620
</details>
