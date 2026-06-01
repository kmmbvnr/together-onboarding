# Together Onboarding

Marketplace for the **Together / Хочу.Вместе** intern onboarding plugin. The plugin is an onboarding
**coach** that runs inside your AI agent and walks a new intern through short, hands-on drills in a real
checkout of the Together repo — across general concepts, repo orientation, the backend (Django), and the
frontend (the React mini app in `mates/`). Progress and the course content live on the RunDrill MCP server
(behind sign-in); this repo only ships the thin client plugin.

## Install

**Claude Code / Desktop**
```
/plugin marketplace add kmmbvnr/together-onboarding
/plugin install together-onboarding@together
/together-onboarding-coach
```

**OpenAI Codex**
```
codex plugin marketplace add kmmbvnr/together-onboarding
```
then install `together-onboarding` and start the coach.

**Google Antigravity** (no registry — drop the plugin folder in)
```
git clone https://github.com/kmmbvnr/together-onboarding.git
ln -s "$PWD/together-onboarding/together-onboarding" ~/.gemini/config/plugins/together-onboarding
```

## First run

On first use the coach connects to the RunDrill MCP server and asks you to **Authorize**
`together-onboarding` — a browser tab opens for a quick sign-in, then closes. No API key to paste. Until
it's authorized, the coach won't run. The course is private: only authorized users get drills.

## What's here

- [`together-onboarding/`](./together-onboarding/) — the plugin (skill + per-host MCP config).
- [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json) — the install index.

The course curriculum and the cohort's data are **not** in this repo.
