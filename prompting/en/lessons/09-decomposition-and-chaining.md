# Lesson 09 — Decomposition & Prompt Chaining

⏱️ **12 minutes** · Level: Intermediate → Advanced · Needs: any AI chat

🌐 [Polski](../../pl/lessons/09-dekompozycja-i-lancuchy.md) · [← Prev](08-step-by-step-reasoning.md) · [Course home](../README.md) · [Next: Controlling output →](10-controlling-output.md)

---

## 🧠 Theory (4 min)

Big, complex asks in one giant prompt often produce mediocre results — the model juggles too much at once. **Decomposition** is breaking the task into smaller steps; **prompt chaining** is feeding the output of one step into the next.

Two ways to do it:

- **One structured prompt, sequenced** — "Do step 1, then 2, then 3," so the model tackles them in order (builds on Lesson 8).
- **Multiple prompts chained** — you run a prompt, take its output, and use it as the input to the next prompt. Each step is focused and reviewable.

Chaining shines for real workflows: **outline → draft → critique → revise**, or **extract → analyze → summarize**. You get to inspect (and fix) each stage instead of hoping one mega-prompt nails everything.

---

## 🛠️ Practice (7 min)

### Step 1 — Decompose in a single prompt

```text
Write a blog post in stages, showing each:
1. A 5-point outline.
2. A draft from that outline.
3. Three specific improvements you'd make.
4. The final revised version.
```

### Step 2 — Chain across separate prompts

Prompt 1:

```text
Give me a 5-point outline for a post on "backing up your PC."
```

Review/edit the outline, then Prompt 2:

```text
Here is the outline: [paste]. Write a 300-word draft following it exactly.
```

Then Prompt 3:

```text
Critique this draft for clarity and cut 15%: [paste].
```

You controlled and improved each stage.

### Step 3 — Use one output as another's input

```text
Extract all action items from these meeting notes as a list.
```

Then:

```text
For each action item above, draft a one-line Slack message to the owner.
```

### Step 4 — Add a review step

Always insert a checkpoint you can act on:

```text
Before finalizing, list any assumptions you made and anything that's unclear.
```

### Step 5 — Know when one prompt is enough

Small tasks don't need chaining. Reach for it when a task has **distinct stages**, each worth reviewing.

---

## 🧩 Common chains

| Workflow | Chain |
|----------|-------|
| Writing | Outline → draft → critique → revise |
| Research | Gather → extract → analyze → summarize |
| Data | Parse → transform → validate → report |
| Decisions | Options → weigh → recommend → plan |

---

## ✅ Checkpoint

- [ ] You broke a big task into ordered steps in one prompt.
- [ ] You chained separate prompts, feeding output into input.
- [ ] You reviewed/edited an intermediate result before continuing.
- [ ] You can name a task that needs chaining vs one that doesn't.

---

## 🎯 Homework

Pick something you'd normally ask for in one shot (a report, a plan, an article). Do it as a chain of at least three prompts, reviewing each stage. Compare the final result to a single mega-prompt version — note where reviewing mid-way improved it.

---

## 💡 Key takeaways

- **Decompose** complex tasks into steps; **chain** prompts by feeding one output into the next.
- Chaining lets you **inspect and fix each stage** instead of trusting one giant prompt.
- Use it when a task has **distinct, review-worthy stages**; skip it for small asks.

🌐 [Polski](../../pl/lessons/09-dekompozycja-i-lancuchy.md) · [← Prev](08-step-by-step-reasoning.md) · [Course home](../README.md) · [Next: Controlling output →](10-controlling-output.md)
