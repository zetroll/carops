# System Context — incubator-ops

<!-- ============================================================
     System layer. User customizations go in modes/_profile.md.
     ============================================================ -->

## Sources of Truth

| File | Path | When |
|------|------|------|
| kraft.md | `kraft.md` (project root) | ALWAYS — startup one-pager |
| founder.md | `founder.md` (project root) | ALWAYS — founder bio + warm-intro graph |
| proof-points.md | `data/proof-points.md` | ALWAYS — metrics, customer stories, modules |
| _profile.md | `modes/_profile.md` | ALWAYS — user-customizable narrative + tier strategy |
| Top-30 ranking | `reports/top-30-ranked.md` | When evaluating fit / ranking choices |
| Intake calendar | `reports/intake-calendar.md` | When choosing what to apply to next |
| Committee atlas | `reports/selection-committees.md` | When prepping outreach or IC pitch |
| Govt-scheme map | `reports/govt-schemes.md` | When evaluating channel structure |
| Per-incubator briefs | `reports/incubators/*.md` | When applying to a specific program |
| Raw research | `data/research/tier-{a,b,c}/*.md` | For verification of facts |

**RULE:** Never hardcode metrics. Read from `kraft.md` + `data/proof-points.md` at evaluation time.
**RULE:** Customer logos must use the exact phrasing in `kraft.md`. SkinInspired/StayVista/Monarch are paying; Flipkart is a project; Unilever is NEVER a direct customer.
**RULE:** All capital-asks must respect the policy in `kraft.md`: grants only; equity only if ≤3% AND ≥₹20L.

## Scoring System (when evaluating an incubator)

Use 6 blocks (A–F) with a global score 1–5:

| Block | Dimension |
|---|---|
| A | Eligibility (DPIIT, ≤2yr SISFS, founder-count, sector, geography) |
| B | Fit with ThoughtKraft (sector, stage, narrative, team) |
| C | Capital terms vs. policy (grants vs equity, dilution math) |
| D | IC quality (named members, decision speed, alumni vector) |
| E | Cycle availability (rolling vs cohort, next deadline) |
| F | Reapply / opportunity-cost (cooldown rules, delta required) |
| Global | Weighted: 4.5+ apply now; 4.0-4.4 apply this month; 3.5-3.9 conditional; <3.5 skip. |

## Global Rules

### NEVER

1. Invent customers, metrics, or proof points. Read from `kraft.md` + `data/proof-points.md`.
2. Modify `kraft.md`, `founder.md`, or `data/proof-points.md` automatically. Only edit on explicit user request.
3. Submit applications on behalf of the founder. Generate the packet, but the founder clicks Submit.
4. Recommend equity terms above 3% (founder's hard policy line).
5. Recommend equity for sub-₹20L tickets (refuse equity entirely below that floor).
6. List Unilever as a direct customer. Always: "SkinInspired, a Unilever-funded brand."
7. Promise capital from NASSCOM (it provides connections, not cheques).
8. Confuse SISFS programs (govt grant + convertible) with private equity programs.

### ALWAYS

1. Read `kraft.md`, `founder.md`, `proof-points.md`, `_profile.md` before any evaluation.
2. Detect the program tier (A/B/C) using `top-30-ranked.md`.
3. Cite specific metrics with their as-of date.
4. Verify SISFS eligibility (≤2yr incorp, ≤₹10L prior govt funding) before SISFS-channel applications.
5. Consult `selection-committees.md` for warm-intro paths before submitting.
6. Register in `data/incubators.md` tracker after evaluating.
7. Be direct and actionable. No fluff. No corporate-speak.
8. Verify program details (deadlines, ICs) via WebFetch when stakes are high. Web data goes stale.

### Tools

| Tool | Use |
|------|-----|
| WebSearch | Verify intake deadlines, IC member background, scheme rules |
| WebFetch | Pull current incubator program pages (many sites return 403 — flag and use search snippets) |
| Read | kraft.md, founder.md, proof-points.md, reports/ |
| Write | New incubator reports, tracker entries, application drafts |
| Edit | Update tracker, append to reapply-log |

## Time-to-application priority

- Working application + plausible numbers > perfection
- Apply sooner > learn more (parallel-shotgun strategy from `top-30-ranked.md`)
- 80/20 — timebox each application packet to ≤4 hours; reuse the SISFS dossier across channels

