# Lesson 18 — Costs, Limits, Privacy & Where to Go Next

⏱️ **10 minutes** · Level: All levels · Needs: nothing new

🌐 [Polski](../../pl/lessons/18-koszty-limity-i-kolejne-kroki.md) · [← Prev](17-copilot-cli-and-actions.md) · [Course home](../README.md) · [↩ All courses](../../../README.md)

---

## 🧠 Theory (4 min)

You can now use Copilot across VS Code, GitHub, PRs, review, and automation. Let's finish with using it **responsibly and sustainably**.

- **Plans & limits** — Free has monthly caps on completions and chat; Pro/Business lift them. Heavy features (agent, premium models) may draw on a **request/usage allowance**. Know your plan's limits.
- **Privacy** — Copilot sends relevant code/context to the service to generate suggestions. Business/Enterprise offer admin controls (and options like excluding files). Never paste secrets; use a `.gitignore` and repo settings to keep them out.
- **Quality & responsibility** — Copilot can be wrong, suggest insecure code, or reproduce patterns that need a license check. **You own every line you merge.**

The mindset: Copilot is a fast, powerful assistant — and **you are the engineer** who reviews, tests, and takes responsibility.

---

## 🛠️ Practice (5 min)

### Step 1 — Check your usage and limits

In GitHub **Settings → Copilot**, review your plan, what's included, and any usage indicators. Know when you're near a cap.

### Step 2 — Set content exclusions (if available)

On Business/Enterprise (or repo settings), configure **content exclusions** so Copilot ignores sensitive files. At minimum, keep secrets out of the repo entirely.

### Step 3 — Protect secrets

```powershell
notepad .gitignore
```

Add lines like `.env` and any secret files. Enable **secret scanning** / **push protection** in repo settings so tokens can't be pushed by accident.

### Step 4 — Adopt a review habit

Commit to this rule: **read every suggestion, run the tests, review every PR** — including Copilot's own. Speed without review is how bugs ship.

### Step 5 — Build your setup

Bring your habits together into a reusable setup:
- A `.github/copilot-instructions.md` per project (Lesson 7).
- Tests + a CI workflow (Lessons 6, 17).
- Copilot review on PRs (Lesson 13).

### Step 6 — Plan what's next

Pick your next step from the roadmap below and put it on a project board.

---

## 🗺️ Where to go next

| Path | Do this |
|------|---------|
| **Go deeper in VS Code** | Master Edit/Agent mode on a real project |
| **Automate reviews** | Enable Copilot review + CI on all your repos |
| **Delegate more** | Practice the coding agent on scoped issues |
| **Customize** | Refine instructions, explore chat modes & extensions |
| **Learn the models** | Try different models; see the AI courses in this repo |

> Pair this course with the **Claude / Gemini / ChatGPT** courses in this repo to understand the models *behind* assistants like Copilot.

---

## ✅ Checkpoint

- [ ] You know your plan's limits and where to check usage.
- [ ] Secrets are protected (`.gitignore`, secret scanning).
- [ ] You've committed to a read-test-review habit.
- [ ] You picked a concrete next step.

---

## 🎯 Homework

Set up **one** repo as your "gold standard": custom instructions, tests with CI, Copilot review on PRs, and a clean README. This becomes the template for how you work with Copilot from now on. Then revisit the goal you wrote in Lesson 1 — can you do it now?

---

## 💡 Key takeaways

- Know your **plan's limits**, protect **secrets**, and understand that context is sent to generate suggestions.
- **You own every line you merge** — read suggestions, run tests, review every PR (including Copilot's).
- Build a reusable setup (**instructions + tests/CI + review + README**) and keep learning the models behind the tools.

🌐 [Polski](../../pl/lessons/18-koszty-limity-i-kolejne-kroki.md) · [← Prev](17-copilot-cli-and-actions.md) · [Course home](../README.md) · [↩ All courses](../../../README.md)
