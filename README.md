# incubator-ops

AI-assisted pipeline for applying to Indian startup incubators. Single-tenant fork of [career-ops](https://github.com/zetroll/carops), retargeted from job-application automation to incubator-application strategy + delivery.

Built for **ThoughtKraft AI Partners LLP** (founder: Purvabh Surana).

## What this gives you

A working agent + structured knowledge base that:

1. **Ranks 30+ Indian incubators** by your actual probability of getting in — not by prestige. (`reports/top-30-ranked.md`)
2. **Tracks intake cycles** in a 60/90/180-day calendar so you don't miss deadlines like NASSCOM Emerge 50 (~17 May 2026 close). (`reports/intake-calendar.md`)
3. **Maps selection committees** with named members, what they care about, and warm-intro paths specific to your network. (`reports/selection-committees.md`)
4. **Decodes govt schemes** (SISFS, NIDHI-SSS, NIDHI-PRAYAS, MeitY TIDE 2.0, AIM ACIC/AIC) so you can apply scheme-first, incubator-second. (`reports/govt-schemes.md`)
5. **Generates per-incubator strategy** — 10 detailed briefs for the highest-probability programs, plus condensed strategies for the rest. (`reports/incubators/`)
6. **Drafts application packets** — form answers, 1-page memos, 10-slide deck specs, IC-member outreach drafts. Never submits.
7. **Manages reapply cooldowns** — 3-month SISFS rule, tier-specific delta requirements, automated cycle tracking.

## How to use

The system runs through Claude Code. Open this repo in your shell and start a session.

| You say... | Agent runs |
|---|---|
| "Evaluate {URL or incubator name}" | `evaluate` mode → produces an A–F brief in `reports/incubators/` |
| "Apply to {incubator}" | `apply` mode → drafts form answers + memo + deck spec + outreach |
| "I got rejected by {X}" | `reapply` mode → calculates cooldown + delta + reapply date |
| "Prep me for {X} IC pitch" | `ic-prep` mode → 60s opener + per-IC-member talk track + 10-Q rehearsal |
| "Draft an intro to {person}" | `outreach` mode → warm-intro request OR cold LinkedIn message |
| "Process my pipeline" | `pipeline` mode → loop through `data/pipeline.md` URLs |

## Project structure

```
.
├── kraft.md                        # startup one-pager (canonical)
├── founder.md                      # founder bio + warm-intro graph
├── CLAUDE.md                       # agent entry point
├── modes/                          # 8 modes: _shared, _profile, evaluate, apply, reapply, ic-prep, outreach, pipeline
├── data/
│   ├── proof-points.md             # metrics + customer stories + modules
│   ├── needs-from-you.md           # pending fills the founder still owes the system
│   ├── research/                   # raw research dumps for the Top 30 (tier-a/b/c)
│   ├── incubators.md               # tracker (created on first run)
│   └── pipeline.md                 # pending URLs (created on first run)
├── reports/
│   ├── top-30-ranked.md            # master ranking by ThoughtKraft probability
│   ├── intake-calendar.md          # 60/90/180-day deadlines
│   ├── selection-committees.md     # IC atlas + cross-cutting people-graph
│   ├── govt-schemes.md             # SISFS/NIDHI/AIM/MeitY channel matrix
│   └── incubators/                 # per-program strategy briefs (1-10 detailed, 11-30 condensed)
├── templates/
│   └── states.yml                  # canonical pipeline states
└── config/
    └── profile.yml                 # founder/startup config (gitignored)
```

## Provenance

This is a personal-use single-tenant fork. The upstream [career-ops](https://github.com/zetroll/carops) is open-source; this fork keeps the spirit (file-based knowledge, mode-dispatch, AI-augmented evaluation) but rebuilds the surface for Indian incubator applications instead of jobs.

The 30 incubators researched cover SISFS-channel TBIs, AIM ACIC/AIC, IIM/IIT/IIIT incubators, IIMA Ventures (CIIE), NSRCEL, T-Hub, NASSCOM, Upekkha, Axilor, GSF, Social Alpha, and several state-level programs. Research dumps in `data/research/` cite their sources.

## Disclaimers

- "Probability of getting in" is a directional estimate based on stated eligibility, narrative fit, and capital terms. Real outcomes depend on cohort timing, IC chemistry, and execution between application and decision — none of which any system can fully model.
- Incubator websites change frequently. Re-verify deadlines and IC composition before submitting.
- Several user-supplied premises in the original brief did NOT verify in research (e.g. "Axilor is now part of Accel" — false as of 2026). Always cross-check.

