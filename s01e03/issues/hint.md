Split from support desk ticket #4471 ("dates parse mm/dd in eu locales", 412 reports, marked known).

**Reports: 33** of the 412 in #4471 · 3 tenants · received 2026-04-17 → 2026-09-22

The booking-v3 form prints `MM/DD/YYYY` under its date field. People type the month first, as the hint says. The form then reads the date the tenant's way, day first. So the day and the month swap.

This is not the parser bug: it happens only through the form, only for the 3 tenants on booking-v3 (alder.physio, copper.studio, pale.harbour). Fixing the parser does not fix it.
Intake tagged 15 of these 33 as `parser`, because the tag comes from the reporter's browser.
Fix: make the booking-v3 hint match the order the form reads (the tenant's locale).

How we counted: the 412 unique reports in `reports-4471.json` (427 rows, 15 duplicates), split by `causeOf` in `src/lib/kb/causes.ts`, by tenant, channel and form. Counts are on the kb page `/kb/incidents/4471-split`.

<details><summary>All 33 report ids</summary>

R-41230, R-41241, R-41251, R-41259, R-41262, R-41275, R-41294, R-41305, R-41308, R-41366, R-41372, R-41384, R-41387, R-41396, R-41400, R-41406, R-41415, R-41416, R-41418, R-41428, R-41439, R-41441, R-41449, R-41453, R-41456, R-41460, R-41472, R-41485, R-41493, R-41539, R-41572, R-41582, R-41584
</details>
