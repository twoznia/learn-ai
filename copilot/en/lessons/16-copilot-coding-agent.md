# Lesson 16 — The Copilot Coding Agent

⏱️ **12 minutes** · Level: Advanced · Needs: a GitHub repo + Copilot (agent features vary by plan)

🌐 [Polski](../../pl/lessons/16-agent-kodujacy-copilot.md) · [← Prev](15-copilot-on-github-com.md) · [Course home](../README.md) · [Next: Copilot CLI & Actions →](17-copilot-cli-and-actions.md)

---

## 🧠 Theory (4 min)

So far *you* drove Copilot. The **coding agent** flips it: you **assign an issue to Copilot**, and it works in the background — exploring the repo, making changes on a branch, and **opening a pull request** for you to review. It's like delegating a task to a teammate who always sends a PR back.

The flow:

1. You write a clear **issue** (Lesson 11).
2. You **assign it to Copilot** (or start the agent from the issue/PR).
3. Copilot works on a branch and opens a **draft PR**.
4. **You review** the PR — request changes via comments, and it iterates.
5. You merge when it's right.

The golden rule stays: **you are the reviewer.** The agent proposes; nothing merges without your approval.

> Coding-agent availability, where you trigger it, and its exact behavior depend on your plan and settings and are evolving. Check GitHub's current "Copilot coding agent" docs.

---

## 🛠️ Practice (7 min)

### Step 1 — Write an agent-friendly issue

Use a small, self-contained one from Lesson 11, e.g. "Add a `--language` flag." Include **acceptance criteria** and mention the files involved. The clearer the issue, the better the PR.

### Step 2 — Assign it to Copilot

On the issue, assign it to **Copilot** (in the Assignees area, where available) — or use the "start coding agent" / delegate option on github.com or in VS Code.

### Step 3 — Watch it open a PR

Copilot works on a branch and opens a **draft pull request** describing what it did. This may take a few minutes.

### Step 4 — Review it like any PR

Read the **Files changed** diff (Lessons 10, 13). Does it meet the acceptance criteria? Run the code. Use Copilot review (Lesson 13) as a second pass.

### Step 5 — Request changes

Not quite right? Leave **review comments** describing what to fix. The agent reads them and **pushes updates** to the same PR — iterating like a teammate.

### Step 6 — Merge or take over

When it meets the bar, merge. If it's stuck, **check out the branch** and finish it yourself in VS Code — you're never locked out.

---

## 🧩 You-driven vs agent-driven

| | You-driven (Lessons 2–8) | Agent-driven (this lesson) |
|--|--------------------------|----------------------------|
| Trigger | You type in the editor | You assign an issue |
| Where it works | Your open editor | A branch on GitHub |
| Output | Edits in front of you | A pull request |
| Your role | Author + reviewer | **Reviewer** |

> ⚠️ Give the agent **scoped, well-specified** tasks. Review its PR as carefully as a stranger's — assign, but always verify.

---

## ✅ Checkpoint

- [ ] You wrote a clear, self-contained issue with acceptance criteria.
- [ ] You assigned/handed it to the Copilot coding agent.
- [ ] You reviewed the PR it opened and ran the code.
- [ ] You requested a change (or merged) — staying the reviewer.

---

## 🎯 Homework

Hand the agent one small, well-specified issue on your repo. Review its PR against the acceptance criteria, request one improvement via a comment, and see it update the PR. Then merge. Reflect: what makes an issue easy vs hard for the agent?

---

## 💡 Key takeaways

- The **coding agent** takes an **assigned issue** and opens a **pull request** you review.
- You iterate via **review comments**; it pushes updates — and you can always take over the branch.
- Success depends on **clear, scoped issues** — and you remain the **reviewer** who approves the merge.

🌐 [Polski](../../pl/lessons/16-agent-kodujacy-copilot.md) · [← Prev](15-copilot-on-github-com.md) · [Course home](../README.md) · [Next: Copilot CLI & Actions →](17-copilot-cli-and-actions.md)
