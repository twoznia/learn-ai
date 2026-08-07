# E2 — GitHub with the Gemini CLI

⏱️ **15 minutes** · Track: 🅴 Tools & MCP · Needs: a GitHub account, the Gemini CLI

🌐 [Polski](../../pl/track-e/02-github-mcp.md) · [← Prev](01-tools-and-mcp-explained.md) · [Track index](../README.md) · [Next: Atlassian with Gemini →](03-atlassian-mcp.md)

---

## 🧠 Theory (4 min)

The **GitHub MCP server** lets Gemini work with your repositories like a teammate: read code, browse issues and pull requests, create issues, open PRs, and check CI — through tool calls you approve, right in the Gemini CLI.

You add it as an MCP server. GitHub publishes an official MCP server (endpoint `https://api.githubcopilot.com/mcp/`), and there are local options too. Either way, the CLI becomes GitHub-aware.

> Exact server URLs and setup evolve — check GitHub's current **"GitHub MCP server"** docs for the latest endpoint and auth. **Scopes matter most:** a read-only token lets Gemini *look*; a write token lets it *change* things. Start read-only while you learn.

---

## 🛠️ Practice (9 min)

### Step 1 — Add the GitHub server

Use the CLI's `mcp add`. The general shape (adapt to the current GitHub server + your token):

```powershell
gemini mcp add github -- npx -y @modelcontextprotocol/server-github
```

You'll provide a GitHub token when prompted (or via the server's documented setting). Prefer a **read-only** token to start.

> Prefer editing config? Add the same server under `mcpServers` in `.gemini/settings.json` (see E1). Run `gemini mcp --help` for current options.

### Step 2 — Confirm it's connected

```text
/mcp
```

You should see `github` and its tools. Restart the CLI if it doesn't appear.

### Step 3 — Read before you write

Start with safe, read-only questions:

```text
List the 5 most recently updated repositories on my GitHub account.
```
```text
In my repo <owner/repo>, show the 5 newest open issues with their labels.
```

Watch Gemini call GitHub tools and return live data — no copy-paste.

### Step 4 — Investigate a pull request

```text
In <owner/repo>, summarize open pull request #<N>: what it changes, and any
review comments or failing checks. Flag anything risky.
```

### Step 5 — Create an issue (your first write action)

```text
Create an issue in <owner/repo> titled "Docs: add Windows setup steps"
with a short checklist body. Show me the draft first and wait for my OK.
```

Gemini drafts it, **asks before creating**, and — once you approve — files it and returns the link. That approval step is your safety net.

### Step 6 — A real mini-workflow

Combine your files with GitHub — the CLI can do both:

```text
Read the TODO comments in this project, then draft a GitHub issue capturing
the follow-up work. Ask before creating it.
```

Local code understanding + a real write action, gated by your approval.

---

## 🧩 Useful GitHub moves

| Ask for… | You get |
|----------|---------|
| "List recent issues / PRs in repo X" | Live triage in the terminal |
| "Summarize PR #N + its checks" | A review briefing |
| "Create an issue / comment (ask first)" | Drafted, approved, filed |
| "What changed in the last 5 commits?" | A plain-English changelog |
| "From my TODOs, draft an issue" | Files + GitHub in one flow |

> ⚠️ **Scope check:** if Gemini can push or open PRs, it's using a **write** token. Grant that only when needed, and keep approving each action.

---

## ✅ Checkpoint

- [ ] You added the GitHub MCP server and saw it under `/mcp`.
- [ ] You ran read-only queries against a real repo.
- [ ] Gemini created an issue **after** asking your approval.
- [ ] You can state whether your token is read-only or read-write.

---

## 🎯 Homework

Pick one repo you own. Use the Gemini CLI + GitHub to triage its issues, summarize one PR, and draft (with approval) one issue from your code's TODOs. Note which actions needed write access.

---

## 💡 Key takeaways

- The **GitHub MCP server** makes the Gemini CLI repo-aware: read issues/PRs/code, create issues/PRs — via approved tool calls.
- Add it with `gemini mcp add` (or `settings.json`); check GitHub's current docs for the endpoint/auth.
- **Scope carefully**: read-only to learn; grant write only when needed, and approve every change.

🌐 [Polski](../../pl/track-e/02-github-mcp.md) · [← Prev](01-tools-and-mcp-explained.md) · [Track index](../README.md) · [Next: Atlassian with Gemini →](03-atlassian-mcp.md)
