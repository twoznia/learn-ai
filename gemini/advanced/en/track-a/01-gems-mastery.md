# A1 — Gems Mastery

⏱️ **15 minutes** · Track: 🅰️ Power User · Needs: Gemini app (Gems)

🌐 [Polski](../../pl/track-a/01-mistrzostwo-gems.md) · [← Track index](../README.md) · [Next: Prompt library →](02-prompt-library.md)

---

## 🧠 Theory (4 min)

In the beginner course you met **Gems** as "custom assistants with standing instructions." Now we treat a Gem as a **product you design** — a specialized assistant that behaves consistently for one job.

A great Gem has three layers:

1. **Role & rules** (instructions) — *who it is and how it behaves*.
2. **Knowledge** (files/context) — *what it always knows*: facts, style, policies, examples.
3. **Workflows** (saved prompts) — *the repeatable jobs it does*.

The beginner mistake is one giant instruction. The pro move is **separating stable knowledge from behavior from tasks** so each stays clean and reusable.

---

## 🛠️ Practice (9 min)

We'll build a **"Client Email Assistant"** Gem end-to-end.

### Step 1 — Create the Gem + role/rules

In the Gemini app, create a **New Gem** called **"Client Emails"**. In its instructions, paste:

```text
You are my client-communication assistant for a small design studio.

BEHAVIOR
- Tone: warm, professional, concise.
- Never promise deadlines, prices, or scope I haven't confirmed.
- If a request needs info you don't have, ask me ONE clarifying question first.
- Default to 2 versions of any email: "concise" and "warm".

OUTPUT FORMAT
- Start with a one-line summary of what the email does.
- Then the email(s), each under a clear heading.
- End with "Watch-outs:" noting anything I should double-check.
```

This is all **behavior** — no facts yet.

### Step 2 — Add knowledge (facts it must not invent)

Gems can take reference files or a "knowledge" block. Add this as an uploaded `studio-facts.txt` or paste it into the instructions under a `FACTS` heading:

```text
STUDIO FACTS (reference — do not invent beyond this)
- Studio name: Northlight Design
- Services: brand identity, web design, print
- Typical project start: 2-3 weeks after deposit
- We never quote final prices by email without a scoping call
```

Now it references real facts instead of guessing.

### Step 3 — Add a voice example

Give it one email you're proud of (as a file or pasted example), and add:

```text
- Match the voice in the example: greeting style, sign-off, sentence length.
```

### Step 4 — Save workflows as reusable prompts

Keep these in your `my-prompts.txt`:

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

### Step 5 — Test the layers together

Paste a real (or made-up) client email and check:
- Did it use a **fact**?
- Did it match the **voice**?
- Did it follow the **format**?

Fix the weak *layer* — usually the knowledge, not the instructions.

---

## 🧩 The design principle

| Put this… | …in this layer | Why |
|-----------|----------------|-----|
| How it behaves | Instructions | Rarely changes; short |
| Facts it must not invent | Knowledge/files | Update the facts, not prompts |
| Voice/format examples | Knowledge/files | Show, don't describe |
| The repeatable jobs | Saved prompts | Reuse across chats |

---

## ✅ Checkpoint

- [ ] Your Gem has instructions **and** a knowledge/facts layer.
- [ ] It referenced a fact you provided.
- [ ] You saved at least two reusable workflow prompts.

---

## 🎯 Homework

Build a **second** Gem for a different real job (study, side business, a hobby). Reuse the three-layer pattern.

---

## 💡 Key takeaways

- A strong Gem = **behavior + knowledge + workflows**, kept separate.
- Put facts in the knowledge layer so Gemini stops guessing.
- Fix the weak *layer*, not the whole prompt.

🌐 [Polski](../../pl/track-a/01-mistrzostwo-gems.md) · [← Track index](../README.md) · [Next: Prompt library →](02-prompt-library.md)
