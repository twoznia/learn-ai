# D5 — Agents & Claude Code on Your Subscription

⏱️ **15 minutes** · Track: 🅳 Subscription Power · Needs: a Pro/Max account, Node.js (from the beginner course)

🌐 [Polski](../../pl/track-d/05-agenci-i-claude-code.md) · [← Prev](04-skills-and-connectors.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (5 min)

So far Claude has answered questions and made files. An **agent** goes a step further: given a goal, it **plans, takes steps, uses tools, checks its own work, and keeps going** until the task is done — with you approving along the way.

The most useful agent for most people is **Claude Code** — Claude working directly with files and commands on your computer. The key fact for this track: **Claude Code runs on your Pro/Max subscription**. You log in with your Claude account — **no API key, no separate per-token bill.**

Two ways to think about "agentic" work on your plan:

- **In the chat apps** — Claude already chains steps: it plans, calls Skills and connectors, and works through a multi-part request in one go.
- **On your machine** — Claude Code reads and edits real files, runs commands, and iterates, all under your approval.

---

## 🛠️ Practice (9 min)

### Step 1 — Install Claude Code

In **PowerShell**:

```powershell
npm install -g @anthropic-ai/claude-code
```

(If `npm` isn't found, install Node.js from the beginner course first.)

### Step 2 — Log in with your subscription

Go to a folder you want to work in, then start it:

```powershell
mkdir $HOME\claude-code-demo
cd $HOME\claude-code-demo
claude
```

On first run it asks how to sign in. **Choose "log in with your Claude account"** (your Pro/Max plan) rather than an API key. A browser opens; approve it. Now Claude Code uses your **subscription** — no extra billing.

> If it also mentions an API-key option: that's the paid developer path. For this track, use your **account login**.

### Step 3 — Give it a small goal

Type a plain-English task at the prompt:

```text
Create a file called notes.md with three sections: Goals, Today, Later.
Then add three example bullet points under Today.
```

Watch it **plan**, propose the change, and ask permission before writing. Approve it and check the file appeared. You just ran an agent that acted on real files.

### Step 4 — Let it iterate

Agents shine when you refine:

```text
Now add a "Done" section at the top and move one Today item into it.
```

It reads the current file, makes a targeted edit, and shows you the change. You approve each step — you're the reviewer.

### Step 5 — Ask it to explain and verify

```text
Show me the final notes.md and confirm each section has at least one bullet.
```

A good agent checks its own work. Ask it to verify against what you wanted, so you're not taking the result on faith.

### Step 6 — Know your limits still apply

Claude Code draws on the **same usage** as your plan. Heavy, long agent sessions use more of your window — so the habits from D2 and D3 still matter: clear goals, lean context, the right model, and starting a fresh session for a new task.

---

## 🧩 Agent working habits

| Do | Instead of |
|----|------------|
| State the goal + constraints, let it plan | Micro-managing every keystroke |
| Approve each change as you review it | Blindly accepting everything |
| Ask it to verify against your intent | Trusting the result unchecked |
| Work in a dedicated folder | Pointing it at your whole disk |
| Start fresh for a new task | One endless session |

> **Safety:** Claude Code asks before editing files or running commands. Keep it in a **dedicated folder** (or a git branch) so every change is easy to review and undo. You are always the human approving actions.

---

## ✅ Checkpoint

- [ ] Claude Code is installed and logged in with your **subscription** (no API key).
- [ ] It planned and made a real file change that you approved.
- [ ] You iterated with a follow-up and had it verify its own work.
- [ ] You can explain that Claude Code uses your plan's usage, so the D2/D3 habits apply.

---

## 🎯 Homework

Pick a small, real, low-risk task in a dedicated folder — organize some notes, draft a simple script, tidy a to-do list. Drive it with Claude Code using the plan-first, approve-each-step, verify-at-the-end workflow. Keep the goal clear so you stay efficient.

---

## 💡 Key takeaways

- An **agent** plans, acts, uses tools, and verifies toward a goal — with you approving each step.
- **Claude Code** runs on your **Pro/Max subscription** (account login), so there's **no API key and no extra per-use bill**.
- The same **usage limits** apply — clear goals and lean context (D2/D3) keep agent sessions efficient.

🌐 [Polski](../../pl/track-d/05-agenci-i-claude-code.md) · [← Prev](04-skills-and-connectors.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
