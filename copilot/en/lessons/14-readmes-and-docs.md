# Lesson 14 — READMEs & Documentation with Copilot

⏱️ **11 minutes** · Level: Intermediate · Needs: a GitHub repo + Copilot

🌐 [Polski](../../pl/lessons/14-readme-i-dokumentacja.md) · [← Prev](13-automatic-code-review.md) · [Course home](../README.md) · [Next: Copilot on github.com →](15-copilot-on-github-com.md)

---

## 🧠 Theory (3 min)

A **README** is the front door of your project — the first thing people (and future-you) read. A good one explains **what** the project is, **how to install and run it**, and **how to use it**. Copilot can draft the whole thing from your code, then keep it up to date.

Good docs to generate:

- **README.md** — overview, install, usage, examples.
- **Docstrings/comments** — in the code (Lesson 6).
- **CONTRIBUTING / usage guides** — for bigger projects.

The win: Copilot reads your actual project, so the docs match the code — as long as you **review** for accuracy.

---

## 🛠️ Practice (7 min)

### Step 1 — Generate a README

In VS Code, with your project open:

```text
@workspace Write a README.md for this project: a one-line description, features,
installation (Windows/PowerShell), usage with a runnable example, and a project
structure section. Keep it friendly and concise.
```

Save it as `README.md` in the project root.

### Step 2 — Preview it

Open `README.md` and press **Ctrl+Shift+V** for the Markdown preview. Check headings, code blocks, and links render well.

### Step 3 — Make the examples real

Docs rot when examples are fake. Ask:

```text
Make the usage examples match the actual commands and output of this project.
Verify against the code.
```

Then **run the commands yourself** to confirm they work.

### Step 4 — Add badges and a table of contents (optional)

```text
Add a short table of contents and a "Requirements" section. Suggest any badges
that make sense (e.g. language, license).
```

### Step 5 — Keep it in sync

After a feature change, update docs in the same PR:

```text
@workspace I added the --language flag. Update README.md's usage section and
examples to include it. Show the diff.
```

Docs updated in the **same PR** as the code never drift.

### Step 6 — Document as you go

For any non-obvious function, generate a docstring (Lesson 6). Well-documented code makes README generation better, too.

---

## 🧩 A solid README

| Section | Contents |
|---------|----------|
| **Title + one-liner** | What it is, in a sentence |
| **Features** | What it can do |
| **Install** | Exact steps (Windows/PowerShell) |
| **Usage** | Runnable examples + expected output |
| **Structure** | Key files/folders |
| **License** | How others may use it |

> ⚠️ Copilot can invent commands or features. **Run the examples** and verify claims before committing docs.

---

## ✅ Checkpoint

- [ ] You generated a README with Copilot and previewed it.
- [ ] You made the examples match the real project and ran them.
- [ ] You updated the docs after a change, in the same PR.
- [ ] Your README covers install, usage, and structure.

---

## 🎯 Homework

Write (or regenerate) a real README for your project with Copilot. Verify every command by running it, fix anything inaccurate, and commit it. Then make a small feature change and update the README in the **same** PR.

---

## 💡 Key takeaways

- Copilot drafts **READMEs and docs** from your actual code — a huge head start.
- A good README covers **what, install, usage (with real examples), and structure**.
- **Verify examples by running them**, and update docs **in the same PR** as the code so they never drift.

🌐 [Polski](../../pl/lessons/14-readme-i-dokumentacja.md) · [← Prev](13-automatic-code-review.md) · [Course home](../README.md) · [Next: Copilot on github.com →](15-copilot-on-github-com.md)
