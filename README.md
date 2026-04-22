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
| `product/concepts/*.mdx` | Agent, agent version, session, run, trigger, LLM provider, secret |
| `product/dashboard/*.mdx` | Phrony web app how-tos |
| `product/reference/platform-rules.mdx` | Limits, permissions, plans (user-facing) |
| `api-reference/introduction.mdx` | HTTP API overview |
| `docs.json` | Navigation and site config |

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md).
