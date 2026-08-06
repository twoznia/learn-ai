# E2 — GitHub MCP

⏱️ **15 minutes** · Track: 🅴 MCP Mastery · Needs: a GitHub account, Claude Desktop or Claude.ai

🌐 [Polski](../../pl/track-e/02-github-mcp.md) · [← Prev](01-mcp-explained.md) · [Track index](../README.md) · [Next: Atlassian MCP →](03-atlassian-mcp.md)

---

## 🧠 Theory (4 min)

The **GitHub MCP server** lets Claude work with your repositories the way a teammate would: read code, browse issues and pull requests, create issues, open PRs, and check CI — all through tool calls you approve.

Two ways to connect (use whichever your setup offers):

- **Remote connector (easiest)** — enable GitHub in **Settings → Connectors** and sign in with OAuth. Hosted, nothing to install.
- **Custom / local** — point a client at GitHub's MCP server URL (`https://api.githubcopilot.com/mcp/`) with a GitHub token, or run GitHub's server locally. Useful in Claude Code and for fine-grained scopes.

> Exact connector names and URLs evolve — if a screen looks different, check GitHub's current **"GitHub MCP server"** docs for the latest endpoint and setup.

**Scopes matter most here.** A read-only token lets Claude *look*; a read-write token lets it *change* things (push, open PRs). Start read-only while you learn.

---

## 🛠️ Practice (9 min)

### Step 1 — Connect GitHub

**Option A — Connector (recommended):**
1. Claude app → **Settings → Connectors** → find **GitHub** → **Connect**.
2. Complete the OAuth sign-in; approve the access it requests.

**Option B — Custom connector by URL (Claude apps that support it, or Claude Code):**
- Server URL: `https://api.githubcopilot.com/mcp/`
- Authorize with your GitHub account / token when prompted.

### Step 2 — Read before you write

Start with safe, read-only questions so you can see the tools working:

```text
List the 5 most recently updated repositories on my GitHub account.
```
```text
In my repo <owner/repo>, show the 5 newest open issues with their labels.
```

Watch Claude call GitHub tools and return live data — no copy-paste.

### Step 3 — Investigate a pull request

```text
In <owner/repo>, summarize open pull request #<N>: what it changes, and any
review comments or failing checks. Flag anything risky.
```

Claude reads the PR, its diff, and CI status through the server and gives you a briefing.

### Step 4 — Create an issue (your first write action)

```text
Create an issue in <owner/repo> titled "Docs: add setup steps for Windows"
with a short checklist body. Show me the draft first and wait for my OK.
```

Claude drafts it, **asks before creating**, and — once you approve — files it and returns the link. That approval step is your safety net.

### Step 5 — A real mini-workflow

Combine reading and writing:

```text
Find issues in <owner/repo> labeled "good first issue". Pick one, and draft a
step-by-step plan to fix it as a comment on that issue. Ask before posting.
```

You've gone from browsing to acting — with a human gate on every change.

---

## 🧩 Useful GitHub MCP moves

| Ask for… | You get |
|----------|---------|
| "List recent issues / PRs in repo X" | Live triage without leaving chat |
| "Summarize PR #N + its checks" | A review briefing |
| "Create an issue / comment (ask first)" | Drafted, approved, filed |
| "What changed in the last 5 commits?" | A plain-English changelog |
| "Search code for `<term>` in repo X" | Located references |

> ⚠️ **Scope check:** if Claude can push code or open PRs, it's using a **write** token. Only grant that when you need it, and keep approving each action.

---

## ✅ Checkpoint

- [ ] GitHub is connected (connector or URL).
- [ ] You ran read-only queries against a real repo.
- [ ] Claude created an issue or comment **after** asking your approval.
- [ ] You can state whether your connection is read-only or read-write.

---

## 🎯 Homework

Pick one real repo you own. Use GitHub MCP to triage its open issues, summarize one PR, and draft (with approval) one issue that captures a task you keep forgetting. Note which actions needed write access.

---

## 💡 Key takeaways

- GitHub MCP turns Claude into a repo-aware teammate: read issues/PRs/code, create issues/PRs — via approved tool calls.
- Connect via a **remote connector** (OAuth, easiest) or a **URL/token** for finer control.
- **Scope carefully**: read-only to learn; grant write only when needed, and approve every change.

🌐 [Polski](../../pl/track-e/02-github-mcp.md) · [← Prev](01-mcp-explained.md) · [Track index](../README.md) · [Next: Atlassian MCP →](03-atlassian-mcp.md)
