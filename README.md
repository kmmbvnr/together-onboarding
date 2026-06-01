# Together Onboarding

Intern onboarding **coach** for the **Together / Хочу.Вместе** project (a Telegram Mini App for Astana). It
runs inside your AI agent and walks a new intern through short, hands-on drills — universal foundations first
(the terminal, Git, `uv`, Node, then the ideas behind the stack), then a light tour of our repo, then the
backend (Django) and frontend (`mates/`). Drills are read/run/trace only — no code changes. The course
content lives on the RunDrill MCP server (behind sign-in); this repo is the thin client plugin and doubles
as its own one-plugin marketplace.

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
ln -s "$PWD/together-onboarding" ~/.gemini/config/plugins/together-onboarding
```

## First run

On first use the coach connects to the RunDrill MCP server and asks you to **Authorize**
`together-onboarding` — a browser tab opens for a quick sign-in, then closes. No API key to paste. Until
it's authorized, the coach won't run. The course is private: only authorized users get drills.

## Layout

The plugin lives at the repo **root** (`.claude-plugin/plugin.json`, `skills/`, `.mcp.json`, per-host
manifests), and `.claude-plugin/marketplace.json` lists it (`source: "./"`) so the repo is installable as a
marketplace and mountable as a git submodule. The course curriculum and the cohort's data are **not** here.
