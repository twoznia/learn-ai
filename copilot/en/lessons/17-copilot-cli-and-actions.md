# Lesson 17 — Copilot in the Terminal + GitHub Actions

⏱️ **13 minutes** · Level: Advanced · Needs: a GitHub repo, Node.js or the GitHub CLI

🌐 [Polski](../../pl/lessons/17-copilot-cli-i-actions.md) · [← Prev](16-copilot-coding-agent.md) · [Course home](../README.md) · [Next: Costs, limits & next steps →](18-costs-limits-and-next-steps.md)

---

## 🧠 Theory (4 min)

Two power tools tie everything together:

- **Copilot in the terminal (Copilot CLI)** — ask for shell commands and get code help right in your terminal, and script it for automation. Great for "what's the command to…?" and headless tasks.
- **GitHub Actions** — GitHub's automation that runs on events (like opening a PR). The classic use is **CI (Continuous Integration)**: automatically run your tests on every PR, so broken code can't merge unnoticed. Copilot's review can layer on top, and **Copilot Autofix** can even propose fixes for security issues it finds.

Together: your tests run automatically, Copilot reviews, and you merge with confidence.

> Tool names, install commands, and Autofix availability change over time. Check the current GitHub docs for the Copilot CLI and GitHub Actions; the *concepts* — scriptable Copilot + automated checks — are stable.

---

## 🛠️ Practice (8 min)

### Step 1 — Get a Copilot CLI

A common path is the **GitHub CLI** with the Copilot extension:

```powershell
winget install --id GitHub.cli -e
gh auth login
gh extension install github/gh-copilot
```

(Or install the standalone Copilot CLI per the current docs.)

### Step 2 — Ask for a command

```powershell
gh copilot suggest "find the 5 largest files in this folder tree on Windows"
```

It proposes a command and explains it. Ask before running anything you don't understand.

### Step 3 — Explain a scary command

```powershell
gh copilot explain "git reset --hard origin/main"
```

Perfect for understanding a command before you run it.

### Step 4 — Add CI: run tests on every PR

Create `.github/workflows/ci.yml`. Let Copilot draft it:

```text
@workspace Create a GitHub Actions workflow that runs on pull requests: set up
Python, install pytest, and run the tests. Keep it minimal.
```

A minimal example:

```yaml
name: CI
on: [pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-python@v5
        with:
          python-version: "3.x"
      - run: pip install pytest
      - run: pytest
```

Commit it on a branch and open a PR — watch the **Checks** run.

### Step 5 — Read the check results

On the PR, the **Checks** tab shows pass/fail. If tests fail, the PR flags it — and you can ask Copilot to fix them.

### Step 6 — Explore Copilot Autofix (security)

If your repo has code scanning enabled, **Copilot Autofix** may propose fixes for security alerts on PRs. Review its suggested fix like any other — then apply if correct.

---

## 🧩 Automation stack

| Layer | What it does |
|-------|--------------|
| **Copilot CLI** | Command suggestions + scriptable help |
| **GitHub Actions (CI)** | Runs your tests on every PR automatically |
| **Copilot review** | AI review comments on the PR |
| **Copilot Autofix** | Proposes fixes for security alerts |
| **You** | Approve the merge |

> ⚠️ CI runs code from PRs — be careful enabling it on untrusted contributions. And always review Autofix suggestions; a proposed fix can still be wrong.

---

## ✅ Checkpoint

- [ ] You used a Copilot CLI to suggest and explain a command.
- [ ] You added a GitHub Actions workflow that runs tests on PRs.
- [ ] You opened a PR and watched the checks run.
- [ ] You know where Copilot review and Autofix fit in the stack.

---

## 🎯 Homework

Add the CI workflow to your repo, then open a PR that intentionally breaks a test. Confirm CI catches it (red check), fix it with Copilot, and watch the check go green. You've now got automated tests guarding your `main`.

---

## 💡 Key takeaways

- The **Copilot CLI** suggests and explains shell commands and can be scripted.
- **GitHub Actions (CI)** runs your **tests automatically on every PR** — broken code gets flagged.
- **Copilot review + Autofix** layer AI checks on top; you still **approve the merge**.

🌐 [Polski](../../pl/lessons/17-copilot-cli-i-actions.md) · [← Prev](16-copilot-coding-agent.md) · [Course home](../README.md) · [Next: Costs, limits & next steps →](18-costs-limits-and-next-steps.md)
