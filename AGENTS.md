> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- Phrony **customer-facing** documentation on [Mintlify](https://mintlify.com)
- Pages are MDX under `index.mdx`, `academy/`, `product/concepts/`, `product/dashboard/`, `product/reference/`, and `api-reference/`
- Navigation lives in `docs.json`
- Run `mint dev` to preview locally; `mint broken-links` to check links
- **Voice**: say **Phrony**, **Phrony dashboard**, **API** — do **not** use internal code names (e.g. Cockpit, control-plane) in user-visible MDX

## Terminology

- **Workflows vs. agents** — `product/workflows-vs-agents.mdx`
- **Academy** — `academy/*.mdx` (deploy, multi-agent, Guard L1)
- **Agent** — `product/concepts/agent.mdx`
- **Agent version** — `product/concepts/agent-version.mdx`
- **Session** — `product/concepts/session.mdx`
- **Run** — `product/concepts/run.mdx`
- **Trigger** — `product/concepts/trigger.mdx`
- **LLM provider** — `product/concepts/llm-provider.mdx`
- **Secret** — `product/concepts/secret.mdx`
- **Integration** — `product/concepts/integration.mdx`
- **Limits, permissions, plans** — `product/reference/platform-rules.mdx`
- **Dashboard (brief)** — `product/dashboard/*.mdx` (home, settings, approvals, guard)

## Style preferences

{/* Add any project-specific style rules below */}

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references

## Content boundaries

{/* Define what should and shouldn't be documented */}
{/* Example: Don't document internal admin features */}
