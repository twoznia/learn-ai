# Lesson 11 — Issues, Labels & Project Boards

⏱️ **11 minutes** · Level: Beginner (GitHub) · Needs: a GitHub repo

🌐 [Polski](../../pl/lessons/11-zgloszenia-etykiety-projekty.md) · [← Prev](10-branches-and-pull-requests.md) · [Course home](../README.md) · [Next: Great pull requests →](12-great-pull-requests.md)

---

## 🧠 Theory (3 min)

GitHub isn't just code — it's how work gets **tracked**. Three tools:

- **Issues** — a to-do or bug report with a title, description, and discussion. Each has a number (#12) you can reference from commits and PRs.
- **Labels** — tags like `bug`, `enhancement`, `good first issue` to categorize and filter.
- **Projects** — a board (like sticky notes in columns: To do / In progress / Done) that organizes issues and PRs.

Why it matters here: in Lesson 16, you'll **assign an issue to Copilot's coding agent** and it will open a PR to solve it. Good issues make that work.

---

## 🛠️ Practice (7 min)

### Step 1 — Open an issue

On your repo, go to the **Issues** tab → **New issue**. Write a clear, actionable one:

```text
Title: Add a --language flag to the CLI

Body:
The app should accept --language en|pl and pass it to get_greeting.
Acceptance:
- `python app.py --language pl` prints a Polish greeting
- Defaults to English when omitted
```

A good issue states **what** and **how you'll know it's done** (acceptance).

### Step 2 — Add labels

On the issue, add a label like **enhancement**. Create custom labels via the **Labels** page if you want (e.g. `copilot-task`).

### Step 3 — Reference issues from commits

When you work on it, mention the number so GitHub links them:

```powershell
git commit -m "Add --language flag (part of #1)"
```

Writing **"Closes #1"** in a PR description auto-closes the issue when merged.

### Step 4 — Make a simple project board

Go to **Projects** (on your profile or repo) → **New project** → pick the **Board** template. Add columns **To do / In progress / Done** and drop your issue in **To do**.

### Step 5 — Let Copilot draft issues

In Copilot Chat (VS Code or github.com):

```text
@workspace Read the TODO comments in this project and draft GitHub issues for
them — clear titles and acceptance criteria. I'll create the good ones.
```

### Step 6 — Write issues Copilot can act on

For Lesson 16, the best issues are **specific and self-contained**: one clear outcome, acceptance criteria, and pointers to the files involved.

---

## 🧩 Tracking building blocks

| Tool | Purpose |
|------|---------|
| **Issue** | A tracked task/bug with discussion (#number) |
| **Label** | Categorize & filter (bug, enhancement…) |
| **Project board** | Visualize work across To do / Doing / Done |
| **"Closes #N"** | Auto-close an issue when a PR merges |

---

## ✅ Checkpoint

- [ ] You created a clear issue with acceptance criteria.
- [ ] You added a label.
- [ ] You referenced an issue number from a commit or PR.
- [ ] You made a simple project board (or drafted issues with Copilot).

---

## 🎯 Homework

Write two well-formed issues for your project — each with a specific outcome and acceptance criteria — and add them to a board. Keep at least one small and self-contained; you'll hand it to Copilot's coding agent in Lesson 16.

---

## 💡 Key takeaways

- **Issues** track tasks/bugs; **labels** categorize; **project boards** visualize the flow.
- Reference issues with **#number**, and **"Closes #N"** auto-closes them on merge.
- Clear, self-contained issues with **acceptance criteria** are what Copilot's agent needs to help.

🌐 [Polski](../../pl/lessons/11-zgloszenia-etykiety-projekty.md) · [← Prev](10-branches-and-pull-requests.md) · [Course home](../README.md) · [Next: Great pull requests →](12-great-pull-requests.md)
