# Changelog

## 0.1.0 — 2026-04-29

Initial fork from [career-ops](https://github.com/zetroll/carops). Single-tenant rebuild for ThoughtKraft AI Partners LLP (Purvabh Surana). Adapted the career-ops job-application pipeline into incubator-ops for Indian startup incubator applications.

### Added

- `kraft.md`, `founder.md`, `data/proof-points.md` — canonical docs.
- `data/research/tier-{a,b,c}/` — 30 raw research files for the Top-30 incubators.
- `reports/top-30-ranked.md` — re-ranked Top 30 by ThoughtKraft probability.
- `reports/intake-calendar.md` — 60/90/180-day deadlines.
- `reports/selection-committees.md` — IC atlas with named members + warm-intro graph.
- `reports/govt-schemes.md` — SISFS / NIDHI / AIM / MeitY channels matrix.
- `reports/incubators/01-..-10-...md` — detailed per-incubator strategy briefs.
- `reports/incubators/11-30-condensed.md` — compact strategies for ranks 11–30.
- `modes/{_shared,_profile,evaluate,apply,reapply,ic-prep,outreach,pipeline}.md` — 8 modes.
- `templates/states.yml` — 16 canonical pipeline states.
- `data/incubators.md`, `data/pipeline.md`, `data/needs-from-you.md` — tracker scaffolds.
- `config/profile.example.yml` — founder/startup config schema.

### Removed (career-ops carryover not relevant)

- All job-era modes.
- Foreign-language modes (de, fr, ja, pt, ru) and localized READMEs.
- Job-era scripts and infrastructure (`scan.mjs`, `update-system.mjs`, etc.).
- Job-era directories (`batch`, `dashboard`, `examples`, `interview-prep`, `jds`, `output`, `fonts`).
- CV templates (HTML / LaTeX) and `portals.example.yml`.
- `.opencode/` and `.gemini/` slash commands.

### Hard-coded policies

- **Customer-logo policy:** SkinInspired (Unilever-funded), StayVista, Monarch are paying customers. Flipkart is a project. Unilever is NEVER a direct customer.
- **Capital policy:** grants only; equity acceptable only if ≤3% AND ≥₹20L.
- **Submission policy:** the agent never submits applications. Generates packets; founder clicks Submit.
