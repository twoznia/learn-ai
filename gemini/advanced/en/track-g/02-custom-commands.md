# G2 — Custom Commands (& Built-in Ones)

⏱️ **15 minutes** · Track: 🅶 Gemini CLI in Depth · Needs: the Gemini CLI installed & signed in

🌐 [Polski](../../pl/track-g/02-wlasne-komendy.md) · [← Prev](01-gemini-md-and-context.md) · [Track index](../README.md) · [Next: Built-in tools & approvals →](03-tools-and-approvals.md)

---

## 🧠 Theory (4 min)

**Slash commands** are shortcuts you type in the Gemini CLI, starting with `/`. Two kinds:

- **Built-in** — commands that ship with the CLI to manage the session, memory, tools, and MCP.
- **Custom** — commands *you* create. In the Gemini CLI a custom command is a small **TOML file**; its `prompt` becomes a reusable request you fire with `/<name>`. This turns a workflow you repeat ("review this code," "write a commit message," "explain this file") into one keystroke.

Custom commands are the fastest way to standardize how you work.

---

## 🛠️ Practice (10 min)

### Step 1 — Explore the built-ins

Type `/` and read the list. Worth knowing:

| Command | Does |
|---------|------|
| `/help` | List commands |
| `/init` | Generate a project `GEMINI.md` (G1) |
| `/memory` | Show/refresh/add context (G1) |
| `/tools` | List built-in tools (G3) |
| `/mcp` | List MCP servers (Track E) |
| `/chat` | Save / resume a conversation |
| `/clear` | Clear the screen/context for a fresh start |

Use `/clear` between unrelated tasks — the "one task = one context" habit from D2, which also saves usage.

### Step 2 — Create your first custom command

Custom commands live in a `commands` folder — project (`.gemini/commands/`) or global (`~/.gemini/commands/`). Create one:

```powershell
mkdir .gemini\commands
notepad .gemini\commands\explain.toml
```

Put a `prompt` inside:

```toml
description = "Explain a file in plain English"
prompt = """
Explain the file I mention in plain English for a beginner:
what it does, its main parts, and anything risky. Keep it under 200 words.
"""
```

Save. Now in the CLI:

```text
/explain
```

Your prompt runs — no retyping.

### Step 3 — Pass arguments

Make commands flexible with `{{args}}`. Create `.gemini/commands/commit.toml`:

```toml
description = "Write a commit message"
prompt = """
Write a clear git commit message for the current staged changes.
If I gave extra context, use it: {{args}}
Keep the subject under 60 characters; add a short body if needed.
"""
```

Then:

```text
/commit focus on the security fix
```

Your text lands where `{{args}}` sits.

### Step 4 — Build a small command library

- `.gemini/commands/review.toml` — "Review my recent changes for bugs and clarity; list findings by severity."
- `.gemini/commands/readme.toml` — "Draft/update a README for this project from the code."
- `.gemini/commands/plan.toml` — "Propose a step-by-step plan for the task I describe; don't edit yet."

Each becomes `/review`, `/readme`, `/plan`.

### Step 5 — Namespacing & scope

- **Sub-folders namespace commands:** `.gemini/commands/git/commit.toml` becomes `/git:commit`.
- **Project vs global:** project commands (`.gemini/commands/`) ship with the repo; global ones (`~/.gemini/commands/`) follow you everywhere.

> Command file format and argument syntax can evolve — run `/help` or check the current Gemini CLI docs if a command doesn't load.

---

## 🧩 Good custom commands

| Command | Turns this chore into one keystroke |
|---------|-------------------------------------|
| `/review` | Reviewing your own changes |
| `/commit` | Writing a good commit message |
| `/explain` | Understanding an unfamiliar file |
| `/plan` | Getting a plan before edits |
| `/readme` | Keeping docs up to date |

---

## ✅ Checkpoint

- [ ] You explored built-in commands and used `/clear` between tasks.
- [ ] You created a custom `/explain` command (TOML) and ran it.
- [ ] You made a command that uses `{{args}}`.
- [ ] You can explain project vs global commands and sub-folder namespacing.

---

## 🎯 Homework

Turn your three most-repeated Gemini CLI requests into custom TOML commands. Give one an `{{args}}` slot. Use them for a day and refine the wording where output isn't quite right.

---

## 💡 Key takeaways

- **Built-in** commands manage the session; `/clear`, `/memory`, `/tools`, `/mcp`, `/chat` are worth knowing.
- **Custom commands** are TOML files (`.gemini/commands/*.toml`) whose `prompt` becomes `/<name>` — your repeated prompts, one keystroke.
- Use **`{{args}}`**, **sub-folder namespacing**, and **project vs global** scope to organize them.

🌐 [Polski](../../pl/track-g/02-wlasne-komendy.md) · [← Prev](01-gemini-md-and-context.md) · [Track index](../README.md) · [Next: Built-in tools & approvals →](03-tools-and-approvals.md)
