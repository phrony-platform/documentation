# Sample Phrony manifest

This repository ships **one** parameterized example: **`telegram-public-api-notify/`** — a **HITL** agent that **fetches a cat fact** from a read-only public HTTP API and **sends it to Telegram**, started by an **API** trigger.

The YAML uses [manifest inputs](/concepts/manifest#manifest-inputs) (`inputs` + `{{inputs.*}}`). Put **`phrony.values.yaml`** next to the manifest entry file so the [Phrony CLI](/packages/cli/manifest) can substitute values for `phrony lint` / apply. **`telegram_service_name`** uses **`type: integration`**: in **Apply manifest** you pick an existing Telegram integration. After apply, finish **integration connection** in the Phrony dashboard when prompted.

| Folder | Use case |
| ------ | -------- |
| `telegram-public-api-notify/` | **HITL** agent: **API** trigger → **cat fact** (public HTTP) → **Telegram** send (approval), **`telegram_chat_id`**. |

## Telegram + public API (`telegram-public-api-notify/`)

This manifest is a **small relay pattern**: an **API trigger** starts a run on a **HITL** root agent. Each run **fetches one cat fact** from a **read-only public HTTP** API (`https://catfact.ninja/fact`) and **sends that fact to Telegram**. **Human-in-the-loop** means the Telegram **send** operation uses **require approval** so a human **approves or rejects** the outbound message in the Phrony dashboard before delivery—not back-and-forth about what the text should be.

**How to use it**

1. **Apply** the manifest (dashboard or CLI with values). Set **`telegram_chat_id`** to the numeric chat your bot should post in.
2. **Connect** the Telegram integration (bot token). The **Cat Facts (public HTTP)** integration is declared in the manifest (read-only, no auth).
3. Open the agent’s **API trigger** and call it from your system (you can pass optional context in the payload). The agent fetches a fact and proposes the Telegram send; the operator **approves the send** when prompted.
4. Read more on HITL behavior in [Human in the loop (HITL)](/techniques/human-in-the-loop).

## Validate with the CLI

From the root of this **documentation** repository (with the Phrony CLI installed; see the CLI manifest docs in this repo):

```bash
phrony lint samples/manifests/telegram-public-api-notify/telegram-public-api-notify.yaml
```

The CLI picks up `phrony.values.yaml` automatically when it sits next to the manifest path you pass to `lint` or `apply`.

On the published Phrony docs, open **Sample manifests** in the navigation (`/samples/manifests`).
