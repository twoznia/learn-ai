# E4 — Azure with the Codex CLI

⏱️ **15 minutes** · Track: 🅴 Tools & MCP · Needs: an Azure account, Node.js + Azure CLI, the Codex CLI

🌐 [Polski](../../pl/track-e/04-azure-mcp.md) · [← Prev](03-atlassian-mcp.md) · [Track index](../README.md) · [Next: Build your own server →](05-build-your-own-mcp-server.md)

---

## 🧠 Theory (4 min)

The **Azure MCP server** lets GPT explore and work with your **Azure cloud resources** — storage, databases, resource groups, Key Vault, logs — through natural language.

Azure MCP is commonly run **locally**: a small server launched via `npx` that talks to Azure using the credentials you're already signed in with (Azure CLI). So it's the **local server** pattern from E1.

Why local + your existing login is nice:
- **No new secret to paste** — it reuses your `az login` session.
- **Your permissions apply** — GPT can only touch what your Azure account already can.

> Package names and commands for Microsoft's Azure MCP server can change. If `@azure/mcp` doesn't launch, check Microsoft's current **"Azure MCP Server"** docs for the exact package/command and swap it in.

---

## 🛠️ Practice (9 min)

### Step 1 — Sign in to Azure locally

Install the Azure CLI if needed, then:

```powershell
az login
```

A browser opens; sign in. This session is what Azure MCP will reuse.

### Step 2 — Add the Azure MCP server

Add it to the Codex CLI:

```powershell
codex mcp add azure -- npx -y @azure/mcp@latest server start
```

> Or add the same under `[mcp_servers.azure]` in `~/.codex/config.toml`. Restart Codex so it launches the server.

### Step 3 — Confirm and explore, read-only

```text
/mcp
```

Then look, never change:

```text
List my Azure subscriptions, and for the default one, list the resource groups.
```
```text
Show the storage accounts in resource group <name> and their locations.
```

GPT runs Azure tools locally and returns live results — a guided tour of your cloud.

### Step 4 — Ask real questions

```text
Which resources in subscription <name> were created most recently? Group them by type.
```
```text
Summarize the containers in storage account <name> and roughly how much each holds.
```

You're querying your cloud in plain English instead of hunting through the portal.

### Step 5 — Be deliberate about changes

Azure actions can cost money or delete data. While learning:
- Keep prompts **read-only** ("list", "show", "summarize").
- Never delete/scale/deploy without understanding the exact effect.
- For any change, make GPT **explain what it will run and why first**, and confirm the target.

```text
I might resize <resource>. First explain exactly what change that is, the risks,
and how to undo it — do NOT make any change yet.
```

---

## 🧩 Useful Azure moves

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

- [ ] `az login` works and the Azure MCP server is added to Codex.
- [ ] GPT listed your subscriptions/resource groups.
- [ ] You ran several read-only queries about real resources.
- [ ] You can explain why you keep Azure prompts read-only while learning.

---

## 🎯 Homework

Give GPT a read-only tour of one subscription: list resource groups, inventory the biggest, and have it produce a short plain-English summary of what you're running. Make no changes.

---

## 💡 Key takeaways

- The **Azure MCP server** runs **locally** and reuses your **`az login`** session — no new secret, your permissions apply.
- Add it to the Codex CLI, then query your cloud in plain English.
- Cloud changes are **high-stakes** — stay read-only, and make GPT explain any write before it happens.

🌐 [Polski](../../pl/track-e/04-azure-mcp.md) · [← Prev](03-atlassian-mcp.md) · [Track index](../README.md) · [Next: Build your own server →](05-build-your-own-mcp-server.md)
