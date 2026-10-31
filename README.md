# S01E03 "what it shows" — tickets from #4471 + the signed kb page

Deliverables for MEGA.dev challenge S01E03, all in this one public repo:

1. **One ticket per problem found in #4471** — GitHub issues in this repo, each stating
   how many reports it covers:
   - `parser`: the shared month-first parser flips day/month for day-first tenants —
     **379 of the 412 reports** merged into #4471 (all 11 tenants; app 204, email 150,
     booking-v2 form 25). See `analysis/groups-4471.json`.
   - `hint`: the booking-v3 form's `MM/DD/YYYY` hint is misread by day-first tenants on
     the web form — **33 of the 412 reports** (form channel only; the 3 booking-v3
     tenants alder.physio 12, copper.studio 11, pale.harbour 10).
   - 379 + 33 = 412 = all unique reports merged into #4471 (427 raw export rows, deduped
     by id; every row has `mergedInto: 4471`).
2. **The signed kb page about them** — added to the kb export in `support-kb/`:
   - source: `support-kb/src/routes/kb/incidents/4471/problems/+page.svx`
     (frontmatter carries `signature: omp-harness`; page ends with
     `<RenderStamp {signature} />`)
   - as the desk will see it: `support-kb/src/routes/kb/incidents/4471/problems/+page.html`
     (rendered with the kb's own runbook layout and cause model; desk ref
     `DR-5X0T-78KP` = `deskRef("omp-harness")`)

`support-kb/` is the unmodified kb export from
https://hq.mega.dev/challenges/what-it-shows plus the one added page.
`analysis/groups-4471.json` is the machine-readable breakdown (cause model ported
verbatim from `support-kb/src/lib/kb/causes.ts`, run with platform `Intl` locale data):
groups, counts, intake-tag disagreements (38 of 412), the desk-notes one-day-move
footnote (5 reports, all under `parser`).
