# MORYA for Claude

The official MORYA plugin for Claude. It connects Claude to your MORYA account
through MORYA's remote MCP server, and teaches Claude how to use it well.

MORYA is a French real-estate intelligence suite: market prices and rents
(DVF, INSEE, DPE), property listings, rental yield, rental management (Pilot),
short-term rentals (Stay) and off-market prospecting (Radar).

## Install

In Claude Code:

```
/plugin marketplace add PauFou/morya-claude-plugin
/plugin install morya@morya
```

The first time a MORYA tool is used, Claude opens the MORYA sign-in and
authorization page. Access follows your subscription, product by product:
you only get the modules you subscribe to.

## Security and privacy

- Authentication is OAuth 2.1 with PKCE. This repository contains **no keys,
  tokens or credentials** — only the public address of the MCP server.
- Nothing is ever modified without you: every write (adding a favourite,
  marking a rent as paid…) is first proposed in the conversation, and happens
  only once you say yes. The confirmation token is single-use, expires after
  ten minutes and is bound to the exact action you approved.
- You can revoke Claude's access at any time from your MORYA settings; the
  revocation applies to the very next call.
- Privacy policy: https://morya.app/confidentialite · Contact: contact@morya.app

## Contents

- `.claude-plugin/marketplace.json` — this repository is a plugin marketplace.
- `plugins/morya/.claude-plugin/plugin.json` — the plugin manifest.
- `plugins/morya/.mcp.json` — the remote MCP server (`https://invest.morya.app/mcp`).
- `plugins/morya/skills/morya/SKILL.md` — usage guidance read by Claude.

## License

MIT for the files of this repository. The MORYA service itself is proprietary.
