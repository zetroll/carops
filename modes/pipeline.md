# Mode: pipeline — process pending incubator URLs

When the user says "process my pipeline" or "evaluate the URLs in pipeline.md", run through `data/pipeline.md` in order.

## Required reads

1. `data/pipeline.md` — pending URLs (one per line; format: `URL [optional notes]`)
2. `kraft.md`, `founder.md`, `data/proof-points.md`, `modes/_profile.md`

## Loop per URL

For each URL in the pipeline:

1. **Parse** — identify incubator name and program track from URL/title.
2. **Lookup** — check if already in `data/research/tier-{a,b,c}/*.md` or `reports/incubators/`. If yes → skip to step 4.
3. **Research** — run a single-pass WebFetch (or WebSearch fallback if 403) to gather:
   - Official site
   - Apply portal
   - Intake model + next deadline
   - IC composition (if public)
   - Capital terms
   - Sector / stage filter
   - DPIIT/SISFS/AIM affiliation
   - Eligibility gates
4. **Evaluate** — invoke `evaluate` mode logic to produce the A–F brief.
5. **Write** — output to `reports/incubators/{rank}-{slug}.md`.
6. **Log** — add row to `data/incubators.md` tracker.
7. **Mark processed** — remove URL from `data/pipeline.md` (or move to a processed list).

## Triage decision per URL

After evaluation, output one of:

- **APPLY NOW** — score ≥4.5, hot deadline → invoke `apply` mode.
- **APPLY THIS MONTH** — score 4.0–4.4, rolling → schedule in `reports/intake-calendar.md`.
- **WATCH** — score 3.5–3.9, cohort/conditional → add weekly-watch note.
- **SKIP** — score <3.5 → mark in tracker, don't write a strategy report.

## Hard rules

- One URL at a time. Don't batch web-fetches in parallel — they can rate-limit.
- If a URL returns 403/404, mark it `Verification: unconfirmed` and proceed with WebSearch fallback rather than stalling.
- Always write the brief to disk, even for SKIP cases (one paragraph). Logged decisions are the value.
- Re-rank `reports/top-30-ranked.md` if a new incubator scores into the top 30.

## Output

After the loop completes, deliver a session summary:

```
Processed N URLs:
- M evaluated → reports/incubators/...
- K skipped (reasons cited)
- L hot deadlines → see reports/intake-calendar.md
- Top-30 ranking updated: Y/N
```
