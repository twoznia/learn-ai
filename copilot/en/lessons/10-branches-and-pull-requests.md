# Lesson 10 — Branches & the Pull Request Workflow

⏱️ **13 minutes** · Level: Beginner → Intermediate (GitHub) · Needs: a GitHub repo (Lesson 9)

🌐 [Polski](../../pl/lessons/10-galezie-i-pull-requesty.md) · [← Prev](09-git-and-github-fundamentals.md) · [Course home](../README.md) · [Next: Issues, labels & projects →](11-issues-labels-projects.md)

---

## 🧠 Theory (4 min)

The **pull request (PR)** is the heart of working on GitHub — and where Copilot's review and summary features shine (next lessons). First, the workflow.

- A **branch** is a parallel copy of your code where you make changes safely, without touching `main`.
- You commit your work on the branch, **push** it, then open a **pull request** — a proposal to merge your branch into `main`.
- A PR is a place to **review** the changes (see the diff, comment, run checks) before merging.

The loop: **branch → commit → push → open PR → review → merge.** Even solo, this keeps `main` clean and gives you a review step.

---

## 🛠️ Practice (8 min)

### Step 1 — Create a branch

In your repo (VS Code terminal):

```powershell
git switch -c add-farewell
```

You're now on a branch called `add-farewell`; `main` is untouched.

### Step 2 — Make a change with Copilot

Ask Copilot to add a small feature, e.g. a `get_farewell(name)` function. Accept it.

### Step 3 — Commit and push the branch

```powershell
git add -A
git commit -m "Add get_farewell function"
git push -u origin add-farewell
```

### Step 4 — Open a pull request

GitHub prints a link after the push, or go to your repo on github.com — it shows **"Compare & pull request."** Click it. You'll see:
- The **title** and **description** boxes.
- The **diff** (files changed).

Give it a clear title, and open the PR.

> In VS Code, the **GitHub Pull Requests** extension lets you create and review PRs without leaving the editor. Install it if you'd like — it's the same workflow.

### Step 5 — Review your own PR

On the PR's **Files changed** tab, read the diff as if reviewing someone else. This habit catches mistakes before they land.

### Step 6 — Merge it

When you're happy, click **Merge pull request** → **Confirm**. Then locally:

```powershell
git switch main
git pull
```

Your change is now in `main`, and your history stays tidy.

---

## 🧩 The PR workflow

| Step | Command / action |
|------|------------------|
| New branch | `git switch -c my-feature` |
| Commit work | `git commit -m "..."` |
| Push branch | `git push -u origin my-feature` |
| Open PR | "Compare & pull request" on GitHub |
| Review | Read the **Files changed** diff |
| Merge | **Merge pull request** → Confirm |

> Branch names should describe the change (`fix-login-bug`, `add-dark-mode`) — Copilot can suggest one if you ask.

---

## ✅ Checkpoint

- [ ] You created a branch and made a change on it.
- [ ] You pushed the branch and opened a pull request.
- [ ] You reviewed the diff on the Files changed tab.
- [ ] You merged the PR and pulled `main` locally.

---

## 🎯 Homework

Do a second full loop: branch, make a Copilot-assisted change, push, open a PR with a clear title, review the diff, and merge. The workflow should start feeling routine — because the next lessons build on it.

---

## 💡 Key takeaways

- Work on a **branch**, then open a **pull request** to merge into `main`.
- A PR is a **review surface** — always read the **Files changed** diff before merging.
- The loop is **branch → commit → push → PR → review → merge**, and it's the foundation for Copilot's PR features.

🌐 [Polski](../../pl/lessons/10-galezie-i-pull-requesty.md) · [← Prev](09-git-and-github-fundamentals.md) · [Course home](../README.md) · [Next: Issues, labels & projects →](11-issues-labels-projects.md)
