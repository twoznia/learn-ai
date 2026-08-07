# E3 — Atlassian with the Gemini CLI (Jira & Confluence)

⏱️ **15 minutes** · Track: 🅴 Tools & MCP · Needs: an Atlassian account, the Gemini CLI

🌐 [Polski](../../pl/track-e/03-atlassian-mcp.md) · [← Prev](02-github-mcp.md) · [Track index](../README.md) · [Next: Azure with Gemini →](04-azure-mcp.md)

---

## 🧠 Theory (4 min)

The **Atlassian MCP server** connects Gemini to **Jira** (issues, boards, sprints) and **Confluence** (pages, docs). Atlassian publishes a remote MCP server you add to the Gemini CLI and authorize with OAuth.

What it unlocks:

- **Jira** — find and summarize issues, create tickets, move them, comment.
- **Confluence** — search pages, read docs, draft new pages from your notes.

Same discipline as GitHub: **read first, write with approval, scope tightly.** The difference is the *domain* — project tickets and team docs instead of code.

> Atlassian's remote MCP server and its exact URL are provided by Atlassian and may change. Check the current **"Atlassian Remote MCP Server"** docs for the endpoint, then add it to the Gemini CLI.

---

## 🛠️ Practice (9 min)

### Step 1 — Add the Atlassian server

Add Atlassian's MCP server to the CLI (use the current URL/command from Atlassian's docs):

```powershell
gemini mcp add atlassian -- <command or URL from Atlassian's docs>
```

Complete the OAuth sign-in it prompts for; approve access to your Jira/Confluence site.

> You can also add it under `mcpServers` in `.gemini/settings.json`. Run `gemini mcp --help` for the remote-server (URL) options.

### Step 2 — Confirm and read Jira

```text
/mcp
```

Then start read-only:

```text
Show the open Jira issues assigned to me, newest first, with status and priority.
```
```text
Summarize the current sprint for project <KEY>: done, in progress, and blocked.
```

Gemini pulls live issues and gives you a stand-up-ready summary.

### Step 3 — Create a Jira ticket (with approval)

```text
Create a Jira task in project <KEY>: "Update onboarding checklist for Windows",
priority Medium, with a 3-item description. Show the draft and wait for my OK.
```

Gemini drafts it, **asks first**, then files it and returns the key/link.

### Step 4 — Search and use Confluence

```text
Search Confluence for our "Release process" page and summarize the steps as a checklist.
```

Then compose from it:

```text
Draft a new Confluence page "Release process — quick reference" from that checklist.
Show me the draft before creating anything.
```

### Step 5 — Cross-tool workflow

```text
For project <KEY>, list issues resolved this week, then draft a short Confluence
"Weekly update" page summarizing them. Ask before creating the page.
```

A real reporting task, end to end, in the terminal.

---

## 🧩 Useful Atlassian moves

| Ask for… | You get |
|----------|---------|
| "My open Jira issues" / "sprint status" | Instant triage / stand-up notes |
| "Create a Jira task (ask first)" | Drafted, approved, filed |
| "Search Confluence for <topic>" | The right page, summarized |
| "Draft a Confluence page from these notes" | A clean doc, on approval |
| "Weekly update from resolved issues" | An auto-drafted report |

> ⚠️ **Scope:** connect only the site you need, prefer read while learning, and approve every write.

---

## ✅ Checkpoint

- [ ] You added the Atlassian MCP server and saw it under `/mcp`.
- [ ] You summarized real Jira issues or a sprint.
- [ ] You created a Jira ticket or Confluence page **after** approving the draft.
- [ ] You ran one workflow spanning Jira **and** Confluence.

---

## 🎯 Homework

Use Atlassian for a real weekly chore: pull your open issues, draft one ticket you keep meaning to file (with approval), and generate a short status page from this week's resolved work.

---

## 💡 Key takeaways

- The **Atlassian MCP server** connects the Gemini CLI to **Jira** and **Confluence** — add it and authorize with OAuth.
- Same discipline as GitHub: **read first, write with approval, scope to one site**.
- The payoff is **cross-tool workflows** — resolved Jira issues → a drafted Confluence update.

🌐 [Polski](../../pl/track-e/03-atlassian-mcp.md) · [← Prev](02-github-mcp.md) · [Track index](../README.md) · [Next: Azure with Gemini →](04-azure-mcp.md)
