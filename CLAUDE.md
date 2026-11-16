# Aavya owner workspace

Open Claude Code in this folder to work as Aavya's owner agent.

- The `aavya` MCP server (`.mcp.json`) gives the WhatsApp inbox, Nami PMS and payment tools. First use: run `/mcp`, pick
  `aavya`, sign in in the browser with the team access secret.
- The `aavya-owner` skill (`.claude/skills/aavya-owner/SKILL.md`) holds how to work: approvals, drafting, pending items, voice.
- Knowledge: `core.md`, `topics/`, `owner_topics/`. These files are the source of truth for both WhatsApp agents too.
