# Lesson 07 — Custom Instructions & House Style

⏱️ **11 minutes** · Level: Intermediate · Needs: VS Code + Copilot, a project folder

🌐 [Polski](../../pl/lessons/07-wlasne-instrukcje.md) · [← Prev](06-tests-docs-refactoring.md) · [Course home](../README.md) · [Next: Context, participants & references →](08-context-participants-references.md)

---

## 🧠 Theory (4 min)

Re-typing "use pathlib, add type hints, write concise comments" every time is a waste. **Custom instructions** let you set standing rules once, and Copilot applies them automatically.

The main mechanism is a file in your repo:

```
.github/copilot-instructions.md
```

Copilot **reads it automatically** and follows it for chat and edits in that project. Put your project's facts and conventions there — language, style, libraries, do's and don'ts — and stop repeating yourself.

You can also set **personal** instructions in VS Code settings that follow *you* across projects. Project instructions describe *the project*; personal ones describe *your preferences*.

> The exact filenames and settings for custom instructions evolve (there are also per-task and "prompt file" variants). Check the current Copilot docs; the idea — **standing rules Copilot auto-applies** — is stable.

---

## 🛠️ Practice (7 min)

### Step 1 — Create the instructions file

In your project, create `.github/copilot-instructions.md`:

```powershell
mkdir .github -Force
notepad .github\copilot-instructions.md
```

### Step 2 — Write real, useful rules

```markdown
# Copilot instructions for this project

## About
A small Python utility project. Beginner-friendly, Windows-first.

## Conventions
- Python 3, use type hints and `pathlib` (not `os.path`).
- Keep functions small; write concise docstrings with one example.
- Prefer standard library; ask before adding a dependency.

## Testing
- Use `pytest`. Every new function gets at least one test.

## Don't
- Don't reformat unrelated code.
- Don't include secrets or API keys in code.
```

Save it.

### Step 3 — See it take effect

Start a fresh chat and ask Copilot to add a function. It should now use type hints and `pathlib` **without you asking** — because it read your instructions.

### Step 4 — Add personal instructions (optional)

In VS Code settings (search "Copilot instructions"), add preferences that follow you everywhere, e.g. *"Explain risky changes before making them; I'm on Windows, give PowerShell commands."*

### Step 5 — Keep instructions lean and current

- Put facts Copilot can't guess (how to run, conventions, no-go zones).
- Remove anything stale — a wrong instruction misleads every session.
- It's committed to the repo, so **no secrets**.

### Step 6 — Let it help write them

```text
Look at this project and draft a copilot-instructions.md capturing its language,
conventions, and how to run and test it. I'll review before saving.
```

---

## 🧩 Which instructions go where

| Rule | Put it in |
|------|-----------|
| Project language, style, libraries | `.github/copilot-instructions.md` |
| How to run/test this project | `.github/copilot-instructions.md` |
| "I'm on Windows, be concise" | Personal (VS Code settings) |
| A one-off task's rules | In the chat prompt itself |

---

## ✅ Checkpoint

- [ ] You created `.github/copilot-instructions.md` with real conventions.
- [ ] A fresh Copilot answer followed your rules without being told.
- [ ] You know project vs personal instructions.
- [ ] Your instructions contain no secrets.

---

## 🎯 Homework

Write a real `copilot-instructions.md` for a project you care about: what it is, how to run/test it, its conventions, and its no-go zones. Then ask Copilot for a change and confirm it honors the rules.

---

## 💡 Key takeaways

- **`.github/copilot-instructions.md`** sets standing rules Copilot **auto-applies** in that repo.
- **Project** instructions describe the project; **personal** ones describe your preferences.
- Keep them **lean, current, secret-free** — and let Copilot draft a first version for you to review.

🌐 [Polski](../../pl/lessons/07-wlasne-instrukcje.md) · [← Prev](06-tests-docs-refactoring.md) · [Course home](../README.md) · [Next: Context, participants & references →](08-context-participants-references.md)
