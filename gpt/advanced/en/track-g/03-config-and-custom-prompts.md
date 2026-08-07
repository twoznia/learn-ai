# G3 — Config & Custom Prompts

⏱️ **15 minutes** · Track: 🅶 Codex CLI in Depth · Needs: the Codex CLI installed & signed in

🌐 [Polski](../../pl/track-g/03-konfiguracja-i-wlasne-prompty.md) · [← Prev](02-approval-modes-and-sandbox.md) · [Track index](../README.md) · [Next: Safe editing with git →](04-safe-editing-with-git.md)

---

## 🧠 Theory (4 min)

Two features turn Codex from "good" into "yours":

- **Config** — a settings file (`~/.codex/config.toml`) that sets your defaults: which model, the default approval/sandbox level, MCP servers, and more. Set it once and every session starts the way you like.
- **Custom prompts** — reusable instructions you save as files in `~/.codex/prompts/` and call by name. Your personal "recipes" for tasks you do again and again.

Both live in your home `~/.codex/` folder, alongside the global `AGENTS.md` from G1.

> Exact config keys and prompt features evolve. When something doesn't match, check the current Codex docs — the *ideas* here stay the same.

---

## 🛠️ Practice (10 min)

### Step 1 — Open your config

```powershell
notepad $HOME\.codex\config.toml
```

A simple config sets your defaults. For example:

```toml
# Default model and approval behaviour
model = "gpt-5-codex"
approval_policy = "on-request"

# An MCP server (see Track E)
[mcp_servers.my-tools]
command = "python"
args = ["C:/path/to/server.py"]
```

Save, restart Codex, and your defaults are in effect — no flags to remember.

> Don't know the exact key names? Ask Codex: "Show me a minimal `config.toml` that sets my default model and approval mode," then verify against the docs.

### Step 2 — Create a custom prompt

Make the prompts folder and add one:

```powershell
mkdir $HOME\.codex\prompts -Force
notepad $HOME\.codex\prompts\review.md
```

Put a reusable instruction inside:

```markdown
Review the current changes for bugs, unclear names, and missing error
handling. List findings as a short checklist, most important first.
Don't change any code — just report.
```

### Step 3 — Run it by name

In a session, invoke your saved prompt (custom prompts appear as commands):

```text
/review
```

Codex runs your saved recipe. One word replaces a paragraph you'd otherwise retype.

### Step 4 — Build a small library

Add a few you'll reuse:

- `explain.md` — "Explain what this file does in plain language."
- `tests.md` — "Suggest unit tests for the current changes; don't write code yet."
- `commit.md` — "Write a clear, conventional commit message for the staged changes."

### Step 5 — Config vs prompts — which is which?

- **Config** changes *how Codex behaves* (model, approvals, servers).
- **Prompts** are *tasks you reuse* (review, explain, test).

Keep them separate and both stay simple.

---

## 🧩 Your `~/.codex/` folder

| File | Purpose |
|------|---------|
| `config.toml` | Defaults: model, approvals, MCP servers |
| `AGENTS.md` | Your global context/preferences (G1) |
| `prompts/*.md` | Reusable, named task recipes |

---

## ✅ Checkpoint

- [ ] You set at least one default in `config.toml` (e.g. model or approval mode).
- [ ] You created a custom prompt in `~/.codex/prompts/`.
- [ ] You ran it by name in a session.
- [ ] You can explain the difference between config and prompts.

---

## 🎯 Homework

Set your two most-wanted defaults in `config.toml`, then create three custom prompts for tasks you repeat (review, explain, tests). Use one in a real session and refine its wording.

---

## 💡 Key takeaways

- **`config.toml`** sets your defaults — model, approvals, MCP servers — so every session starts your way.
- **Custom prompts** in `~/.codex/prompts/` are reusable, named recipes you call in one word.
- Config controls **behaviour**; prompts are reusable **tasks** — keep them separate and simple.

🌐 [Polski](../../pl/track-g/03-konfiguracja-i-wlasne-prompty.md) · [← Prev](02-approval-modes-and-sandbox.md) · [Track index](../README.md) · [Next: Safe editing with git →](04-safe-editing-with-git.md)
