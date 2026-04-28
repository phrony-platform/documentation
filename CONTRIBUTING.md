# Contributing to Phrony documentation

## Edit in GitHub

1. Open the `.mdx` file you want to change.
2. Use the GitHub editor and open a pull request.

## Local preview

1. Clone this repository.
2. Install the [Mintlify CLI](https://www.npmjs.com/package/mint): `npm i -g mint`
3. From the repository root (where `docs.json` is), run `mint dev`.
4. Preview at `http://localhost:3000`.

## Writing guidelines

- Use active voice and address the reader as **you**.
- Prefer one idea per sentence; lead with the goal of the section.
- Use terminology from [AGENTS.md](./AGENTS.md) consistently.
- Do not add Mintlify starter or third-party template pages unless they describe Phrony.

## Dialog description markup (Phrony web app / monorepo)

This note applies to the **Phrony dashboard** UI in the main product monorepo, not to Mintlify `.mdx` content here. It is documented alongside these docs so maintainers working in both places see the constraint.

**Limitation:** In HTML, a `<p>` element cannot legally contain block-level descendants such as `<ul>`, `<ol>`, nested `<p>`, or `<div>`. Browsers implicitly close the paragraph when they encounter them, which produces **invalid DOM** and can trigger **React hydration mismatches** (Next.js will often log this as a hydration error).

**Context:** Base UI’s dialog `Description` primitive renders a `<p>` by default. Any richer body (bulleted lists, block layouts, or components that render those) must not be authored as a raw child of that `<p>`.

**What we did:** Shared wrappers default the description element to a `<div>` via Base UI’s `render` prop (e.g. `render={render ?? <div />}`) so block content is valid. Implementations live under the monorepo’s dashboard app, in `components/cockpit/src/components/ui/alert-dialog.tsx` (`AlertDialogDescription`) and `dialog.tsx` (`DialogDescription`). Call sites can still pass a custom `render` when they need a different host element.

If you add lists or other blocks inside a dialog or alert description in that app, use those wrappers (or keep using a `<div>` host) instead of relying on a plain `<p>` description.
