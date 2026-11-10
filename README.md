# LoonBids plugin

Find Canadian tenders from your AI assistant, check which ones fit your company, see who won similar contracts, and get email alerts for new matches. Data comes from government open data and public notices (details on [loonbids.com/resources](https://loonbids.com/resources#sources)); LoonBids is independent and not affiliated with any government.

## What's in it

- `.mcp.json` (Claude Code) and `mcp.json` ([Agent Plugins](https://agent-plugins.org)): the remote LoonBids MCP server, `https://app.loonbids.com/mcp`. The first tool call asks you to sign in to LoonBids (a free account is enough). No API keys are stored here.
- `skills/`: `find-tenders`, `check-fit`, `set-up-alerts`, `who-wins-this-work`.
- `.claude-plugin/plugin.json`, `.cursor-plugin/plugin.json`, `plugin.json`: manifests for Claude Code, Cursor and Agent Plugins. `.claude-plugin/marketplace.json` makes the repo its own one-plugin Claude Code marketplace.
- `assets/logo.png` (transparent mark, used by Cursor) and `assets/icon.png` (on white: the ChatGPT listing and composer icon, readable in dark mode).

## For maintainers

`.claude/skills/` holds OpenAI's official `plugin-creator` and `chatgpt-app-submission` skills (from [openai/plugins](https://github.com/openai/plugins), Apache 2.0) for packaging and submitting this plugin. They aren't part of the plugin; only `skills/` is.

## Install

- **Claude Code**: `/plugin marketplace add halitdincer/loonbids-plugin`, then `/plugin install loonbids@loonbids`. Or try it for one session: clone this repo and run `claude --plugin-dir ./loonbids-plugin`.
- **Cursor**: from the Cursor plugin marketplace once listed (it reads `.cursor-plugin/plugin.json` and `mcp.json`).
- Other [Agent Plugins](https://agent-plugins.org) hosts read `plugin.json` and `mcp.json`.

Check it with `claude plugin validate --strict .` and `claude plugin validate --strict .claude-plugin/marketplace.json`.

## Without the plugin

- Claude Code: `claude mcp add --transport http loonbids https://app.loonbids.com/mcp`
- Claude, ChatGPT, Cursor, VS Code: see [loonbids.com/connect](https://loonbids.com/connect).

## Privacy and support

[Privacy](https://loonbids.com/privacy) · [Terms](https://loonbids.com/terms) · [Support](https://loonbids.com/support) · hello@loonbids.com
