# incubator-ops — ThoughtKraft AI Partners LLP

Single-tenant fork. Adapted from career-ops (job-application automation) into incubator-ops (Indian startup incubator application automation) for ThoughtKraft / Purvabh Surana.

## What this is

AI-assisted pipeline for applying to Indian startup incubators. Same architecture pattern as career-ops, retargeted from "job offers" to "incubator programs":

| Job-era concept | Incubator-era concept |
|---|---|
| `cv.md` | `kraft.md` (startup) + `founder.md` (founder bio) |
| `article-digest.md` | `data/proof-points.md` |
| Job offer / JD | Incubator program intake |
| `oferta` mode | `evaluate` mode |
| `apply` mode (form-fill) | `apply` mode (memo + deck + form + outreach) |
| `interview-prep` | `ic-prep` |
| `contacto` (LinkedIn) | `outreach` (warm-intro + IC member messaging) |
| `tracker` | `data/incubators.md` |
| `scan.mjs` (job portals) | `pipeline.md` (manual URLs for now; scanner later) |

## Sources of truth (read in this order)

1. `kraft.md` — startup one-pager (LLP, MRR, modules, customers, capital ask, customer-logo policy)
2. `founder.md` — Purvabh Surana bio + warm-intro graph
3. `data/proof-points.md` — metrics, customer stories, modules
4. `modes/_profile.md` — narrative archetypes + tier strategy
5. `modes/_shared.md` — system rules, scoring blocks
6. `reports/top-30-ranked.md` — current Top 30 ranked by ThoughtKraft fit
7. `reports/intake-calendar.md` — what to apply to and when
8. `reports/selection-committees.md` — IC roster across all 30
9. `reports/govt-schemes.md` — SISFS/NIDHI/AIM/MeitY channels
10. `reports/incubators/*.md` — per-incubator strategy briefs

## Hard rules (never violate)

1. **Capital policy:** grants only; equity acceptable only if ≤3% AND ≥₹20L. Refuse equity below ₹20L.
2. **Customer logos:** SkinInspired (Unilever-funded), StayVista, Monarch are paying. Flipkart is a project. Unilever is NEVER a direct customer.
3. **Never submit applications.** Generate the packet; founder clicks Submit.
4. **Never invent metrics.** Read from `kraft.md` + `data/proof-points.md`.

## Mode dispatch table

When the user says... → run mode...

| Trigger | Mode |
|---|---|
| "evaluate {incubator}" / "look into {URL}" / pastes URL | `evaluate` |
| "apply to {incubator}" / "draft my {X} application" | `apply` |
| "I got rejected by {X}" / "should I reapply?" | `reapply` |
| "prep me for {X} IC" / "I'm pitching {X}" | `ic-prep` |
| "draft an intro to {person}" / "outreach for {X}" | `outreach` |
| "process my pipeline" / "evaluate the URLs" | `pipeline` |

For first-time users: read `kraft.md`, `founder.md`, `data/proof-points.md` once at session start. Note any `__FILL__` markers and surface them via `data/needs-from-you.md`.

## Hands-free + multi-turn workflow

The user explicitly works in hands-free mode. When given a complex task:
- Break into phases (research → canonical docs → deliverables → cleanup → docs).
- Commit + push after each phase rather than at the end.
- Each Write/Edit ≤200 words to avoid stream timeouts.
- Use TodoWrite to track phases. Update statuses as you go.
- If a research agent is launched, it returns asynchronously — keep working on non-overlapping tasks.

## Project structure

```
ROOT
├── kraft.md                    — startup one-pager
├── founder.md                  — founder bio + warm-intro graph
├── CLAUDE.md                   — this file (agent entry point)
├── README.md                   — human entry point
├── modes/
│   ├── _shared.md              — system rules
│   ├── _profile.md             — ThoughtKraft narrative + tier strategy
│   ├── evaluate.md, apply.md, reapply.md, ic-prep.md, outreach.md, pipeline.md
├── data/
│   ├── proof-points.md         — metrics + customer stories + modules
│   ├── needs-from-you.md       — pending __FILL__ items
│   ├── research/tier-{a,b,c}/  — 30 raw research files
│   ├── incubators.md           — tracker (created on first run)
│   └── pipeline.md             — pending URLs (created on first run)
├── reports/
│   ├── top-30-ranked.md        — master ranking
│   ├── intake-calendar.md      — 60/90/180-day deadlines
│   ├── selection-committees.md — IC atlas + warm-intro graph
│   ├── govt-schemes.md         — SISFS/NIDHI/AIM/MeitY channels
│   └── incubators/             — per-incubator strategy briefs (1-10 detailed, 11-30 condensed)
├── templates/
│   └── states.yml              — canonical pipeline states
└── config/
    └── profile.yml             — founder/startup config (gitignored)
```

## Today's date for forward-looking content: 2026-04-29.

## What's NOT here (vs. the upstream career-ops)

- No PDF/LaTeX generation pipeline (deferred — markdown-only deliverables for now).
- No portal scanner (.mjs) — programs vary too much; manual `pipeline.md` for now.
- No multi-language modes (India-only; English).
- No OpenCode/Gemini slash commands (Claude Code only).
- No upstream `update-system.mjs` checker (this fork has diverged).
- No batch processing infrastructure (single-tenant, low volume).

