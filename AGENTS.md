> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- Phrony **customer-facing** documentation on [Mintlify](https://mintlify.com)
- Content is currently **`index.mdx` only** (introduction). Navigation lives in `docs.json` (**Documentation** → **Overview**, plus **Academy** and **API** tabs that also point at `index` until more pages exist).
- Run `mint dev` to preview locally; `mint broken-links` to check links
- **Voice**: say **Phrony**, **Phrony dashboard**, **API** — do **not** use internal code names (e.g. Cockpit, control-plane) in user-visible MDX
- **Contributors** who also work on the Phrony monorepo: see [CONTRIBUTING.md](./CONTRIBUTING.md) (includes HTML/dialog notes for dashboard UI)

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
