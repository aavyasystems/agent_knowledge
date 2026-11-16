# Aavya agent knowledge

Source of truth for what the owner and guest WhatsApp agents know about Aavya.

- `core.md`: always loaded into every conversation. Keep it small: voice, fixed prices, links, hard rules.
- `topics/*.md`: loaded on demand by both agents (`aavya_knowledge` tool). One file per subject.
- `owner_topics/*.md`: owner agent only. Internal rules, discounts, open questions.

## Editing
1. Change one topic file. Prices and policies go in the topic and, if headline, in `core.md`.
2. Add a line to `CHANGELOG.md` with the reason and source.
3. Open a pull request or commit to `main`; every change is reviewable and reversible.
4. Deploy: copy into `aavya-agent/src/aavya_agent/knowledge/` and run `./scripts/install.sh`.

Never store live Nami prices, availability, bookings or guest data here. This repo must stay private.
