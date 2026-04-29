# Mode: reapply — when and how to apply again after rejection

When the user says "I got rejected by {X}" or "should I reapply to {X}?", this mode evaluates whether to reapply, when, and what delta is required.

## Step 1 — Log the rejection

Append to `data/reapply-log.md`:
- Incubator name + tier
- Date of rejection email
- Track applied to
- Reason cited (if given)
- Cooldown clock starts (3 mo standard for SISFS; varies otherwise)

## Step 2 — Read the cooldown

| Type of incubator | Default cooldown |
|---|---|
| SISFS-channel (any) | 3 months from rejection email per Startup India portal rules |
| AIM ACIC / NIDHI | 3 months default |
| IIM/IIT cohort programs | next cohort cycle (~6 months) |
| Private accelerator (NASSCOM, GSF, etc.) | next cohort or 6 months |
| Rolling regional TBI | informal — typically 3-6 months with delta |

Per-incubator overrides in `reports/incubators/{rank}-{slug}.md` "Reapply if rejected" section.

## Step 3 — Compute the required delta

Most incubators won't say it explicitly, but they expect a *meaningful improvement* before reading you again. Use this matrix:

| Tier of incubator | Minimum delta |
|---|---|
| Tier A (rolling, lower-bar) | one new logo OR ≥30% revenue jump OR new paid pilot |
| Tier B (cohort) | ≥50% revenue jump OR a tier-1 logo (Flipkart-MSA upgrade) OR co-founder hired |
| Tier C (elite) | ≥100% revenue jump OR a strategic partnership (acquihire offer, large enterprise contract) OR public IP artifact |

Cross-check ThoughtKraft's organic trajectory: 13% MoM compounded → 2x in ~5.5 months. So natural growth meets Tier-A delta in ~3 months and Tier-B delta in ~5-6 months.

## Step 4 — Recommend or refuse

Output one of:

- **Reapply now** (cooldown met, delta met) — generate refreshed packet via `apply` mode.
- **Reapply on {date}** (cooldown not met but delta will be) — schedule the date in `reports/intake-calendar.md`.
- **Wait for delta** (cooldown met but delta not yet) — list the specific milestones needed.
- **Don't reapply** (program turned out to be a poor fit; opportunity-cost too high) — mark Withdrawn in tracker.

## Step 5 — Compose the "delta narrative"

When reapplying, the application must lead with the delta. Format:

> "Last time I applied to {program}, I was at ₹{X}L MRR with {Y} customers. Today I'm at ₹{X'}L MRR with {Y'} customers, including {new logo}. Here's what changed in the last {N} months: ..."

This signals self-awareness AND meaningful progress — both of which reset the IC's prior.

## Anti-patterns

- Don't reapply with an identical packet. ICs remember (or read each other's notes). A fresh packet with no delta = auto-reject.
- Don't reapply before cooldown for SISFS — the portal may auto-reject the duplicate.
- Don't fabricate the delta. ICs verify by checking the customer / revenue claims.

## Output to disk

- Update `data/reapply-log.md` with cooldown clock and delta requirement.
- If reapplying now: trigger `apply` mode with the new packet referencing the delta narrative.
- Update `data/incubators.md` status: `Rejected → Reapply-Pending → Applied (round 2)`.

