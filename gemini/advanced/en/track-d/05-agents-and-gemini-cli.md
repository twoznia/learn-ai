# D5 — Agents & the Gemini CLI on Your Plan

⏱️ **15 minutes** · Track: 🅳 Subscription Power · Needs: a Google account, Node.js (from the beginner course)

🌐 [Polski](../../pl/track-d/05-agenci-i-gemini-cli.md) · [← Prev](04-personalization-and-memory.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)

---

## 🧠 Theory (5 min)

So far Gemini has answered questions and made files. An **agent** goes further: given a goal, it **plans, takes steps, uses tools, checks its work, and keeps going** until the task is done — with you approving along the way.

The most useful agent for most people is the **Gemini CLI** — Gemini working directly with files and commands on your computer. The key fact for this track: **you can sign in with your Google account** and use a **generous free tier** — no API key and no separate billing to get started.

Two ways to think about agentic work:

- **In the app** — Gemini already chains steps: it plans, uses Deep Research, calls connected apps, and works through a multi-part request in one go.
- **On your machine** — the Gemini CLI reads and edits real files, runs commands, and iterates, under your approval.

---

## 🛠️ Practice (9 min)

### Step 1 — Install the Gemini CLI

In **PowerShell**:

```powershell
npm install -g @google/gemini-cli
```

(If `npm` isn't found, install Node.js from the beginner course first.)

### Step 2 — Sign in with your Google account

Go to a folder you want to work in, then start it:

```powershell
mkdir $HOME\gemini-cli-demo
cd $HOME\gemini-cli-demo
gemini
```

On first run it asks how to sign in. **Choose "Login with Google"** to use the free tier on your account (rather than pasting an API key). A browser opens; approve it. Now the CLI runs on your account — no extra billing to start.

> If it also offers an API-key option: that's the developer/metered path. For this track, use your **Google login**.

### Step 3 — Give it a small goal

Type a plain-English task at the prompt:

```text
Create a file called notes.md with three sections: Goals, Today, Later.
Then add three example bullet points under Today.
```

Watch it **plan**, propose the change, and ask permission before writing. Approve it and check the file appeared. You just ran an agent on real files.

### Step 4 — Let it iterate

```text
Now add a "Done" section at the top and move one Today item into it.
```

It reads the current file, makes a targeted edit, and shows you the change. You approve each step — you're the reviewer.

### Step 5 — Ask it to verify

```text
Show me the final notes.md and confirm each section has at least one bullet.
```

A good agent checks its own work — ask it to verify against what you wanted.

### Step 6 — Your limits still apply

The CLI draws on your account's usage. Long agent sessions use more — so the D2/D3 habits matter: clear goals, lean context, the right model, and fresh sessions for new tasks.

---

## 🧩 Agent working habits

| Do | Instead of |
|----|------------|
| State the goal + constraints, let it plan | Micro-managing every keystroke |
| Approve each change as you review it | Blindly accepting everything |
| Ask it to verify against your intent | Trusting the result unchecked |
| Work in a dedicated folder | Pointing it at your whole disk |
| Start fresh for a new task | One endless session |

> **Safety:** the Gemini CLI asks before editing files or running commands. Keep it in a **dedicated folder** (or a git branch) so every change is easy to review and undo. You're always the human approving actions.

---

## ✅ Checkpoint

- [ ] The Gemini CLI is installed and signed in with your **Google account** (free tier, no API key).
- [ ] It planned and made a real file change you approved.
- [ ] You iterated with a follow-up and had it verify its own work.
- [ ] You can explain that the CLI uses your account's usage, so D2/D3 apply.

---

## 🎯 Homework

Pick a small, real, low-risk task in a dedicated folder — organize notes, draft a simple script, tidy a to-do list. Drive it with the Gemini CLI using plan-first, approve-each-step, verify-at-the-end. Keep the goal clear to stay efficient.

---

## 💡 Key takeaways

- An **agent** plans, acts, uses tools, and verifies toward a goal — with you approving each step.
- The **Gemini CLI** runs on your **Google account's free tier** (Google login) — no API key, no separate bill to start.
- The same **usage limits** apply — clear goals and lean context (D2/D3) keep agent sessions efficient.

🌐 [Polski](../../pl/track-d/05-agenci-i-gemini-cli.md) · [← Prev](04-personalization-and-memory.md) · [Track index](../README.md) · [↩ Advanced landing](../README.md)
