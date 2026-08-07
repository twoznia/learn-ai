# Lesson 07 — Role & System Prompts

⏱️ **11 minutes** · Level: Intermediate · Needs: any AI chat

🌐 [Polski](../../pl/lessons/07-role-i-prompty-systemowe.md) · [← Prev](06-few-shot-prompting.md) · [Course home](../README.md) · [Next: Step-by-step reasoning →](08-step-by-step-reasoning.md)

---

## 🧠 Theory (4 min)

Telling the AI **who to be** shapes *how* it answers. A **role** (or persona) sets the voice, depth, and priorities in one line — "You are a skeptical editor," "You are a friendly kindergarten teacher," "You are a senior security engineer."

There are two places a role can live:

- **In your message** — "Act as a nutritionist and…" Works in any chat.
- **In a system prompt / custom instructions** — a standing role that applies to *every* message: ChatGPT's custom instructions, Claude's Projects/system prompt, Gemini's Gems/saved info. Set it once; it persists.

A role isn't magic — it won't give the model knowledge it lacks. But it reliably steers **tone, level of detail, and what the model prioritizes**, which is often exactly what you need.

---

## 🛠️ Practice (6 min)

### Step 1 — Set a role in the message

```text
You are a patient tutor for absolute beginners. Explain what an API is using a
restaurant analogy, then a one-sentence technical definition.
```

### Step 2 — Change the role, same task

```text
You are a senior backend engineer briefing a colleague. Explain what an API is,
assuming they know programming. Be precise and concise.
```

Same topic, very different answer — you're steering with the role.

### Step 3 — Add priorities to the role

A role can carry values:

```text
You are a careful medical writer. Prioritize accuracy over fluency, flag
uncertainty explicitly, and never state something you're unsure of as fact.
```

### Step 4 — Make it standing (system / custom instructions)

Put a role you reuse into your tool's persistent settings:

```text
Always respond as a concise, practical mentor. Lead with the answer, then a
short "why." I'm on Windows. Avoid filler and hype.
```

Now every new chat starts in that voice.

### Step 5 — Combine role + format + constraints

Roles stack with earlier lessons:

```text
You are a UX writer. Rewrite these 3 error messages to be friendly and clear,
under 12 words each, no blame language. Return a table: Original | Rewrite.
```

---

## 🧩 Where roles live

| Place | Scope | Examples |
|-------|-------|----------|
| In the message | This chat/turn | "Act as a…" |
| System / custom instructions | Every chat | ChatGPT custom instructions, Claude Projects, Gemini Gems |
| A saved assistant | A reusable persona | Custom GPT, Gem, Claude Project |

> A role steers **tone, depth, priorities** — not knowledge. Pair it with real context (Lesson 4) when facts matter.

---

## ✅ Checkpoint

- [ ] You set a role in a message and saw it shape the answer.
- [ ] You changed only the role and got a very different response.
- [ ] You added priorities/values to a role.
- [ ] You set a standing role in your tool's persistent settings.

---

## 🎯 Homework

Write one standing role for how you want the AI to talk to you (tone, depth, what to avoid) and put it in your tool's custom instructions / persona. Use it for a day and refine the wording until answers feel right by default.

---

## 💡 Key takeaways

- A **role** sets voice, depth, and priorities in one line — steering *how* the AI answers.
- Roles can be **per-message** or **standing** (system prompts / custom instructions / saved assistants).
- A role shapes **tone and priorities, not knowledge** — combine it with real context.

🌐 [Polski](../../pl/lessons/07-role-i-prompty-systemowe.md) · [← Prev](06-few-shot-prompting.md) · [Course home](../README.md) · [Next: Step-by-step reasoning →](08-step-by-step-reasoning.md)
