# G2 — Slash Commands (Built-in & Custom)

⏱️ **15 minutes** · Track: 🅶 Claude Code in Depth · Needs: Claude Code installed & logged in

🌐 [Polski](../../pl/track-g/02-komendy-ukosnik.md) · [← Prev](01-claude-md-and-plan-mode.md) · [Track index](../README.md) · [Next: Subagents →](03-subagents.md)

---

## 🧠 Theory (4 min)

**Slash commands** are shortcuts you type in Claude Code, starting with `/`. Two kinds:

- **Built-in** — commands that ship with Claude Code: manage the session, models, MCP, memory, and more.
- **Custom** — commands *you* create. A custom command is just a **Markdown file**; its contents become a reusable prompt you fire with `/<name>`. This is how you turn a workflow you repeat ("review this code," "write a commit message," "explain this file") into one keystroke.

Custom commands are the fastest way to standardize how you work with Claude Code.

---

## 🛠️ Practice (10 min)

### Step 1 — Explore the built-ins

In Claude Code, type `/` and read the list. Useful ones to know:

| Command | Does |
|---------|------|
| `/help` | List available commands |
| `/init` | Generate a project `CLAUDE.md` (G1) |
| `/clear` | Start a fresh context (like a new chat) |
| `/model` | Switch model (Sonnet/Opus…) |
| `/agents` | Manage subagents (G3) |
| `/mcp` | Manage MCP servers (G5) |

Try `/clear` between unrelated tasks — same "one task = one context" habit from D2, and it saves tokens.

### Step 2 — Create your first custom command

Custom commands live in a `.claude/commands/` folder in your project. Create one:

```powershell
mkdir .claude\commands
notepad .claude\commands\explain.md
```

Put a reusable prompt inside:

```markdown
Explain the file I mention in plain English for a beginner:
what it does, its main parts, and anything risky. Keep it under 200 words.
```

Save. Now in Claude Code:

```text
/explain
```

Your prompt runs — no retyping.

### Step 3 — Pass arguments

Make commands flexible with `$ARGUMENTS`. Create `.claude/commands/commit.md`:

```markdown
Write a clear git commit message for the current staged changes.
If I gave extra context, use it: $ARGUMENTS
Keep the subject under 60 characters; add a short body if needed.
```

Then:

```text
/commit focus on the security fix
```

Claude uses your text where `$ARGUMENTS` sits.

### Step 4 — Build a small command library

Add commands for chores you repeat:

- `.claude/commands/review.md` — "Review my recent changes for bugs and clarity; list findings by severity."
- `.claude/commands/readme.md` — "Draft/update a README for this project from the code."
- `.claude/commands/plan.md` — "Propose a step-by-step plan for the task I describe; don't edit yet."

Each becomes `/review`, `/readme`, `/plan`.

### Step 5 — Personal vs project commands

- **Project commands** (`.claude/commands/` in the repo) ship with the project — great for team conventions.
- **Personal commands** (in your user Claude Code folder) follow *you* across all projects.

Put team workflows in the project; personal helpers in your user folder.

---

## 🧩 Good custom commands

| Command | Turns this chore into one keystroke |
|---------|-------------------------------------|
| `/review` | Reviewing your own changes |
| `/commit` | Writing a good commit message |
| `/explain` | Understanding an unfamiliar file |
| `/plan` | Getting a plan before edits |
| `/readme` | Keeping docs up to date |

> 💡 A command file is just a prompt. If you keep typing the same request, make it a command.

---

## ✅ Checkpoint

- [ ] You explored the built-in commands and used `/clear` between tasks.
- [ ] You created a custom `/explain` command and ran it.
- [ ] You made a command that uses `$ARGUMENTS`.
- [ ] You can explain project vs personal commands.

---

## 🎯 Homework

Turn your three most-repeated Claude Code requests into custom commands. Give one an `$ARGUMENTS` slot. Use them for a day and refine the wording where the output isn't quite right.

---

## 💡 Key takeaways

- **Built-in** slash commands manage the session; `/clear`, `/model`, `/init`, `/agents`, `/mcp` are worth knowing.
- **Custom commands** are Markdown files (`.claude/commands/*.md`) that become `/<name>` — your repeated prompts, one keystroke.
- Use **`$ARGUMENTS`** for flexibility; put team workflows in the project, personal helpers in your user folder.

🌐 [Polski](../../pl/track-g/02-komendy-ukosnik.md) · [← Prev](01-claude-md-and-plan-mode.md) · [Track index](../README.md) · [Next: Subagents →](03-subagents.md)
