# A2 — Build a Prompt Library

⏱️ **15 minutes** · Track: 🅰️ Power User · Needs: a text editor (Notepad is fine)

🌐 [Polski](../../pl/track-a/02-biblioteka-promptow.md) · [← Prev](01-projects-mastery.md) · [Track index](../README.md) · [Next: Advanced MCP →](03-advanced-mcp.md)

---

## 🧠 Theory (4 min)

You've been saving prompts to `my-prompts.txt`. That's a start — but a **library** is organized so you can find and reuse the right prompt in seconds. The difference between "some saved prompts" and a real library is **structure + templates + versioning**.

Three ideas:

1. **Templates with slots.** A good library prompt has clearly-marked blanks (`<like_this>`) so you fill and fire.
2. **Categories.** Group by job (Write, Summarize, Analyze, Decide) so you scan fast.
3. **Versioning.** When you improve a prompt, keep the old one so you can compare.

You can build this in a plain folder of text files — no app needed.

---

## 🛠️ Practice (9 min)

### Step 1 — Create the library folder

In PowerShell:

```powershell
mkdir $HOME\prompt-library
cd $HOME\prompt-library
mkdir write, summarize, analyze, decide
```

### Step 2 — Write your first template

Create `write\email-reply.md`:

```powershell
notepad write\email-reply.md
```

Paste this template:

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

The header comments (`# Version`, `# Last good result`) are your versioning notes.

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

## summarize/
- (add as you go)

## analyze/
- (add as you go)

## decide/
- weigh-options.md — compare 2+ options with a recommendation
```

### Step 5 — Version a prompt (the pro habit)

When you improve `email-reply.md`, don't overwrite blindly. Bump the version and keep a note:

```powershell
copy write\email-reply.md write\email-reply-v1-backup.md
```

Then edit the main file to Version 2. Now you can compare if v2 ever feels worse.

> 💡 **Bonus:** put this whole folder in a Claude **Project** as knowledge files. Then you can ask Claude *"which of my saved prompts fits this task?"* and it will pick from your own library.

---

## 🧩 What "good" looks like

| Sign of a weak library | Sign of a strong one |
|------------------------|----------------------|
| One giant text file | Folders by job |
| No blanks, must rewrite each time | Clear `<slots>` to fill |
| Overwrite when improving | Versioned with backups |
| Can't find the right prompt | An index you scan in seconds |

---

## ✅ Checkpoint

- [ ] You have a `prompt-library` folder with category subfolders.
- [ ] At least two templates with clear `<slots>`.
- [ ] An index file listing what's inside.

---

## 🎯 Homework

Migrate every prompt you've collected so far into the library, sorted into categories. Delete duplicates. Add one new template for the task you do most.

---

## 💡 Key takeaways

- A library = **templates with slots + categories + versioning**, in a plain folder.
- Version prompts (keep backups) so improvements are reversible.
- Load the library into a Project so Claude can pick the right prompt for you.

🌐 [Polski](../../pl/track-a/02-biblioteka-promptow.md) · [← Prev](01-projects-mastery.md) · [Track index](../README.md) · [Next: Advanced MCP →](03-advanced-mcp.md)
