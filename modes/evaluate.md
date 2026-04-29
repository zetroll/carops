# Mode: evaluate — single-incubator fit + strategy

When the user pastes an incubator URL, name, or program description, deliver the 6-block A–F evaluation. Treat the output as a per-incubator brief that lives in `reports/incubators/{rank}-{slug}.md`.

## Step 0 — Identify and locate

1. If incubator already in `reports/incubators/` → read existing brief; this is a refresh/update.
2. If new → check `data/research/tier-{a,b,c}/*.md` for raw research.
3. If neither → use WebFetch + WebSearch to gather facts (URL, intake model, IC names, capital terms, sector filter, eligibility gates).

## Block A — Eligibility check

Hard pass/fail per row. If any HARD requirement fails → score is at most 2/5 and recommend SKIP.

| Requirement | ThoughtKraft status |
|---|---|
| DPIIT recognition (if SISFS-channel) | check `kraft.md` |
| ≤2 yrs incorporation (SISFS) | verify ThoughtKraft AI Partners LLP date |
| ≤₹10L prior govt funding | check `data/cap-table.md` if exists |
| Founder count (some need 2+ FT) | solo + 1% advisor — likely fail if 2 FT required |
| Sector filter | compare to `kraft.md` positioning |
| Geography / state restriction | founder is Udaipur, Rajasthan |
| Alumni / affiliation gate | check education in `founder.md` (IIFT Delhi, MIT Manipal/MAHE) |
| LLP form | OK for SISFS/NIDHI/AIM grants; fails for traditional equity programs |

## Block B — Fit with ThoughtKraft

Map ThoughtKraft's positioning to the program's stated thesis. Use the relevant archetype from `_profile.md`:
- AIM/ACIC IAS-led → MSME-uplift framing
- IIM/B-school → structured-plan framing
- IIT/deep-tech → IP framing
- Private accelerator → global-trajectory framing
- Impact-mandate → reframe required (or skip)

State the fit out loud: "STRONG / MEDIUM / WEAK / SKIP".

## Block C — Capital terms vs. policy

| | |
|---|---|
| Format | grant / convertible / equity / mixed |
| Ticket size | ₹X – ₹Y |
| Equity ask | %, or "n/a (grant)" |
| Effective dilution | compute on convertible if cap is known |
| Policy compliance | PASS if grant-only OR (≤3% AND ≥₹20L); else FAIL |

If FAIL on policy → either negotiate (state target terms) or SKIP.

## Block D — IC quality + decision speed

From `reports/selection-committees.md`:
- Named IC members? (yes = high quality)
- Public criteria stated? (yes = lower variance)
- Decision speed (days from app to decision)
- Warm-intro vector available for ThoughtKraft?

## Block E — Cycle availability

| | |
|---|---|
| Model | rolling / cohort / challenge |
| Next deadline | YYYY-MM-DD or "rolling" |
| Window urgency | HOT (<30d) / MEDIUM (30-90d) / LOW (>90d / TBA) |
| Cost-of-application | hours of effort estimate |

## Block F — Reapply / opportunity-cost

If rejected:
- Cooldown period (3 mo for SISFS; varies otherwise)
- Required delta (revenue jump, logo addition, IP artifact, co-founder)
- Whether ThoughtKraft's organic growth meets that delta within the cooldown

## Output: write to disk

Save to `reports/incubators/{rank}-{slug}.md`. Format:

```
# Strategy — {Name} (rank N, prob X%)

**Status:** ⏳/🔥/📅/❌
**Decision body:** ...
**Capital:** ...
**Why apply (or not):** 1-2 lines.

## Eligibility check
(table from Block A)

## Application strategy
3 numbered points specific to this incubator.

## Anti-patterns
3 things NOT to do.

## Action checklist (this week)
- [ ] ...

## Reapply if rejected
- Cooldown: ...
- Required delta: ...
```

Then append a row to `data/incubators.md` tracker.

