# E6 — Tools & MCP at Scale: Safety & Management

⏱️ **15 minutes** · Track: 🅴 Tools & MCP · Needs: the servers from E2–E5 added

🌐 [Polski](../../pl/track-e/06-mcp-bezpieczenstwo.md) · [← Prev](05-build-your-own-mcp-server.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (5 min)

Once you have several MCP servers in the Gemini CLI — GitHub, Atlassian, Azure, your own — plus the built-in file/shell tools, the challenge shifts from *connecting* to **running it all safely**. Three principles carry everything:

1. **Least privilege.** Give each server the *narrowest* access that still does the job. Read-only beats read-write; one repo/site/subscription beats "everything."
2. **Human in the loop.** The CLI asks before actions that change or send things — keep that on for anything that writes, deletes, deploys, or messages people. (Avoid blanket "auto-approve everything" modes while learning.)
3. **Know what runs and where.** Every server is either a program on your PC (local) or an authorized link (remote). Only keep ones you understand and trust.

### How auth differs by server type

| Type | Auth | Where the secret lives |
|------|------|------------------------|
| **Remote, OAuth** (Atlassian, GitHub) | Sign-in; you approve scopes | Held by the provider |
| **Local, reuses a session** (Azure) | Your existing `az login` | Your machine's CLI session |
| **Local with a token** (some servers) | A token you set in config | Your `settings.json` — treat like a password |
| **Your own server** | Runs as *you* | Your OS permissions |

Safest default: **OAuth and session-based servers** — no long-lived secret in a text file.

---

## 🛠️ Practice (8 min)

### Step 1 — Audit what's connected

```text
/mcp
```
```text
/tools
```

List every MCP server and the built-in tools. Note for each: *what can it reach, and can it write?*

### Step 2 — Tighten each to least privilege

For every server, ask "what's the smallest scope that still works?":
- GitHub token with unused write access → downgrade to read-only.
- Filesystem server pointed at your home folder → point it at **one** project folder.
- A server for something you no longer touch → **remove** it.

### Step 3 — Remove what you don't use

Fewer servers = fewer risks and less confusion for Gemini. Remove stale entries (`gemini mcp remove <name>`, or delete from `settings.json`) and restart.

### Step 4 — Keep secrets out of plain text

If a server needs a token:
- Never commit `settings.json` with a token to git, or paste it into a chat.
- Prefer servers that use **OAuth** or a **CLI session** over pasted tokens.
- Rotate a token immediately if it leaks.

### Step 5 — Set your approval discipline

Decide your rule and keep it:

```text
For any tool that creates, edits, deletes, deploys, or sends anything,
show me exactly what you'll do and wait for my explicit "yes" first.
```

Say this at the start of sessions where Gemini has write-capable tools. Avoid turning on modes that auto-run everything until you fully trust the setup.

### Step 6 — Troubleshoot calmly

If a server won't load:
- **Restart** the CLI (config changes need it).
- Check the JSON is valid (a stray comma breaks the file).
- Confirm the command works alone in a terminal (`npx ...` / `python my_server.py`).
- For remote servers, re-run the OAuth sign-in.

---

## 🔒 Safety checklist

| Check | Why |
|-------|-----|
| Least privilege per server? | Smallest blast radius |
| Read-only where you can be? | Can't break what it can't change |
| Human approval on all writes? | You stay in control |
| Any secrets in plain-text config? | Move to OAuth/session if possible |
| Removed servers you don't use? | Fewer moving parts |
| Trust every server's source? | It runs with real access |
| Config kept out of git/chats? | Don't leak tokens |

---

## ✅ Checkpoint

- [ ] You audited every server (`/mcp`) and the built-in tools (`/tools`).
- [ ] You tightened at least one to least privilege and removed one you don't use.
- [ ] No long-lived secret sits in a plain-text config (or you know exactly which does and why).
- [ ] You have an explicit approval rule and avoid blanket auto-run.

---

## 🎯 Homework

Write your personal "tools policy": which servers you keep, their scope, read vs write, and your approval rule. Apply it — remove, downgrade, or re-scope anything that doesn't fit. Revisit monthly.

---

## 💡 Key takeaways

- Run tools safely with **least privilege**, **human-in-the-loop** on writes, and **knowing what runs where**.
- Prefer **OAuth / session-based** servers over pasted tokens; keep `settings.json` out of git and chats.
- **Audit and prune** regularly, and don't enable blanket auto-approve until you fully trust the setup.

🌐 [Polski](../../pl/track-e/06-mcp-bezpieczenstwo.md) · [← Prev](05-build-your-own-mcp-server.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
