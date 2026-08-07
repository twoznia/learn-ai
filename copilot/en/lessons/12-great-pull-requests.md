# Lesson 12 — Writing Great Pull Requests with Copilot

⏱️ **12 minutes** · Level: Intermediate · Needs: a GitHub repo + Copilot

🌐 [Polski](../../pl/lessons/12-swietne-pull-requesty.md) · [← Prev](11-issues-labels-projects.md) · [Course home](../README.md) · [Next: Automatic code review →](13-automatic-code-review.md)

---

## 🧠 Theory (4 min)

A great PR is **easy to review**: a clear title, a description that explains *what* and *why*, a sensible size, and good commit messages. Copilot helps with every part — turning "here's a diff, good luck" into a PR a reviewer can approve quickly.

What makes a PR reviewable:

- **Small and focused** — one logical change, not ten.
- **A title that summarizes the change** (not "updates" or "fixes").
- **A description**: what changed, why, how to test, and any risks.
- **Clean commits** with meaningful messages.

Copilot can write the commit messages, generate the PR **summary/description**, and even suggest a good title.

---

## 🛠️ Practice (7 min)

### Step 1 — Let Copilot write your commit message

In VS Code's **Source Control** panel, stage your changes. Look for the **sparkle / Copilot icon** on the commit message box — click it to **generate a commit message** from your diff. Edit if needed, then commit.

### Step 2 — Keep the PR focused

Before opening a PR, ask:

```text
@workspace Look at my changes on this branch. Are they one focused change, or
should this be split into separate PRs? Be specific.
```

### Step 3 — Generate the PR description

Open the PR (github.com or the VS Code **GitHub Pull Requests** extension). On github.com, the description box often has a **Copilot "Summary"** option that drafts a description from the diff. Or ask Copilot Chat:

```text
Write a pull request description for these changes: a "What" section, a "Why"
section, a "How to test" checklist, and any risks. Keep it concise.
```

### Step 4 — Write a strong title

```text
Suggest 3 clear, specific PR titles for this change, under 70 characters each.
```

Pick the one that best summarizes the change.

### Step 5 — Add a "how to test" section

Reviewers love this. Include exact commands:

```text
Add a "How to test" section with the exact PowerShell commands to run and what
the expected output is.
```

### Step 6 — Link the issue

In the description, write **"Closes #1"** so the issue closes automatically on merge — connecting the work to the plan from Lesson 11.

---

## 🧩 Anatomy of a reviewable PR

| Part | Good version |
|------|--------------|
| **Title** | "Add --language flag to CLI (en/pl)" |
| **What** | One-paragraph summary of the change |
| **Why** | The problem it solves / issue link |
| **How to test** | Exact commands + expected result |
| **Risks** | Anything reviewers should scrutinize |
| **Commits** | Small, with meaningful messages |

> ⚠️ Copilot drafts the description from the diff — **read and correct it**. It describes *what changed*, but only *you* know the full *why*.

---

## ✅ Checkpoint

- [ ] You generated a commit message with Copilot.
- [ ] You checked whether your PR should be split.
- [ ] You generated a PR description (What / Why / How to test / Risks).
- [ ] You linked an issue with "Closes #N".

---

## 🎯 Homework

Open a real PR for a change on your repo. Use Copilot to generate the commit message and a full description, write a strong title, and add a "How to test" section. Ask a friend (or re-read it yourself tomorrow) — could they review it without asking questions?

---

## 💡 Key takeaways

- Great PRs are **small, clearly titled, and well-described** (what / why / how to test / risks).
- Copilot generates **commit messages, PR descriptions, and titles** from your diff.
- Always **review Copilot's draft** — it knows the *what*, you supply the *why* — and link issues with **"Closes #N"**.

🌐 [Polski](../../pl/lessons/12-swietne-pull-requesty.md) · [← Prev](11-issues-labels-projects.md) · [Course home](../README.md) · [Next: Automatic code review →](13-automatic-code-review.md)
