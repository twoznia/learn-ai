# E3 — Atlassian MCP (Jira & Confluence)

⏱️ **15 minutes** · Track: 🅴 MCP Mastery · Needs: an Atlassian account (Jira and/or Confluence)

🌐 [Polski](../../pl/track-e/03-atlassian-mcp.md) · [← Prev](02-github-mcp.md) · [Track index](../README.md) · [Next: Azure MCP →](04-azure-mcp.md)

---

## 🧠 Theory (4 min)

The **Atlassian MCP server** connects Claude to **Jira** (issues, boards, sprints) and **Confluence** (pages, docs). It's usually a **remote connector** — hosted by Atlassian, enabled with OAuth, nothing to install.

What it unlocks:

- **Jira** — find and summarize issues, create tickets, move them across a board, comment.
- **Confluence** — search pages, read docs, draft new pages from your notes.

The pattern is the same as GitHub: **read first, write with approval, scope tightly.** The difference is the *domain* — project tickets and team docs instead of code.

> Atlassian's remote MCP server and its exact connect URL are provided by Atlassian and may change. If you don't see it in **Settings → Connectors**, search Atlassian's current **"Atlassian Remote MCP Server"** docs for the endpoint and enable it as a custom connector.

---

## 🛠️ Practice (9 min)

### Step 1 — Connect Atlassian

1. Claude app → **Settings → Connectors** → find **Atlassian** → **Connect**.
2. Sign in with OAuth; approve access to your Jira/Confluence site.
3. If it's not listed, add it as a **custom connector** using Atlassian's published MCP server URL.

### Step 2 — Read your Jira

Start read-only to see the tools working:

```text
Show me the open Jira issues assigned to me, newest first, with status and priority.
```
```text
Summarize what's in the current sprint for project <KEY>: what's done, in progress, and blocked.
```

Claude pulls live issues and gives you a stand-up-ready summary.

### Step 3 — Create a Jira ticket (with approval)

```text
Create a Jira task in project <KEY>: "Update onboarding checklist for Windows users",
priority Medium, with a 3-item description. Show me the draft and wait for my OK.
```

Claude drafts it, **asks first**, then files it and returns the issue key/link.

### Step 4 — Search and use Confluence

```text
Search Confluence for our "Release process" page and summarize the steps as a checklist.
```

Then compose from it:

```text
Draft a new Confluence page "Release process — quick reference" from that checklist.
Show me the draft before creating anything.
```

Read from one page, write a cleaner one — with a human gate.

### Step 5 — Cross-tool workflow

Tie Jira and Confluence together:

```text
For project <KEY>, list issues resolved this week, then draft a short Confluence
"Weekly update" page summarizing them. Ask before creating the page.
```

That's a real reporting task done end to end inside chat.

---

## 🧩 Useful Atlassian MCP moves

| Ask for… | You get |
|----------|---------|
| "My open Jira issues" / "sprint status" | Instant triage / stand-up notes |
| "Create a Jira task (ask first)" | Drafted, approved, filed |
| "Search Confluence for <topic>" | The right page, summarized |
| "Draft a Confluence page from these notes" | A clean doc, on approval |
| "Weekly update from resolved issues" | An auto-drafted report |

> ⚠️ **Scope:** connect only the Jira/Confluence site you need, prefer read while learning, and keep approving writes (new tickets, page edits).

---

## ✅ Checkpoint

- [ ] Atlassian is connected (connector or custom URL).
- [ ] You summarized real Jira issues or a sprint.
- [ ] You created a Jira ticket or Confluence page **after** approving the draft.
- [ ] You ran one workflow spanning Jira **and** Confluence.

---

## 🎯 Homework

Use Atlassian MCP for a real chore you do weekly: pull your open issues, draft one ticket you keep meaning to file (with approval), and generate a short status page from this week's resolved work.

---

## 💡 Key takeaways

- Atlassian MCP connects Claude to **Jira** (tickets, sprints) and **Confluence** (pages) — usually a remote OAuth connector.
- Same discipline as GitHub: **read first, write with approval, scope to one site**.
- The payoff is **cross-tool workflows** — e.g. resolved Jira issues → a drafted Confluence update.

🌐 [Polski](../../pl/track-e/03-atlassian-mcp.md) · [← Prev](02-github-mcp.md) · [Track index](../README.md) · [Next: Azure MCP →](04-azure-mcp.md)
