# Together Onboarding (plugin)

Onboarding **coach** for the **Together / Хочу.Вместе** project (a Telegram Mini App for Astana). It runs
inside your AI agent and walks a new intern through short, **hands-on drills in a real checkout of the
Together repo** — not a generic course, a guided tour of *our* code and flows.

Tracks (Core orientation and Concepts foundations come either way):

- **Concepts** — general "what & why" behind the stack (12-factor apps, ORMs, queues, JWT, embeddings,
  SPAs, TypeScript, object storage, ML basics, …).
- **Core** — orientation in our repo (what it is, how to run it, the front↔back auth seam, the domain model).
- **Backend** — Django: the data models, the API + Telegram auth, the aiogram bot, Celery background work,
  the scrape → parse → moderate event pipeline, and the recommendation / friend-matching ML.
- **Frontend** — the React mini app in `mates/`: the Telegram SDK shell, auth + the API client, tabs &
  navigation, fetching & rendering events, components, Plans/Friends/Trophies, the Leaflet map, and i18n.

Progress and the chosen track live on the RunDrill MCP server, synced across machines.

## One plugin, three hosts

The coaching skill (`skills/together-onboarding-coach/SKILL.md`) and `.mcp.json` are shared; each host
reads its own manifest and ignores the rest.

| Host | Reads |
|---|---|
| Claude Code / Claude Desktop | `.claude-plugin/plugin.json` + `.mcp.json` |
| OpenAI Codex | `.codex-plugin/plugin.json` + `.mcp.json` |
| Google Antigravity | `plugin.json` + `mcp_config.json` (+ `rules/`) |

The MCP endpoint is `https://mcp.rundrill.com/prog/together-onboarding`. On first use the host opens a
browser tab for the OAuth handshake, then closes it — no API key to paste.

## Install

See the [marketplace README](../README.md). In short: add `kmmbvnr/together-onboarding` as a marketplace,
install `together-onboarding@together`, then run `/together-onboarding-coach`.
