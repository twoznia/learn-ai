# A1 — Custom GPTs Mastery

⏱️ **15 minutes** · Track: 🅰️ Power User · Needs: ChatGPT (Custom GPTs; usually a paid plan to build)

🌐 [Polski](../../pl/track-a/01-mistrzostwo-custom-gpt.md) · [← Track index](../README.md) · [Next: Prompt library →](02-prompt-library.md)

---

## 🧠 Theory (4 min)

In the beginner course you met **Custom GPTs** as "a saved ChatGPT with its own instructions." Now we treat a Custom GPT as a **product you design** — a specialized assistant that behaves consistently for one job.

A great Custom GPT has three layers:

1. **Role & rules** (instructions) — *who it is and how it behaves*.
2. **Knowledge** (uploaded files) — *what it always knows*: facts, style, policies, examples.
3. **Workflows** (saved prompts + conversation starters) — *the repeatable jobs it does*.

The beginner mistake is one giant instruction. The pro move is **separating stable knowledge from behavior from tasks**.

---

## 🛠️ Practice (9 min)

We'll build a **"Client Email Assistant"** GPT.

### Step 1 — Create the GPT + role/rules

In ChatGPT, go to **Explore GPTs → Create** (the GPT Builder). Switch to the **Configure** tab and name it **"Client Emails"**. In **Instructions**, paste:

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

### Step 2 — Add knowledge files

Under **Knowledge**, upload a `studio-facts.txt`:

```text
STUDIO FACTS (reference — do not invent beyond this)
- Studio name: Northlight Design
- Services: brand identity, web design, print
- Typical project start: 2-3 weeks after deposit
- We never quote final prices by email without a scoping call
```

Now it references real facts instead of guessing.

### Step 3 — Add a voice example + conversation starters

Upload one email you're proud of as `voice-sample.txt`, and add to Instructions:

```text
- Match the voice in voice-sample.txt: greeting style, sign-off, sentence length.
```

Add **Conversation starters** (the buttons users see):
- "Draft a reply to a client email"
- "Write an apology for a delay"

### Step 4 — Save workflows

Keep these in `my-prompts.txt` too:

```text
Draft a reply to this client email. Use studio facts and my voice.

CLIENT EMAIL:
<paste>

MY ROUGH INTENT:
<a few words>
```

### Step 5 — Test the layers together

Open your GPT, paste a real (or made-up) client email, and check:
- Did it use a **fact** from the file?
- Did it match the **voice**?
- Did it follow the **format**?

Fix the weak *layer* — usually the knowledge file, not the instructions.

> No plan to build GPTs? Use **custom instructions** (Settings → Personalization) for global behavior, and save the workflows as prompts. Same three-layer thinking.

---

## 🧩 The design principle

| Put this… | …in this layer | Why |
|-----------|----------------|-----|
| How it behaves | Instructions | Rarely changes; short |
| Facts it must not invent | Knowledge files | Update files, not prompts |
| Voice/format examples | Knowledge files | Show, don't describe |
| The repeatable jobs | Prompts + starters | Reuse across chats |

---

## ✅ Checkpoint

- [ ] Your Custom GPT has instructions **and** at least one knowledge file.
- [ ] It referenced a fact from a file.
- [ ] You added conversation starters and saved a workflow prompt.

---

## 🎯 Homework

Build a **second** Custom GPT (or custom-instructions setup) for a different real job. Reuse the three-layer pattern.

---

## 💡 Key takeaways

- A strong Custom GPT = **behavior + knowledge files + workflows**, kept separate.
- Put facts in files so ChatGPT stops guessing.
- Fix the weak *layer*, not the whole prompt.

🌐 [Polski](../../pl/track-a/01-mistrzostwo-custom-gpt.md) · [← Track index](../README.md) · [Next: Prompt library →](02-prompt-library.md)
