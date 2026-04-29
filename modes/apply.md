# Mode: apply — application packet builder

When the user says "apply to {incubator}", "fill the {X} form", or "draft my {Y} application", produce the complete packet. Generate, never submit.

## Required reads (in order)

1. `kraft.md` — startup one-pager (master metrics + positioning + customer logo policy)
2. `founder.md` — founder bio + warm-intro graph
3. `data/proof-points.md` — module catalog, customer stories, defensibility evidence
4. `modes/_profile.md` — narrative archetypes + capital policy
5. `reports/incubators/{rank}-{slug}.md` — per-incubator strategy (run `evaluate` first if missing)

## Packet contents

### 1. The form answers

For each form field, draft the response. Use the most-relevant archetype from `_profile.md`. Cite specific metrics from `proof-points.md`. Respect the customer-logo policy.

Common fields and the right framing:

| Field | What to write |
|---|---|
| Problem statement | "Indian MSMEs stitch 8–15 fragmented SaaS tools to run their commerce stack. The cost is ₹X/month + Y hours/week of ops time." |
| Solution | "ThoughtKraft is the AI-infrastructure layer that replaces those 8–15 tools with one platform. 7 modules live in production." |
| Traction | "₹1,00,000 MRR (up from ₹70K, 3 mo ago — ~13% MoM). 3 paying customers: SkinInspired (Unilever-funded D2C brand), StayVista, Monarch Networth Capital. Plus a paid Flipkart project." |
| Why us | "Solo founder, ex-Amazon Sr. PM (3yr Gen AI), IIFT Delhi + MIT Manipal. Shipped 7 modules in 9 months bootstrapped. Father (1% advisor) is ex-VP Reliance Industries — operator family." |
| Ask | follow `kraft.md` capital ask table; respect 3% / ₹20L floor |

### 2. The 1-page memo

If the form allows file uploads, attach a 1-page memo. Structure: TL;DR (60 words from kraft.md), Problem, Solution, Traction, Market, Why-us, Defensibility, Roadmap, Ask.

### 3. The 10-slide deck

If the form requires a deck, deliver this exact slide order:
1. Title — ThoughtKraft, operating system for Indian commerce.
2. Problem — 8–15 fragmented tools, with the cost numbers.
3. Solution — one AI-infrastructure layer, 7 modules.
4. Traction — three numbers in one slide.
5. Market — TAM/SAM/SOM (from `kraft.md`; flag if __FILL__).
6. Why now — ONDC, GST e-invoice, IndiaAI, LLM cost curve.
7. Why us — founder, education, prior pedigree.
8. Defensibility — flywheel, MSME UX, India-compliance graph.
9. Roadmap — 12-month plan with the program's support.
10. Ask — specific to this incubator's capital format.

### 4. Attachments checklist

- DPIIT certificate (PDF)
- LLP Memorandum of Association
- Customer LOIs / contracts (redacted if needed)
- Founder LinkedIn URL
- Pitch deck PDF
- 1-page memo PDF

### 5. Outreach pre-bundle

Before submitting, check `reports/selection-committees.md` for warm-intro vectors. Send 1-2 LinkedIn messages to IC members BEFORE the form goes in. The agent must present these draft messages to the user; user sends them.

## Hard rules

- **Never submit on behalf of the founder.** Generate everything; the founder clicks Submit.
- **Never invent metrics.** If `proof-points.md` says `__FILL__`, surface the gap to the user and ask, don't fabricate.
- **Always log to `data/incubators.md`** after generating the packet (status: Drafted → Applied when user confirms submit).
- **Always note the IC member outreach status** ("warm intro sent to {name} on {date}", or "no warm-intro vector available").

## Output to disk

Write the packet to `reports/applications/{rank}-{slug}-{YYYY-MM-DD}/`:
- `form-answers.md` — every Q answered
- `memo.md` and `memo.pdf` (if a generator is wired up — currently markdown only)
- `deck-outline.md` — 10-slide spec for founder to render
- `outreach.md` — pre-submission warm-intro draft messages

Then update `data/incubators.md` with status `Applied` (after user confirms submit) and the `reports/applications/...` path in the Notes column.

