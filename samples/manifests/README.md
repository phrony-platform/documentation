# Sample Phrony manifests

Open-source registry (GitHub): [**phrony-platform/manifests**](https://github.com/phrony-platform/manifests).

This folder holds **two** parameterized examples you can copy and adapt. Each uses [manifest inputs](/concepts/manifest#manifest-inputs) (`inputs` + `{{inputs.*}}`) and a **`phrony.values.yaml`** beside the entry YAML for **`phrony lint`**, **`phrony plan`**, and **`phrony apply`** (see [Plan, apply, and diff](/packages/cli/manifest)). In the dashboard, map **`integration`** and **`llm_provider`** inputs during **Import manifest** (agents list) or **Apply manifest** (**Agent options** on an agent). After apply, finish **integration connection** in the Phrony dashboard when prompted.

| Folder | Use case |
| ------ | -------- |
| `telegram-public-api-notify/` | **HITL** agent: **API** trigger → **cat fact** (public HTTP) → **Telegram** send (approval), **`telegram_chat_id`**. |
| `gmail-new-mail-hitl/` | **HITL** agent: **Gmail** **new message** event trigger (Composio **`GMAIL_NEW_GMAIL_MESSAGE`**), fetch mail, **triage label**, **reply draft** (approvals on label + draft). |

## Telegram + public API (`telegram-public-api-notify/`)

Each run **fetches one cat fact** from `https://catfact.ninja/fact` and **sends it to Telegram**. **HITL** + **require approval** on Telegram send lets a human approve delivery. See [Sample manifests](/samples/manifests) on the docs site for the full walkthrough and `phrony lint` command.

## Gmail new mail — label + draft (`gmail-new-mail-hitl/`)

When **Composio’s Gmail “New Gmail Message Received”** trigger fires (poll; slug **`GMAIL_NEW_GMAIL_MESSAGE`** per [Composio Gmail triggers](https://docs.composio.dev/toolkits/gmail)), Phrony starts a run on a **HITL** agent that:

1. **Fetches** the new message by id (`GMAIL_FETCH_MESSAGE_BY_MESSAGE_ID`).
2. Optionally **lists labels** (`GMAIL_LIST_LABELS`) if ids are unclear.
3. **Applies a triage label** (`GMAIL_ADD_LABEL_TO_EMAIL`) using **`triage_label_id`** from your values / apply inputs — **require approval**.
4. **Creates a reply draft** in-thread (`GMAIL_CREATE_EMAIL_DRAFT`) — **require approval**.

Set **`triage_label_id`** to a real Gmail **label id** (for example `Label_…`), not only the display name. Trigger **`eventConfig.userId`** is set to **`me`** in the sample; adjust in YAML if your catalog expects a different shape.

## Validate with the CLI

From the root of this **documentation** repository:

```bash
phrony lint samples/manifests/telegram-public-api-notify/manifests
phrony lint samples/manifests/gmail-new-mail-hitl/gmail-new-mail-hitl.yaml
```

The CLI picks up **`phrony.values.yaml`** automatically when it sits next to the manifest path you pass to **`lint`**, **`plan`**, or **`apply`**; otherwise pass **`--values`** (see [Plan, apply, and diff](/packages/cli/manifest)).

On the published Phrony docs, open **Sample manifests** (`/samples/manifests`).
