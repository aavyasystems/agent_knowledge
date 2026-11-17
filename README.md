# Aavya agent knowledge

Source of truth for what the owner and guest WhatsApp agents know about Aavya.

- `core.md`: always loaded into every conversation. Keep it small: voice, fixed prices, links, hard rules.
- `topics/*.md`: loaded on demand by both agents (`aavya_knowledge` tool). One file per subject.
- `owner_topics/*.md`: owner agent only. Internal rules, discounts, open questions.

## Editing
1. Change one topic file. Prices and policies go in the topic and, if headline, in `core.md`.
2. Add a line to `CHANGELOG.md` with the reason and source.
3. Open a pull request or commit to `main`; every change is reviewable and reversible.
4. Deploy: copy into `aavya-agent/src/aavya_agent/knowledge/` on the server and run `./scripts/install.sh` there (no automatic
   sync yet). Topic files are statements: Facts (may be told), Internal (never told), Flex and Guidance (instructions).

## Use as the owner agent in Claude Code
1. `git clone https://github.com/aavyasystems/agent_knowledge.git && cd agent_knowledge && claude`
2. Approve the `aavya` MCP server when asked, then `/mcp` → `aavya` → Authenticate, and enter the team access secret on the
   systems.aavya-rise.com page.
3. Ask anything: "what's pending", "who is staying tonight", "reply to Celina that the piece is not fired yet".
The skill `.claude/skills/aavya-owner/SKILL.md` loads automatically. Pull the repo to get knowledge updates.

Never store live Nami prices, availability, bookings or guest data here. This repo must stay private.
