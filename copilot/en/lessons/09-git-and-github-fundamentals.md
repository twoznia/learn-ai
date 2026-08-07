# Lesson 09 — Git & GitHub Fundamentals (with Copilot as Tutor)

⏱️ **13 minutes** · Level: Beginner (GitHub) · Needs: Windows, a GitHub account

🌐 [Polski](../../pl/lessons/09-podstawy-git-i-github.md) · [← Prev](08-context-participants-references.md) · [Course home](../README.md) · [Next: Branches & pull requests →](10-branches-and-pull-requests.md)

---

## 🧠 Theory (4 min)

To get the most from Copilot's PR and review features, you need the basics of **Git** and **GitHub**.

- **Git** — a tool that tracks changes to your files over time. A **commit** is a saved snapshot; the **history** is the trail of commits.
- **GitHub** — a website that hosts Git **repositories** (repos) online, so you can back up, share, and collaborate.

The everyday loop: **change files → commit (snapshot) → push (upload to GitHub)**. That's it for now. And whenever a Git command confuses you, **ask Copilot** — it's a patient tutor.

---

## 🛠️ Practice (8 min)

### Step 1 — Install Git

```powershell
winget install --id Git.Git -e
```

Close and reopen your terminal, then check:

```powershell
git --version
```

### Step 2 — Tell Git who you are

```powershell
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

### Step 3 — Turn your project into a repo

In your `copilot-course` folder (VS Code terminal, **Ctrl+`**):

```powershell
git init
git add -A
git commit -m "First commit: my Copilot course project"
```

You just saved your first snapshot.

### Step 4 — Create the repo on GitHub and push

Easiest path: VS Code's **Source Control** view (**Ctrl+Shift+G**) has a **Publish to GitHub** button — click it, choose private or public, and it creates the GitHub repo and pushes for you.

> Prefer the browser? Create an empty repo at **github.com/new**, then follow the "push an existing repository" commands it shows.

### Step 5 — Use Copilot to learn Git

Stuck on any Git idea? Ask **@terminal**:

```text
@terminal I changed 3 files. Show me the exact commands to commit them with a
good message and push to GitHub, and explain each step.
```

### Step 6 — See your history

```powershell
git log --oneline
```

Every commit is a point you can return to — your safety net for everything Copilot does next.

---

## 🗺️ Everyday Git (bookmark)

| Do | Command |
|----|---------|
| See what changed | `git status` |
| Stage all changes | `git add -A` |
| Save a snapshot | `git commit -m "message"` |
| Upload to GitHub | `git push` |
| Get latest from GitHub | `git pull` |
| See history | `git log --oneline` |

> **Tip:** VS Code's Source Control panel does all of this with buttons — and Copilot can write your commit messages (Lesson 12).

---

## ✅ Checkpoint

- [ ] Git is installed and knows your name/email.
- [ ] Your project is a Git repo with at least one commit.
- [ ] You published it to GitHub (it's visible in your account).
- [ ] You asked Copilot to explain a Git command.

---

## 🎯 Homework

Make a small change to a file, then commit and push it — using either the terminal or VS Code's Source Control buttons. Refresh your repo on github.com and confirm the change appears. Ask Copilot to explain anything that felt unclear.

---

## 💡 Key takeaways

- **Git** snapshots your work (commits); **GitHub** hosts it online.
- The loop is **change → commit → push**; `git pull` gets others' changes.
- VS Code's **Source Control** panel does it with buttons, and **Copilot is a great Git tutor** — just ask.

🌐 [Polski](../../pl/lessons/09-podstawy-git-i-github.md) · [← Prev](08-context-participants-references.md) · [Course home](../README.md) · [Next: Branches & pull requests →](10-branches-and-pull-requests.md)
