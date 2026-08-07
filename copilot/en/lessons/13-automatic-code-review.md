# Lesson 13 — Automatic Code Review with Copilot

⏱️ **12 minutes** · Level: Intermediate · Needs: a GitHub repo + Copilot

🌐 [Polski](../../pl/lessons/13-automatyczny-przeglad-kodu.md) · [← Prev](12-great-pull-requests.md) · [Course home](../README.md) · [Next: READMEs & documentation →](14-readmes-and-docs.md)

---

## 🧠 Theory (4 min)

Copilot can **review your code** — pointing out bugs, unclear names, missing error handling, and style issues — both *before* you open a PR (in VS Code) and *on* the PR itself (on github.com).

Two moments to use it:

1. **Pre-flight, in VS Code** — ask Copilot to review your changes before you even push. Catch issues privately.
2. **On the pull request** — request **Copilot as a reviewer**, and it posts review comments on specific lines, like a human reviewer. In some setups it can review **automatically** on every PR.

Crucially, Copilot review **complements**, not replaces, human review and tests. It's a fast first pass that catches the obvious stuff so humans focus on the important stuff.

> Availability of Copilot code review (and automatic review) depends on your plan and repo settings, and the feature evolves. Check GitHub's current "Copilot code review" docs to enable it.

---

## 🛠️ Practice (7 min)

### Step 1 — Review changes before pushing

On your branch, in Copilot Chat:

```text
@workspace Review my changes on this branch for bugs, unclear names, missing
error handling, and edge cases. List findings as a checklist, most important first.
Don't change code — just report.
```

Fix what's worth fixing, then commit.

### Step 2 — Request Copilot review on a PR

Open a PR (Lesson 10). In the **Reviewers** section, add **Copilot** as a reviewer (where available). It analyzes the diff and posts comments.

### Step 3 — Read the review comments

Copilot leaves comments on specific lines, sometimes with **suggested changes** you can commit with one click. Treat each like a human suggestion: **evaluate**, don't blindly accept.

### Step 4 — Apply or dismiss, with judgment

- A real bug or clear improvement → apply the suggestion.
- A false positive or out-of-scope note → reply why and dismiss.

You're still the decision-maker; Copilot is an assistant reviewer.

### Step 5 — Turn on automatic review (optional)

In repo/org settings, you may be able to have Copilot **automatically review** new PRs (e.g. via a rule or the repository's Copilot settings). Great for a consistent first pass on every change.

### Step 6 — Combine review layers

The strongest setup stacks them:

```text
1) Copilot pre-flight review in VS Code
2) Tests (Lesson 6) run in CI (Lesson 17)
3) Copilot review on the PR
4) A human review
```

Each layer catches what the others miss.

---

## 🧩 Where Copilot reviews

| Where | How | Best for |
|-------|-----|----------|
| **VS Code** (pre-push) | Ask chat to review your branch | Catching issues privately, fast |
| **On the PR** | Add Copilot as a reviewer | Line-level comments + suggestions |
| **Automatic** | Repo/org rule (if enabled) | A consistent first pass on every PR |

> ⚠️ AI review misses things and raises false alarms. It's a **first pass**, not a substitute for tests and human judgment.

---

## ✅ Checkpoint

- [ ] You had Copilot review your branch in VS Code before pushing.
- [ ] You requested Copilot review on a PR and read its comments.
- [ ] You applied one good suggestion and dismissed one with a reason.
- [ ] You can explain why AI review complements (not replaces) humans + tests.

---

## 🎯 Homework

On a real PR, run the full stack: Copilot pre-flight review in VS Code, fix issues, open the PR, request Copilot review, and act on its comments with judgment. Note one thing it caught that you'd have missed — and one thing it got wrong.

---

## 💡 Key takeaways

- Copilot reviews code **in VS Code before pushing** and **on the PR** (sometimes automatically).
- It posts **line-level comments and suggestions** — evaluate each; you decide.
- AI review is a **first pass** that stacks with **tests and human review**, not a replacement.

🌐 [Polski](../../pl/lessons/13-automatyczny-przeglad-kodu.md) · [← Prev](12-great-pull-requests.md) · [Course home](../README.md) · [Next: READMEs & documentation →](14-readmes-and-docs.md)
