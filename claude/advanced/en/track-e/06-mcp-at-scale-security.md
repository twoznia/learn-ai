# E6 — MCP at Scale: Auth, Safety & Management

⏱️ **15 minutes** · Track: 🅴 MCP Mastery · Needs: the servers from E2–E5 connected

🌐 [Polski](../../pl/track-e/06-mcp-bezpieczenstwo.md) · [← Prev](05-build-your-own-mcp-server.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (5 min)

Once you have several MCP servers — GitHub, Atlassian, Azure, your own — the challenge shifts from *connecting* to **running them safely and keeping them tidy**. Three principles carry everything:

1. **Least privilege.** Give each server the *narrowest* access that still does the job. Read-only beats read-write; one repo/site/subscription beats "everything."
2. **Human in the loop.** Claude asks before actions that change or send things. Never disable that reflex for tools that write, delete, deploy, or message people.
3. **Know what runs and where.** Every server is either a program on your PC (local) or an authorized cloud link (remote). Only keep ones you understand and trust.

### How auth differs by server type

| Type | Auth | Where the secret lives |
|------|------|------------------------|
| **Remote connector** (GitHub, Atlassian) | OAuth sign-in; you approve scopes | Held by the provider, not pasted by you |
| **Local, reuses a session** (Azure) | Your existing `az login` | Your machine's CLI session |
| **Local with a token** (some servers) | A token you set in the config | Your config file — treat it like a password |
| **Your own server** | Runs as *you* | Your OS permissions |

The safest default is **OAuth connectors and session-based local servers** — no long-lived secret sitting in a text file.

---

## 🛠️ Practice (8 min)

### Step 1 — Audit what's connected

- **Remote:** Claude app → **Settings → Connectors**. List every enabled connector.
- **Local:** open your config and list every `mcpServers` entry.

```powershell
notepad $env:APPDATA\Claude\claude_desktop_config.json
```

Write down, for each: *what can it reach, and can it write?*

### Step 2 — Tighten each to least privilege

For every server, ask "what's the smallest scope that still works?" and fix it:

- GitHub token with write access you don't use → downgrade to read-only.
- Filesystem server pointed at your home folder → point it at **one** project folder.
- A connector for a site you no longer touch → **disconnect** it.

### Step 3 — Remove what you don't use

Fewer servers = fewer risks and less confusion for Claude. Delete stale local entries and disconnect unused connectors. Restart Claude Desktop after editing the config.

### Step 4 — Keep secrets out of plain text

If any local server needs a token:
- Never commit the config to git or paste it into a chat.
- Prefer servers that use **OAuth** or a **CLI session** over ones that need a pasted token.
- Rotate a token immediately if it ever leaks.

### Step 5 — Set your approval discipline

Decide your personal rule and stick to it:

```text
For any tool that creates, edits, deletes, deploys, or sends anything,
show me exactly what you'll do and wait for my explicit "yes" first.
```

Say this at the start of sessions where Claude has write-capable tools. It re-arms the human gate.

### Step 6 — Troubleshoot connections calmly

If a server won't load:
- Fully **quit and reopen** Claude Desktop (config changes need a restart).
- Check the JSON is valid (a stray comma breaks the whole file).
- Confirm the command works alone (`npx ...` / `python my_server.py` in a terminal).
- For remote connectors, re-run the OAuth sign-in.

---

## 🔒 MCP security checklist

| Check | Why |
|-------|-----|
| Least privilege per server? | Smallest blast radius |
| Read-only where you can be? | Can't break what it can't change |
| Human approval on all writes? | You stay in control |
| Any secrets in plain-text config? | Move to OAuth/session if possible |
| Removed servers you don't use? | Fewer moving parts |
| Do I trust every server's source? | It runs with real access |
| Config kept out of git/chats? | Don't leak tokens |

---

## ✅ Checkpoint

- [ ] You audited every connected server (remote and local).
- [ ] You tightened at least one to least privilege and removed at least one you don't use.
- [ ] No long-lived secret sits in a plain-text config (or you know exactly which does and why).
- [ ] You have an explicit approval rule for write-capable tools.

---

## 🎯 Homework

Write your personal "MCP policy" in a note: which servers you keep, their scope, read vs write, and your approval rule. Apply it — disconnect, downgrade, or delete anything that doesn't fit. Revisit it monthly.

---

## 💡 Key takeaways

- Scale MCP safely with **least privilege**, **human-in-the-loop** on writes, and **knowing what runs where**.
- Prefer **OAuth connectors** and **session-based** local servers over pasted tokens; keep configs out of git and chats.
- **Audit and prune** regularly — fewer, tightly-scoped servers are safer and easier for Claude to use well.

🌐 [Polski](../../pl/track-e/06-mcp-bezpieczenstwo.md) · [← Prev](05-build-your-own-mcp-server.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
