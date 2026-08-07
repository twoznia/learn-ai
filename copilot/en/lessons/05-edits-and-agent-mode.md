# Lesson 05 — Copilot Edits & Agent Mode

⏱️ **12 minutes** · Level: Intermediate · Needs: VS Code + Copilot, a folder with a few files

🌐 [Polski](../../pl/lessons/05-edits-i-tryb-agenta.md) · [← Prev](04-prompting-copilot-well.md) · [Course home](../README.md) · [Next: Tests, docs & refactoring →](06-tests-docs-refactoring.md)

---

## 🧠 Theory (4 min)

Inline chat edits **one** spot. Copilot can also make **coordinated changes across many files** — that's what **Edits** and **Agent mode** are for.

- **Edit mode** — you pick a set of files and describe a change; Copilot proposes edits **across all of them** as a reviewable set of diffs. You accept or discard, file by file.
- **Agent mode** — you give a **goal**, and Copilot decides which files to change, makes the edits, and can run tasks (like tests) and iterate — checking its own work. You still approve actions.

The difference: Edit mode is *you-directed* across chosen files; Agent mode is *goal-directed* and figures out the steps. Both keep you as the reviewer.

> Mode names and availability evolve. Look for a **mode selector** in the Copilot Chat panel (e.g. Ask / Edit / Agent). If yours differs, the workflow — describe change, review diffs, approve — is the same.

---

## 🛠️ Practice (7 min)

### Step 1 — Set up a tiny multi-file project

Ask Copilot Chat:

```text
Create a small project: app.py with a main() that greets the user, and
greetings.py with a function get_greeting(name). Wire them together.
```

Now you have two files that relate to each other.

### Step 2 — Switch to Edit mode

In the Copilot Chat panel, choose **Edit** mode. **Add** both files to the working set (drag them in, or use the add-files control).

### Step 3 — Describe a cross-file change

```text
Add a language parameter (default "en") throughout: get_greeting(name, language)
should support "en" and "pl", and main() should ask the user which language.
```

Copilot proposes edits in **both** files. Review each **diff**, then **Accept**.

### Step 4 — Try Agent mode

Switch to **Agent** mode and give a goal:

```text
Add a simple unit test file for get_greeting covering both languages, then run
the tests and fix anything that fails.
```

Watch it create the test, run it, and iterate. **Approve** actions it asks about.

### Step 5 — Review everything before keeping it

Open the **Source Control** view (**Ctrl+Shift+G**) to see all changes at once. Never accept a batch you haven't skimmed.

### Step 6 — Undo if needed

Didn't like it? Use **Ctrl+Z** per file, or (better) rely on Git — which we set up in Lesson 9 so any change is reversible.

---

## 🧩 Ask vs Edit vs Agent

| Mode | You give | Copilot does | Best for |
|------|----------|--------------|----------|
| **Ask** | A question | Answers, suggests | Understanding, snippets |
| **Edit** | Files + a change | Diffs across those files | Targeted multi-file edits |
| **Agent** | A goal | Plans, edits, runs, iterates | Bigger tasks, end-to-end |

> ⚠️ Agent mode can run commands and change many files. Work in a **folder backed by Git** and review diffs before committing.

---

## ✅ Checkpoint

- [ ] You made a two-file project.
- [ ] You used **Edit mode** to change both files from one instruction.
- [ ] You used **Agent mode** to add and run tests.
- [ ] You reviewed all changes in Source Control before keeping them.

---

## 🎯 Homework

Take a small project and use Edit mode to rename a concept across files (e.g. "user" → "customer"). Then use Agent mode to "add a README describing how to run it." Review every diff before accepting.

---

## 💡 Key takeaways

- **Edit mode** applies a change across **chosen files** as reviewable diffs.
- **Agent mode** takes a **goal**, plans the steps, edits, runs tasks, and iterates — with your approval.
- Always **review diffs** (Source Control view) and work in a **Git-backed** folder so changes are reversible.

🌐 [Polski](../../pl/lessons/05-edits-i-tryb-agenta.md) · [← Prev](04-prompting-copilot-well.md) · [Course home](../README.md) · [Next: Tests, docs & refactoring →](06-tests-docs-refactoring.md)
