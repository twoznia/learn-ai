# E4 — Azure MCP

⏱️ **15 minutes** · Track: 🅴 MCP Mastery · Needs: an Azure account, Node.js + Azure CLI, Claude Desktop

🌐 [Polski](../../pl/track-e/04-azure-mcp.md) · [← Prev](03-atlassian-mcp.md) · [Track index](../README.md) · [Next: Build your own server →](05-build-your-own-mcp-server.md)

---

## 🧠 Theory (4 min)

The **Azure MCP server** lets Claude explore and work with your **Azure cloud resources** — storage accounts, databases, resource groups, Key Vault, logs, and more — through natural language.

Unlike GitHub/Atlassian, Azure MCP is commonly run **locally**: a small server you launch on your PC (via `npx`) that talks to Azure using the credentials you're already signed in with (Azure CLI). So the setup is the **local config** pattern from E1.

Why local + your existing login is nice:
- **No new secret to paste** — it reuses your `az login` session.
- **Your permissions apply** — Claude can only touch what your Azure account already can.

> Package names and commands for Microsoft's Azure MCP server can change. If `@azure/mcp` doesn't launch, check Microsoft's current **"Azure MCP Server"** docs for the exact package/command and swap it into the config below.

---

## 🛠️ Practice (9 min)

### Step 1 — Sign in to Azure locally

Install the Azure CLI if needed, then:

```powershell
az login
```

A browser opens; sign in. This session is what Azure MCP will reuse.

### Step 2 — Register the Azure MCP server

Open the Claude Desktop config:

```powershell
notepad $env:APPDATA\Claude\claude_desktop_config.json
```

Add an Azure entry (keep any existing servers):

```json
{
  "mcpServers": {
    "azure": {
      "command": "npx",
      "args": ["-y", "@azure/mcp@latest", "server", "start"]
    }
  }
}
```

Save, then **fully quit and reopen** Claude Desktop so it launches the server.

### Step 3 — Explore, read-only

Start by looking, never changing:

```text
List my Azure subscriptions, and for the default one, list the resource groups.
```
```text
Show the storage accounts in resource group <name> and their locations.
```

Claude runs Azure tools locally and returns live results — a guided tour of your cloud.

### Step 4 — Ask real questions across services

```text
Which resources in subscription <name> were created most recently? Group them by type.
```
```text
Summarize the containers in storage account <name> and roughly how much each holds.
```

You're querying your cloud in plain English instead of hunting through the portal.

### Step 5 — Be deliberate about changes

Azure actions can cost money or delete data. Rules while learning:

- Keep prompts **read-only** ("list", "show", "summarize").
- Never ask it to delete, scale, or deploy without understanding the exact effect.
- If you do want a change, ask Claude to **explain what it will run and why first**, and confirm the target resource.

```text
I might resize <resource>. First explain exactly what change that is, the risks,
and how to undo it — do NOT make any change yet.
```

---

## 🧩 Useful Azure MCP moves

| Ask for… | You get |
|----------|---------|
| "List subscriptions / resource groups" | A map of your cloud |
| "Show storage accounts / databases in RG X" | Inventory without the portal |
| "What was created recently, by type?" | A quick audit |
| "Explain this resource's config" | Plain-English documentation |
| "Explain a change before doing it" | Safety before action |

> ⚠️ **Blast radius:** Azure changes are real and can cost money or lose data. Read-only by default; understand every write; your `az login` permissions are the hard limit.

---

## ✅ Checkpoint

- [ ] `az login` works and Azure MCP is registered in the config.
- [ ] Claude listed your subscriptions/resource groups after a restart.
- [ ] You ran several read-only queries about real resources.
- [ ] You can explain why you keep Azure prompts read-only while learning.

---

## 🎯 Homework

Give Claude a read-only tour of one subscription: list resource groups, inventory the biggest ones, and have it produce a short plain-English summary of what you're running. Make no changes.

---

## 💡 Key takeaways

- Azure MCP runs **locally** (via `npx`) and reuses your **`az login`** session — no new secret, your permissions apply.
- It's the **local config** pattern from E1: add the server, restart, then query your cloud in plain English.
- Cloud changes are **high-stakes** — stay read-only, and make Claude explain any write before it happens.

🌐 [Polski](../../pl/track-e/04-azure-mcp.md) · [← Prev](03-atlassian-mcp.md) · [Track index](../README.md) · [Next: Build your own server →](05-build-your-own-mcp-server.md)
