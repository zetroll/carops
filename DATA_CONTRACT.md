# Data Contract — incubator-ops

This is a single-tenant fork. The career-ops "system layer / user layer" split was designed so an open-source repo could be auto-updated without touching personalization. This fork has diverged enough that the split is mostly informational — but it still helps the agent know what to treat as ground truth vs. what to update.

## User layer (ground truth — never auto-edit)

The agent reads these but never modifies them without explicit user request.

- `kraft.md` — startup one-pager
- `founder.md` — founder bio + warm-intro graph
- `data/proof-points.md` — metrics, customer stories, modules
- `data/needs-from-you.md` — pending fill items
- `modes/_profile.md` — narrative archetypes + tier strategy + customer-logo policy
- `config/profile.yml` (when written) — founder identity, contacts
- `data/research/tier-{a,b,c}/*.md` — raw research artifacts (re-run quarterly)

## Working layer (agent edits freely)

The agent appends to these and produces new files within them as part of normal operation.

- `data/incubators.md` — application tracker
- `data/pipeline.md` — pending URLs
- `data/reapply-log.md` — rejection cooldown ledger
- `data/ic-triggers.md` — outreach + IC contact log
- `reports/incubators/*.md` — per-incubator strategy briefs
- `reports/applications/*` — generated application packets
- `reports/outreach/*` — drafted outreach messages
- `reports/ic-prep/*` — IC pitch prep packets

## System layer (the rebuild, owned by the agent + repo)

Stable infrastructure. Agent modifies on intentional refactors only.

- `modes/_shared.md` — system rules, scoring blocks
- `modes/{evaluate,apply,reapply,ic-prep,outreach,pipeline}.md` — modes
- `templates/states.yml` — canonical pipeline states
- `CLAUDE.md`, `README.md`, `DATA_CONTRACT.md` — top-level docs
- `package.json`, `.gitignore`, `flake.nix`, `flake.lock` — tooling

## The single ground rule

When in doubt, **never** modify a file in the user layer without surfacing the change to the user first. Working-layer files are fair game for append-style automation; system-layer files are fair game for refactors.
