# A2 — Build a Prompt Library

⏱️ **15 minutes** · Track: 🅰️ Power User · Needs: a text editor (Notepad is fine)

🌐 [Polski](../../pl/track-a/02-biblioteka-promptow.md) · [← Prev](01-gems-mastery.md) · [Track index](../README.md) · [Next: Deep Research & Canvas →](03-deep-research-canvas.md)

---

## 🧠 Theory (4 min)

You've been saving prompts to `my-prompts.txt`. A **library** is organized so you find and reuse the right prompt in seconds. The difference between "some saved prompts" and a real library is **structure + templates + versioning**.

1. **Templates with slots** — clearly-marked blanks (`<like_this>`) you fill and fire.
2. **Categories** — group by job (Write, Summarize, Analyze, Decide).
3. **Versioning** — keep old versions so you can compare after improving one.

A plain folder of text files is all you need.

---

## 🛠️ Practice (9 min)

### Step 1 — Create the library folder

```powershell
mkdir $HOME\prompt-library
cd $HOME\prompt-library
mkdir write, summarize, analyze, decide
```

### Step 2 — Write your first template

Create `write\email-reply.md`:

```text
# Email reply
# Version: 1  |  Last good result: (date)

Role: You are my communication assistant.
Task: Write a reply to the email below.
Constraints:
- Under 5 sentences, warm-but-professional.
- Two versions: concise and warm.
- Don't promise anything I haven't confirmed.

EMAIL:
<paste the email>

MY INTENT:
<a few words>
```

### Step 3 — Add a "decision" template

Create `decide\weigh-options.md`:

```text
# Weigh options
# Version: 1

Help me decide between the options below.
1. List each option's top 2 pros and top 2 cons.
2. Note the biggest risk of each.
3. Give a recommendation in one sentence, and say what would change your mind.

OPTIONS:
<option A>
<option B>
```

### Step 4 — Make an index

Create `README.md` in the library root:

```text
# My Prompt Library

## write/
- email-reply.md — replies to emails, 2 versions

## decide/
- weigh-options.md — compare 2+ options with a recommendation
```

### Step 5 — Version a prompt

When you improve a template, keep a backup first:

```powershell
copy write\email-reply.md write\email-reply-v1-backup.md
```

Then bump the main file to Version 2 — now improvements are reversible.

> 💡 **Bonus:** attach this folder to a Gem as reference. Then ask *"which of my saved prompts fits this task?"* and Gemini picks from your own library.

---

## 🧩 What "good" looks like

| Weak library | Strong library |
|--------------|----------------|
| One giant text file | Folders by job |
| Must rewrite each time | Clear `<slots>` to fill |
| Overwrite when improving | Versioned with backups |
| Can't find the right prompt | An index you scan in seconds |

---

## ✅ Checkpoint

- [ ] A `prompt-library` folder with category subfolders.
- [ ] At least two templates with clear `<slots>`.
- [ ] An index file listing what's inside.

---

## 🎯 Homework

Migrate every prompt you've collected into the library, sorted into categories. Delete duplicates. Add one new template for the task you do most.

---

## 💡 Key takeaways

- A library = **templates + categories + versioning**, in a plain folder.
- Version prompts (keep backups) so improvements are reversible.
- Attach the library to a Gem so Gemini can pick the right prompt.

🌐 [Polski](../../pl/track-a/02-biblioteka-promptow.md) · [← Prev](01-gems-mastery.md) · [Track index](../README.md) · [Next: Deep Research & Canvas →](03-deep-research-canvas.md)
