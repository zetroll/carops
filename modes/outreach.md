# Mode: outreach — warm-intro + cold-message engine

When the user says "draft an intro to {IC member}" or "outreach for {incubator}", produce ready-to-send messages.

## Required reads

1. `kraft.md` — for the positioning + traction
2. `founder.md` — warm-intro graph
3. `reports/selection-committees.md` — IC member backgrounds + warm-intro vectors

## Step 1 — Detect the vector

For the target person, classify the introduction path:

- **Direct first-degree** (e.g. founder's father knows them): ask for live intro, NOT email — phone or in-person.
- **Second-degree warm** (mutual on LinkedIn, alumni overlap): request a forwarded intro email; templates below.
- **Cold** (no overlap): direct LinkedIn message + 2-week follow-up cadence.

## Step 2 — Draft per vector

### Warm intro — request email (to the connector)

```
Subject: Quick favor — intro to {target} at {incubator}?

Hi {connector},

Hope you're well. I'm raising grant capital for ThoughtKraft (an AI-
infrastructure platform for Indian commerce — ₹1L MRR, 3 paying
customers including a Unilever-funded brand) and we're applying to
{incubator}.

I noticed you know {target} — would you be open to a 1-line forward?
Drafted below for ease, edit as you like:

---
{name} — meet Purvabh, ex-Amazon Sr. PM (3 yr Gen AI), now bootstrapping
ThoughtKraft. He's applying to {incubator}'s {track} and would love 15
min to road-test his thesis with you.
---

Happy to share the deck/memo on request.

Thanks,
Purvabh
```

### Cold LinkedIn — initial message

```
Hi {target},

Building ThoughtKraft — AI-infrastructure layer for Indian commerce.
Live in production with 7 modules, ₹1L MRR, 3 paying customers
(SkinInspired, StayVista, Monarch Networth Capital).

Applying to {incubator} — your perspective on {their domain} would be
valuable. Open to 15 minutes?

Brief: thoughtkraftai.com
```

### Cold follow-up (10 days later, no reply)

```
Hi {target} — circling back. We'd value 15 min before our {incubator}
application lands. Recent signal: {one new thing — a logo, a metric, a
shipped module}.

Direct calendar: {link}.
```

## Step 3 — Log to founder.md and ic-trigger log

Every sent message → log in `data/ic-triggers.md` so we can track:
- Who was contacted, when, with what message
- Reply received? Y/N
- Outcome (intro received, meeting set, no-reply)

After replies, update `founder.md` warm-intro graph table with new connections discovered.

## Hard rules

- **Never send.** The agent drafts. Founder copies-pastes.
- **Never overstate the network.** If the connector has only a 2nd-degree LinkedIn connection, frame it that way — "I noticed you may know" — not "your friend".
- **Never fabricate credentials.** Don't invent an Amazon team or imply Unilever as a direct customer.
- **Always personalize the {their domain}** field — generic "would value your time" reads as spam.

## Output to disk

`reports/outreach/{YYYY-MM-DD}-{target-slug}.md` — the draft message + the source vector + the log entry to copy into `data/ic-triggers.md`.

