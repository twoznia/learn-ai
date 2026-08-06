# G4 — Hooks

⏱️ **15 minutes** · Track: 🅶 Claude Code in Depth · Needs: Claude Code installed & logged in

🌐 [Polski](../../pl/track-g/04-haki.md) · [← Prev](03-subagents.md) · [Track index](../README.md) · [Next: MCP in Claude Code →](05-mcp-in-claude-code.md)

---

## 🧠 Theory (5 min)

**Hooks** let you run **your own commands automatically** at specific moments in a Claude Code session — the harness runs them, not Claude. They're how you enforce rules and automate chores that should happen *every time*, without asking.

Common events you can hook:

| Event | Fires… | Great for |
|-------|--------|-----------|
| **PreToolUse** | Before Claude uses a tool | Blocking risky actions, guardrails |
| **PostToolUse** | After a tool runs | Auto-formatting a file after an edit |
| **UserPromptSubmit** | When you send a message | Injecting context, logging |
| **Stop** | When Claude finishes responding | Notifications, running tests |

The difference from CLAUDE.md or commands: those *ask* Claude to do things (it may or may not). A **hook always runs** — it's deterministic. Use hooks for anything that must happen without fail (format on save, block edits to protected files, run a check).

---

## 🛠️ Practice (9 min)

### Step 1 — Find your settings file

Hooks live in Claude Code **settings** (`.claude/settings.json` in the project, or your user settings). Create/open the project one:

```powershell
mkdir .claude
notepad .claude\settings.json
```

### Step 2 — Add a simple "notify when done" hook

Paste a minimal hooks block (this runs a command when Claude finishes):

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          { "type": "command", "command": "echo Claude finished a turn >> claude-activity.log" }
        ]
      }
    ]
  }
}
```

Save, restart the session, and do anything. Check `claude-activity.log` — a line was appended **automatically** when Claude finished. That's a hook.

### Step 3 — Auto-format after edits (PostToolUse)

A classic use: after Claude edits a file, run your formatter so code is always tidy. The shape (adapt the command to your tools):

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          { "type": "command", "command": "echo formatted >> claude-activity.log" }
        ]
      }
    ]
  }
}
```

Replace the `echo` with your real formatter command (e.g. a Prettier/Black call). Now every edit is auto-formatted — you never ask.

### Step 4 — Add a guardrail (PreToolUse)

A **PreToolUse** hook can inspect an action *before* it runs and block it — e.g. refuse edits to a protected file. Conceptually:

- Match on the tool (an edit).
- Run a small check command.
- If it signals "block," the action is stopped.

This is how you enforce "never touch `secrets.env`" as a hard rule, not a polite request. (Keep your first guardrails simple; test them before trusting them.)

### Step 5 — Keep hooks safe and simple

- Hooks run **real commands on your machine** — only add ones you understand.
- Start with harmless hooks (logging) and verify they fire before adding ones that block or change things.
- Keep commands fast; a slow hook slows every turn.

### Step 6 — Decide what deserves a hook

Ask: *does this need to happen every time, guaranteed?* If yes → hook. If it's occasional or judgment-based → a slash command or just asking Claude is better.

---

## 🧩 Hook or not?

| Need | Use |
|------|-----|
| Format every file after edit | **PostToolUse hook** |
| Block edits to a protected file | **PreToolUse hook** |
| Log/notify when a turn ends | **Stop hook** |
| A review you run sometimes | Slash command (G2) |
| A one-off task | Just ask Claude |

> ⚠️ **Hooks execute commands automatically.** Treat the settings file like code you trust: no untrusted commands, test before relying on a blocking hook, and keep the file out of public places if it references anything sensitive.

---

## ✅ Checkpoint

- [ ] You added a `Stop` hook and confirmed it fired (log line appeared).
- [ ] You understand PreToolUse / PostToolUse / UserPromptSubmit / Stop.
- [ ] You can explain why a hook is deterministic vs asking Claude.
- [ ] You know the safety rule: hooks run real commands — only trusted ones.

---

## 🎯 Homework

Add one genuinely useful hook: auto-format after edits, or a log/notify on Stop. Verify it fires reliably. Then write down one guardrail you'd want as a PreToolUse hook (e.g. protecting a file) — implement it only once you're confident.

---

## 💡 Key takeaways

- **Hooks** run **your commands automatically** on session events (PreToolUse, PostToolUse, UserPromptSubmit, Stop) — deterministic, unlike asking Claude.
- Great for **format-on-edit**, **guardrails**, and **notifications** that must happen every time.
- They execute **real commands** — add only trusted ones, start simple, and test before relying on blocking hooks.

🌐 [Polski](../../pl/track-g/04-haki.md) · [← Prev](03-subagents.md) · [Track index](../README.md) · [Next: MCP in Claude Code →](05-mcp-in-claude-code.md)
