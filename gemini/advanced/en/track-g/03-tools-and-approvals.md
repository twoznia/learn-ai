# G3 — Built-in Tools & the Approval Flow

⏱️ **15 minutes** · Track: 🅶 Gemini CLI in Depth · Needs: the Gemini CLI installed & signed in

🌐 [Polski](../../pl/track-g/03-narzedzia-i-zatwierdzenia.md) · [← Prev](02-custom-commands.md) · [Track index](../README.md) · [Next: Checkpointing & undo →](04-checkpointing-and-undo.md)

---

## 🧠 Theory (5 min)

The Gemini CLI is agentic because it has **built-in tools** — it can read and write files, run shell commands, and fetch/search the web. Understanding these tools and, crucially, the **approval flow** is what makes the CLI both powerful and safe.

Typical built-in tools:

| Tool | Does |
|------|------|
| **Read file** | Read a file's contents |
| **Write / Edit** | Create or change a file |
| **Shell** | Run a terminal command |
| **Web fetch / search** | Get a page or search the web |

The safety model: for anything that **changes your system** (writing a file, running a command), the CLI **pauses and asks you** — you approve, edit, or reject. Read-only actions usually run freely. Your job is to **stay the reviewer**.

---

## 🛠️ Practice (9 min)

### Step 1 — List the tools

```text
/tools
```

See exactly what the CLI can do out of the box. This is its "hands."

### Step 2 — Watch a read-only tool run

Ask something that only needs reading:

```text
Read the README in this folder and summarize what the project does.
```

It reads and answers — no approval needed for a safe, read-only action.

### Step 3 — Trigger an approval prompt

Now ask for a change:

```text
Create a file called hello.txt containing a friendly one-line greeting.
```

The CLI shows what it wants to do and **asks for approval**. Read the proposed action, then approve. Notice you're the gate on every change.

### Step 4 — Understand your approval choices

When asked, you typically can:
- **Approve once** — allow just this action.
- **Approve always** (for this kind/command) — stop being asked for the same safe thing.
- **Reject** — decline and tell it what to do instead.

Grant "always" only for actions you're sure are safe (e.g. a formatter). Keep approving anything that deletes, deploys, or sends.

### Step 5 — Watch a shell command

```text
List the files in this folder and tell me the largest one.
```

It proposes a shell command; approve it and see the result. Because you saw the exact command first, there are no surprises.

### Step 6 — Keep the human gate honest

- Read the proposed action **before** approving — don't rubber-stamp.
- Be extra careful with **shell** and **write** on anything important.
- The CLI has faster "auto-approve" modes (next lesson touches safety) — don't enable them until you trust the setup and are in a safe folder.

---

## 🧩 Tool safety at a glance

| Action | Approval |
|--------|----------|
| Read a file, search web | Usually runs freely (safe) |
| Write / edit a file | Asks first — review it |
| Run a shell command | Asks first — read the command |
| Anything destructive | Asks first — be deliberate |

> ⚠️ **You are the reviewer.** The CLI can touch real files and run real commands. Work in a dedicated folder (or a git branch), read each proposed action, and keep approving changes rather than auto-running everything.

---

## ✅ Checkpoint

- [ ] You listed the built-in tools with `/tools`.
- [ ] You saw a read-only action run without approval.
- [ ] You approved a file write and a shell command after reading them.
- [ ] You understand approve-once vs approve-always vs reject.

---

## 🎯 Homework

Give the CLI a small multi-step task in a scratch folder (create a file, list it, edit it). Approve each action deliberately, reading the proposed command each time. Note which actions you'd be comfortable setting to "always."

---

## 💡 Key takeaways

- The CLI's power comes from **built-in tools** (read, write/edit, shell, web) — see them with `/tools`.
- The **approval flow** gates every system-changing action: approve once, approve always (safe things only), or reject.
- **Stay the reviewer** — read each proposed action, work in a safe folder, and don't auto-run until you trust it.

🌐 [Polski](../../pl/track-g/03-narzedzia-i-zatwierdzenia.md) · [← Prev](02-custom-commands.md) · [Track index](../README.md) · [Next: Checkpointing & undo →](04-checkpointing-and-undo.md)
