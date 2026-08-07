# Lesson 04 — Context & the Context Window

⏱️ **11 minutes** · Level: Beginner → Intermediate · Needs: any AI chat

🌐 [Polski](../../pl/lessons/04-kontekst-i-okno-kontekstowe.md) · [← Prev](03-be-specific.md) · [Course home](../README.md) · [Next: Structure & formatting →](05-structure-and-formatting.md)

---

## 🧠 Theory (4 min)

An LLM only knows what's **in front of it** — the current conversation. That's the **context**, and it lives in a fixed-size **context window**. Two consequences shape good prompting:

- **Missing context = guessing.** If the AI needs a fact to answer well (your product, the audience, a document), you must **provide it**. It can't fetch what you didn't give.
- **Too much context = noise (and cost).** Dumping 50 pages to ask about one paragraph buries the signal, and the whole thing is re-read every turn — slower and, on paid plans, more expensive.

The skill is **curation**: include exactly the context that changes the answer, and nothing else. Relevant in, irrelevant out.

> Every model has a context limit. Very long chats can push early details out of view — the model may "forget" the start. Restate key facts or start fresh when that happens.

---

## 🛠️ Practice (6 min)

### Step 1 — Provide the missing fact

Weak (AI must guess your stack):

```text
Write a function to save user settings.
```

Strong (context supplied):

```text
In a Python 3 project using SQLite, write a function save_settings(user_id, settings_dict)
that upserts a row in a "settings" table. Match this existing style: [paste 5 lines].
```

### Step 2 — Paste the relevant part, not everything

Don't paste a whole report to ask about one section — **paste the section**. Or summarize the rest:

```text
Here is the relevant paragraph: "…". Given only this, answer: …
```

### Step 3 — Front-load what matters

Put the key instruction and the most important context **near the top** of a long prompt, so it isn't buried.

### Step 4 — Carry a summary across chats

Starting a fresh chat to continue work? Bring a compact handoff, not the whole history:

```text
Summarize our decisions and current state in under 150 words so I can paste it
into a new chat.
```

### Step 5 — Notice "forgetting"

In a very long conversation, if the AI loses an early detail, that's the window filling. Restate the fact or start a fresh chat with your summary.

---

## 🧩 Context: include vs cut

| Include | Cut |
|---------|-----|
| Facts the AI can't know (your data, audience) | Background it already knows |
| The specific text you're asking about | Unrelated pages "for completeness" |
| Style examples you want matched | Long history once summarized |
| Constraints and goals | Repetition and filler |

---

## ✅ Checkpoint

- [ ] You supplied a missing fact instead of letting the AI guess.
- [ ] You pasted the relevant part rather than everything.
- [ ] You front-loaded the key instruction/context.
- [ ] You can explain what happens when a chat gets very long.

---

## 🎯 Homework

Take a task that depends on your own information. Write the prompt with just enough context to answer well — then try removing one piece and see if the answer degrades. That tells you what was actually load-bearing.

---

## 💡 Key takeaways

- The AI only knows the **current context** — supply what it needs, cut what it doesn't.
- **Curate**: relevant facts and the specific text in; irrelevant bulk out (it adds noise and cost).
- Long chats can push early details out of the **window** — restate key facts or start fresh with a summary.

🌐 [Polski](../../pl/lessons/04-kontekst-i-okno-kontekstowe.md) · [← Prev](03-be-specific.md) · [Course home](../README.md) · [Next: Structure & formatting →](05-structure-and-formatting.md)
