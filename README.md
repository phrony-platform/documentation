# Phrony documentation

Product documentation for Phrony, built with [Mintlify](https://mintlify.com).

## Preview locally

1. Install the Mintlify CLI: `npm i -g mint` (or use `npx mint dev` from the docs root).
2. From this directory (where `docs.json` lives), run:

   ```bash
   mint dev
   ```

3. Open `http://localhost:3000`.

## Structure

| Path | Purpose |
|------|---------|
| `index.mdx` | Introduction |
| `academy/*.mdx` | Academy guides: deploy your first agent (HITL, Gmail + Calendar), multi-agent |
| `product/concepts/*.mdx` | Agent, agent version, session, run, trigger, integration, LLM provider, secret |
| `product/dashboard/*.mdx` | Short dashboard screens (home, settings, approvals, guard) |
| `product/reference/platform-rules.mdx` | Limits, permissions, plans (user-facing) |
| `api-reference/introduction.mdx` | HTTP API overview |
| `images/*.png` | Screenshots (including Operations tab, integrations, agent create, etc.) |
| `docs.json` | Navigation: **Documentation**, **Academy**, and **API** Mintlify tabs |

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md).
