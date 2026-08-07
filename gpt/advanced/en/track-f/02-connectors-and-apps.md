# F2 — Connectors & Working with Your Apps

⏱️ **15 minutes** · Track: 🅵 Beyond Chat · Needs: a ChatGPT Plus/Pro account + an app to connect

🌐 [Polski](../../pl/track-f/02-konektory-i-aplikacje.md) · [← Prev](01-deep-research.md) · [Track index](../README.md) · [Next: Image generation →](03-image-generation.md)

---

## 🧠 Theory (4 min)

Track E covered developer tools via MCP in the Codex CLI. In the **ChatGPT app**, the everyday integrations are **connectors** — link ChatGPT to your own apps so it can find and use your real content:

- **Google Drive** — find and read your docs/sheets.
- **Gmail / Calendar** — search email, see your schedule (where available).
- **GitHub, SharePoint, and others** — depending on your plan and region.

You enable a connector and sign in with OAuth — no config file, nothing to install. The same discipline from Track E applies: **least privilege, read first, approve every write.**

> Available connectors depend on your plan and region and change over time. Enable them under **Settings → Connectors** (or the app's "work with apps" menu).

---

## 🛠️ Practice (10 min)

### Step 1 — Connect one you actually use

**Settings → Connectors** → pick one (start with **Google Drive**) → **Connect** → complete OAuth and approve the access it requests.

> Approve only the scope you need. You can disconnect any connector later.

### Step 2 — Read-only wins first

```text
Find my "Q3 plan" doc in Drive and summarize its top 3 priorities.
```
```text
What's on my calendar tomorrow, and where are the gaps longer than 45 minutes?
```

Instant leverage — ChatGPT reaches your content instead of you copy-pasting.

### Step 3 — Draft, don't auto-send

For anything that leaves your hands, keep a human gate:

```text
Draft a reply to the latest email from <name> confirming the meeting.
Show me the draft — do NOT send it.
```

ChatGPT writes it; **you** send it.

### Step 4 — Combine connectors + other features

```text
Find this week's meeting notes in Drive, then draft a short summary email of
decisions and owners. Show me the draft before I send.
```

Or with Advanced Data Analysis (Track A3):

```text
Pull the "Sales" sheet from Drive and compute totals per region with a chart.
```

### Step 5 — Turn recurring chores into one prompt

Save prompts you'll reuse (Track A2):

```text
Morning brief: my calendar today, any urgent unread email (just a list, no replies),
and anything due in my shared Drive docs. Keep it under 150 words.
```

One prompt, your whole morning context.

### Step 6 — Connectors vs Custom GPT Actions vs MCP

- **Connectors** — click-to-enable, for *your* apps in the ChatGPT app (this lesson).
- **Custom GPT Actions** (Track A1) — give a Custom GPT one specific API to call.
- **MCP in Codex** (Track E) — the developer-grade, universal path in the CLI.

---

## 🔒 Connector safety

| Habit | Why |
|-------|-----|
| Enable only what you use | Fewer places ChatGPT can reach |
| Review scope at sign-in | You approve access |
| Read-only where possible | Lower blast radius |
| Draft, never auto-send | You control what goes out |
| Disconnect stale connectors | Clean, minimal setup |

---

## ✅ Checkpoint

- [ ] You connected at least one connector.
- [ ] You ran read-only queries against it.
- [ ] You had ChatGPT **draft** (not send) something and approved it.
- [ ] You composed a connector with another feature (data analysis, etc.).

---

## 🎯 Homework

Build a "morning brief" prompt across the connectors you use, keep it read-only, and save it. Then draft one real email and send it yourself after reviewing.

---

## 💡 Key takeaways

- **Connectors** link ChatGPT to your own apps (Drive, Gmail, Calendar…) — OAuth, no install.
- **Read first, draft don't auto-send, least privilege** — the same safety as developer MCP.
- Connectors (app) vs Custom GPT Actions vs MCP (Codex) are three distinct surfaces — pick by the job.

🌐 [Polski](../../pl/track-f/02-konektory-i-aplikacje.md) · [← Prev](01-deep-research.md) · [Track index](../README.md) · [Next: Image generation →](03-image-generation.md)
