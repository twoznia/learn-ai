# Lesson 15 — Copilot on github.com

⏱️ **11 minutes** · Level: Intermediate · Needs: a GitHub repo + Copilot

🌐 [Polski](../../pl/lessons/15-copilot-na-github-com.md) · [← Prev](14-readmes-and-docs.md) · [Course home](../README.md) · [Next: Copilot coding agent →](16-copilot-coding-agent.md)

---

## 🧠 Theory (3 min)

Copilot isn't only in VS Code — it's built into **github.com** too. Right in the browser you can:

- **Chat about a repository** — ask how it works, where something lives, how to do a task.
- **Summarize a pull request** — get the gist of a big diff before reviewing.
- **Ask about issues, code, and docs** — without cloning anything.

This is perfect when you're **away from your editor** — reviewing on a phone or tablet, triaging on someone else's machine, or exploring an unfamiliar project you haven't cloned.

> The exact Copilot features on github.com depend on your plan and roll out over time. Look for the **Copilot icon** in the top bar and on pull requests.

---

## 🛠️ Practice (7 min)

### Step 1 — Open Copilot Chat in the browser

On github.com, click the **Copilot** icon (top bar). A chat opens that can reference GitHub context.

### Step 2 — Ask about a repository

Navigate to your repo, then ask:

```text
What does this repository do, and where is the command-line entry point?
```

Great for getting oriented in **any** repo fast.

### Step 3 — Summarize a pull request

Open a PR with a non-trivial diff and use the **Copilot summary** (on the PR, look for the Copilot option in the description area or the Copilot icon):

```text
Summarize what this PR changes, the risk areas, and what a reviewer should focus on.
```

You get a review briefing before reading every line.

### Step 4 — Explore code without cloning

Browsing an unfamiliar project on GitHub? Ask Copilot:

```text
Explain how authentication works in this repo and which files are involved.
```

### Step 5 — Ask about an issue

On an issue, ask Copilot to suggest an approach or draft acceptance criteria — handy for triage.

### Step 6 — Know when to use which surface

| You're… | Use |
|---------|-----|
| Writing/editing code | **VS Code** Copilot |
| Reviewing a PR in the browser | **github.com** Copilot summary |
| Exploring a repo you haven't cloned | **github.com** chat |
| On mobile / someone else's PC | **github.com** Copilot |

---

## 🧩 Copilot surfaces recap

| Surface | Strengths |
|---------|-----------|
| **VS Code** | Completions, edits, agent, deep code work |
| **github.com** | Repo chat, PR summaries, triage, no clone |
| **Terminal / CLI** | Scriptable help (Lesson 17) |

---

## ✅ Checkpoint

- [ ] You opened Copilot Chat on github.com.
- [ ] You asked about a repository and got oriented.
- [ ] You summarized a pull request in the browser.
- [ ] You can pick the right Copilot surface for a situation.

---

## 🎯 Homework

Find a public open-source repo you don't know. On github.com, use Copilot to explain what it does, where its entry point is, and how to run it — without cloning. Then summarize one of its recent merged PRs.

---

## 💡 Key takeaways

- Copilot lives on **github.com**: repo chat, **PR summaries**, and issue/code exploration.
- It's ideal when you're **away from your editor** or exploring a repo you haven't cloned.
- Match the **surface to the task** — VS Code for building, github.com for reviewing and exploring.

🌐 [Polski](../../pl/lessons/15-copilot-na-github-com.md) · [← Prev](14-readmes-and-docs.md) · [Course home](../README.md) · [Next: Copilot coding agent →](16-copilot-coding-agent.md)
