# Lesson 06 — Tests, Docs & Refactoring with Copilot

⏱️ **11 minutes** · Level: Intermediate · Needs: VS Code + Copilot

🌐 [Polski](../../pl/lessons/06-testy-dokumentacja-refactoring.md) · [← Prev](05-edits-and-agent-mode.md) · [Course home](../README.md) · [Next: Custom instructions →](07-custom-instructions.md)

---

## 🧠 Theory (3 min)

Three everyday jobs where Copilot saves the most time — and where **you must review carefully**:

- **Tests** — Copilot writes unit tests fast, including edge cases you'd forget. Tests are also a great safety net for AI-generated code.
- **Docs** — docstrings, comments, and READMEs from the code itself.
- **Refactoring** — restructuring code without changing behavior (smaller functions, better names, less duplication).

The theme: Copilot drafts, **you verify** — especially that tests actually test the right thing and refactors don't change behavior.

---

## 🛠️ Practice (7 min)

### Step 1 — Generate tests

Open a file with a function (reuse `greetings.py` or `demo.py`). Select the function and:

```text
/tests
```

Or ask specifically:

```text
Write pytest tests for get_greeting covering: normal name, empty string,
and an unsupported language. Use clear test names.
```

### Step 2 — Run them

In the VS Code terminal (**Ctrl+`**):

```powershell
pip install pytest
pytest
```

Fix failures with `/fix` — but first **check the test is correct**, not just the code.

### Step 3 — Add documentation

Select a function and:

```text
/doc
```

Or: "Add a docstring explaining parameters, return value, and one usage example."

### Step 4 — Refactor safely

```text
Refactor this file into smaller functions with clear names. Do NOT change
behavior. List what you changed and why.
```

Then **run your tests again** — green tests are your proof behavior didn't change.

### Step 5 — Improve names and remove duplication

```text
Find duplicated logic in these files and extract it into a shared helper.
Show the diff.
```

### Step 6 — Explain legacy code

Inherited a messy file? Open it and ask:

```text
Explain what this file does, note anything risky, and suggest 3 small,
safe improvements — don't apply them yet.
```

---

## 🧩 Copilot for quality work

| Task | Prompt starter |
|------|----------------|
| Tests | "/tests" or "write pytest tests covering …" |
| Docs | "/doc" or "add a docstring with an example" |
| Refactor | "refactor into smaller functions, no behavior change" |
| Names | "suggest clearer names for these variables" |
| Understand | "explain this file and its risks" |

> ⚠️ AI-written tests can pass while testing the wrong thing. Read each test's **assertions** — do they match what the code *should* do?

---

## ✅ Checkpoint

- [ ] You generated and ran tests, and they pass.
- [ ] You added a docstring with `/doc` or a prompt.
- [ ] You refactored a file and confirmed tests still pass.
- [ ] You had Copilot explain a file and its risks.

---

## 🎯 Homework

Pick a function you wrote earlier. Generate tests (aim for 3+ cases including an edge case), run them, then refactor the function into smaller pieces and confirm the tests still pass. That test-then-refactor loop is a pro habit.

---

## 💡 Key takeaways

- Copilot quickly drafts **tests, docs, and refactors** — huge time-savers.
- **Tests are your safety net** for AI code — but verify their assertions are right.
- Refactor with "**no behavior change**," then **re-run tests** to prove it.

🌐 [Polski](../../pl/lessons/06-testy-dokumentacja-refactoring.md) · [← Prev](05-edits-and-agent-mode.md) · [Course home](../README.md) · [Next: Custom instructions →](07-custom-instructions.md)
