# F4 — Productivity Connectors (Drive, Gmail, Calendar, Slack, Notion)

⏱️ **15 minutes** · Track: 🅵 Beyond Chat · Needs: a Pro/Max account + at least one account to connect

🌐 [Polski](../../pl/track-f/04-konektory-produktywnosci.md) · [← Prev](03-research-and-web.md) · [Track index](../README.md) · [Next: Memory, styles & workflow →](05-memory-styles-workflow.md)

---

## 🧠 Theory (4 min)

Track E covered developer MCP servers (GitHub, Atlassian, Azure). The **productivity connectors** are the everyday ones — and they're the biggest quality-of-life win on a subscription:

- **Google Drive** — find and read your docs/sheets.
- **Gmail** — search and summarize email (draft replies with approval).
- **Google Calendar** — see your schedule, find free slots.
- **Slack** — catch up on channels, summarize threads.
- **Notion** — search pages, pull notes.

They're **remote connectors**: you enable one and sign in with OAuth — no config file, nothing to install. The same discipline from Track E applies: **least privilege, read first, approve every write.**

> Available connectors depend on your plan and region, and the directory grows over time. Enable them under **Settings → Connectors**.

---

## 🛠️ Practice (10 min)

### Step 1 — Connect one you actually use

**Settings → Connectors** → pick one (start with **Google Drive** or **Calendar**) → **Connect** → complete OAuth and approve the access it requests.

> Approve only the scope you need. You can disconnect any connector later.

### Step 2 — Read-only wins first

Try safe, high-value questions:

```text
Find my "Q3 plan" doc in Drive and summarize its top 3 priorities.
```
```text
What's on my calendar tomorrow, and where are the gaps longer than 45 minutes?
```
```text
Summarize the last 20 messages in the #announcements Slack channel.
```

Instant leverage — Claude reaches your tools instead of you copy-pasting.

### Step 3 — Draft, don't auto-send

For anything that leaves your hands, keep a human gate:

```text
Draft a reply to the latest email from <name> confirming the meeting.
Show me the draft — do NOT send it.
```

Claude writes it; **you** send it. Never let it message people without your review.

### Step 4 — Combine connectors + other features

The magic is composing:

```text
Find this week's meeting notes in Drive, then draft a short Slack update summarizing
decisions and owners. Show me the update before I post it.
```

Or with the analysis tool (F2):

```text
Pull the "Sales" sheet from Drive and compute totals per region with a chart.
```

### Step 5 — Turn recurring chores into one prompt

Save prompts you'll reuse (Track A's library):

```text
Morning brief: my calendar today, any urgent unread email (just a list, no replies),
and unread #team Slack highlights. Keep it under 150 words.
```

One prompt, your whole morning context.

---

## 🔒 Connector safety

| Habit | Why |
|-------|-----|
| Enable only what you use | Fewer places Claude can reach |
| Review scope at sign-in | You approve access |
| Read-only where possible | Lower blast radius |
| Draft, never auto-send | You control what goes out |
| Disconnect stale connectors | Clean, minimal setup |

---

## 🧩 High-value moves

| Ask for… | You get |
|----------|---------|
| "Find + summarize my Drive doc" | No hunting through folders |
| "My calendar today + free slots" | Instant schedule view |
| "Summarize this Slack channel/thread" | Catch up in seconds |
| "Draft an email reply (don't send)" | A reviewed draft |
| "Morning brief across my tools" | One-prompt daily context |

---

## ✅ Checkpoint

- [ ] You connected at least one productivity connector.
- [ ] You ran read-only queries against it.
- [ ] You had Claude **draft** (not send) something, and you approved it.
- [ ] You composed a connector with another feature (analysis, Slack, etc.).

---

## 🎯 Homework

Build your own "morning brief" prompt across the connectors you use, keep it read-only, and save it for reuse. Then draft one real message (email or Slack) and send it yourself after reviewing.

---

## 💡 Key takeaways

- **Productivity connectors** (Drive, Gmail, Calendar, Slack, Notion) plug Claude into daily work — OAuth, no install.
- **Read first, draft don't auto-send, least privilege** — the same safety discipline as developer MCP.
- The payoff is **composing** them into one-prompt routines like a morning brief.

🌐 [Polski](../../pl/track-f/04-konektory-produktywnosci.md) · [← Prev](03-research-and-web.md) · [Track index](../README.md) · [Next: Memory, styles & workflow →](05-memory-styles-workflow.md)
