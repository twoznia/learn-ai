# F3 — Connected Apps & Google Workspace

⏱️ **15 minutes** · Track: 🅵 Beyond Chat · Needs: the Gemini app (Pro recommended), a Google account

🌐 [Polski](../../pl/track-f/03-polaczone-aplikacje.md) · [← Prev](02-data-analysis.md) · [Track index](../README.md) · [Next: Create with Gemini →](04-create-with-gemini.md)

---

## 🧠 Theory (4 min)

Track E connected developer tools via MCP in the **CLI**. In the **Gemini app**, the everyday integrations are **extensions / connected apps** — and because you're already in Google's world, they're the biggest quality-of-life win:

- **Google Workspace** — Gmail, Drive, Docs, Calendar (find, summarize, draft).
- **Google Maps** — places, directions, trip help.
- **YouTube** — summarize or find videos.
- Plus other extensions as they roll out.

You enable them in the app and they use your Google sign-in — no config, no install. Same discipline as MCP: **read first, draft don't auto-send, least privilege.**

> Available extensions/connected apps depend on your plan and region and change over time. Enable them in the app's **tools / extensions / connected apps** menu.

---

## 🛠️ Practice (10 min)

### Step 1 — Turn on the ones you use

In the Gemini app, open the **extensions / connected apps** menu and enable **Google Workspace** (and Maps/YouTube if useful). Approve the access it requests.

### Step 2 — Read-only wins first

```text
Find my "Q3 plan" doc in Drive and summarize its top 3 priorities.
```
```text
What's on my calendar tomorrow, and where are the gaps longer than 45 minutes?
```
```text
Summarize the last email thread from <name> and list any action items.
```

Instant leverage — Gemini reaches your Google apps instead of you copy-pasting.

### Step 3 — Draft, don't auto-send

For anything that leaves your hands, keep a human gate:

```text
Draft a reply to the latest email from <name> confirming the meeting.
Show me the draft — do NOT send it.
```

Gemini writes it; **you** send it.

### Step 4 — Combine apps + other features

```text
Find this week's meeting notes in Drive, then draft a short summary email
of decisions and owners. Show me the draft before I send.
```

Or with data analysis (F2):

```text
Pull the "Sales" sheet from Drive and compute totals per region with a chart.
```

### Step 5 — Turn recurring chores into one prompt

Save prompts you'll reuse (Track A2):

```text
Morning brief: my calendar today, any urgent unread email (just a list, no replies),
and anything due in Docs I'm sharing. Keep it under 150 words.
```

One prompt, your whole morning context.

### Step 6 — Gemini right inside Workspace

Don't forget the side panel **inside** Gmail/Docs/Sheets. Same power, in the app where you already work — "summarize this thread," "help me write this section."

---

## 🔒 Connected-app safety

| Habit | Why |
|-------|-----|
| Enable only what you use | Fewer places Gemini can reach |
| Review access when enabling | You approve the scope |
| Read-only where possible | Lower blast radius |
| Draft, never auto-send | You control what goes out |
| Turn off apps you've stopped using | Clean, minimal setup |

---

## 🧩 High-value moves

| Ask for… | You get |
|----------|---------|
| "Find + summarize my Drive doc" | No hunting through folders |
| "My calendar today + free slots" | Instant schedule view |
| "Summarize this email thread" | Catch up in seconds |
| "Draft an email reply (don't send)" | A reviewed draft |
| "Morning brief across my apps" | One-prompt daily context |

---

## ✅ Checkpoint

- [ ] You enabled at least one connected app (Workspace).
- [ ] You ran read-only queries against it.
- [ ] You had Gemini **draft** (not send) something and approved it.
- [ ] You composed a connected app with another feature (data analysis, etc.).

---

## 🎯 Homework

Build a "morning brief" prompt across the Google apps you use, keep it read-only, and save it. Then draft one real email and send it yourself after reviewing.

---

## 💡 Key takeaways

- **Connected apps / extensions** plug Gemini into Gmail, Drive, Calendar, Maps, YouTube — using your Google sign-in, no install.
- **Read first, draft don't auto-send, least privilege** — the same safety as MCP.
- Compose them into **one-prompt routines**, and remember Gemini lives **inside** Workspace too.

🌐 [Polski](../../pl/track-f/03-polaczone-aplikacje.md) · [← Prev](02-data-analysis.md) · [Track index](../README.md) · [Next: Create with Gemini →](04-create-with-gemini.md)
