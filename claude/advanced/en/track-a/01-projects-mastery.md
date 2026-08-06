# A1 — Projects Mastery

⏱️ **15 minutes** · Track: 🅰️ Power User · Needs: Claude (Projects; paid plan for full features)

🌐 [Polski](../../pl/track-a/01-mistrzostwo-projektow.md) · [← Track index](../README.md) · [Next: Prompt library →](02-prompt-library.md)

---

## 🧠 Theory (4 min)

In the beginner course you met **Projects** as "standing instructions + files." Now we treat a Project as a **product you design** — a specialized assistant that behaves consistently for one job.

A great Project has three layers:

1. **Role & rules** (the instructions) — *who it is and how it behaves*.
2. **Knowledge** (files) — *what it always knows*: your style guide, product list, policies, examples.
3. **Workflows** (saved prompts) — *the repeatable jobs it does*.

The mistake beginners make is stuffing everything into one giant instruction. The pro move is **separating stable knowledge (files) from behavior (instructions) from tasks (prompts)** so each part stays clean and reusable.

---

## 🛠️ Practice (9 min)

We'll build a **"Client Email Assistant"** Project end-to-end.

### Step 1 — Create the Project + role/rules

Create a new Project called **"Client Emails"**. In its instructions, paste:

```text
You are my client-communication assistant for a small design studio.

BEHAVIOR
- Tone: warm, professional, concise. British-neutral English.
- Never promise deadlines, prices, or scope I haven't confirmed.
- If a request needs info you don't have, ask me ONE clarifying question first.
- Default to 2 versions of any email: "concise" and "warm".

OUTPUT FORMAT
- Start with a one-line summary of what the email does.
- Then the email(s), each under a clear heading.
- End with "Watch-outs:" noting anything I should double-check.
```

Notice this is all **behavior** — no facts, no examples yet.

### Step 2 — Add knowledge files

Give it what it should always know. Create a small text file `studio-facts.txt` and upload it to the Project:

```text
STUDIO FACTS (reference — do not invent beyond this)
- Studio name: Northlight Design
- Services: brand identity, web design, print
- Typical project start: 2-3 weeks after deposit
- Office hours for replies: Mon-Fri, 9-17
- We never quote final prices by email without a scoping call
```

Now the assistant can reference real facts instead of guessing — and your instructions stay short.

### Step 3 — Add a style example (few-shot as a file)

Create `voice-sample.txt` with one email you're proud of, and upload it. Add one line to the instructions:

```text
- Match the voice in voice-sample.txt (greeting style, sign-off, sentence length).
```

### Step 4 — Save workflows as reusable prompts

Inside the Project, run these once and keep them in your `my-prompts.txt`:

```text
Draft a reply to this client email. Use studio facts and my voice.

CLIENT EMAIL:
<paste>

MY ROUGH INTENT:
<a few words>
```

```text
The client is unhappy about a delay. Write an apology that stays professional,
takes responsibility without over-promising, and offers one concrete next step.

CONTEXT:
<paste>
```

### Step 5 — Test that the layers work together

Paste a real (or made-up) client email and check:
- Did it use a **fact** from `studio-facts.txt`?
- Did it match the **voice** sample?
- Did it follow the **format** (summary → emails → Watch-outs)?

If one layer is weak, fix *that layer* — usually the file, not the instructions.

---

## 🧩 The design principle

| Put this… | …in this layer | Why |
|-----------|----------------|-----|
| How it should behave | Instructions | Rarely changes; short |
| Facts it must not invent | Knowledge files | Update files, not prompts |
| Voice/format examples | Knowledge files | Show, don't describe |
| The repeatable jobs | Saved prompts | Reuse across chats |

---

## ✅ Checkpoint

- [ ] Your Project has instructions **and** at least one knowledge file.
- [ ] The assistant referenced a fact from a file.
- [ ] You saved at least two reusable workflow prompts.

---

## 🎯 Homework

Build a **second** Project for a different real job in your life (study, side business, a hobby). Reuse the three-layer pattern: role/rules → knowledge files → saved workflows.

---

## 💡 Key takeaways

- A strong Project = **behavior (instructions) + knowledge (files) + workflows (prompts)**, kept separate.
- Put facts in files so Claude stops guessing and your instructions stay short.
- Fix the weak *layer*, not the whole prompt.

🌐 [Polski](../../pl/track-a/01-mistrzostwo-projektow.md) · [← Track index](../README.md) · [Next: Prompt library →](02-prompt-library.md)
