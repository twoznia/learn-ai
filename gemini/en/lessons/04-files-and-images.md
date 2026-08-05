# Lesson 04 — Working with Files and Images

⏱️ **10 minutes** · Level: Beginner · Needs: gemini.google.com + any PDF/image

🌐 [Polski](../../pl/lessons/04-pliki-i-obrazy.md) · [← Prev](03-prompting-basics.md) · [Course home](../README.md) · [Next: Gemini in Chrome & Google →](05-gemini-in-chrome-and-google.md)

---

## 🧠 Theory (3 min)

Gemini is **natively multimodal** — understanding text and images is built into the same model, not bolted on. You can **upload files** and Gemini reads them:

- **PDFs, docs, spreadsheets, text files** → Gemini reads the content.
- **Images and screenshots** → Gemini *sees* them (charts, photos, handwriting, error messages).

For beginners this is huge: point Gemini at a real document and say "explain this" instead of retyping.

> ⚠️ **Privacy note:** Only upload files you're comfortable sharing with a cloud service. Don't upload passwords, other people's private data, or confidential work info you're not allowed to share. More in Lesson 17.

---

## 🛠️ Practice (6 min)

### Step 1 — Summarize a PDF

1. Find any PDF (a manual, report, receipt). No PDF? In Chrome, open any page → **⋮ menu → Print → Save as PDF**.
2. In gemini.google.com, click the **➕ / upload** icon near the message box.
3. Select your PDF.
4. Send:

```text
Summarize this document in 5 bullet points. Then list any dates, names,
or amounts I should not miss. If something is unclear, say so.
```

### Step 2 — Ask questions about the file

Same chat:
```text
What is the single most important action I need to take based on this document?
```

### Step 3 — Let Gemini read a screenshot

1. Press **Windows + Shift + S** to snip part of your screen (this copies it).
2. Paste into the Gemini message box with **Ctrl + V**.
3. Try:

```text
Here's a screenshot. Explain what I'm looking at and what each button does.
```

### Step 4 — The killer beginner move: debug an error

Next time **anything** shows an error message:
1. Snip it (**Windows + Shift + S**).
2. Paste into Gemini with:

```text
I got this error on Windows. Explain in plain English what it means and give me
the safest steps to fix it. Assume I'm not technical.
```

This trick will save you countless hours.

---

## 📋 What you can upload — cheat sheet

| File type | Gemini can… |
|-----------|-------------|
| PDF / Docs / TXT | Summarize, answer questions, extract info |
| Sheets / CSV | Explain data, spot trends, suggest formulas |
| PNG / JPG screenshot | Read text, explain UI, decode errors |
| Photo of a document | Transcribe and summarize |
| Photo of handwriting | Read and type it up |

> 💡 Gemini can also handle **long** documents thanks to its large context window — try a whole report, not just a page.

---

## ✅ Checkpoint

- [ ] You uploaded a PDF and got a summary.
- [ ] You pasted a screenshot (**Win+Shift+S**, then **Ctrl+V**) and Gemini described it.
- [ ] You know the "paste the error message" trick.

---

## 🎯 Homework

Find a real document you've been avoiding (terms & conditions, a form, a dense email thread). Upload it and ask Gemini to *"explain what this means for me and what I need to do."*

---

## 💡 Key takeaways

- Gemini is multimodal — upload PDFs/docs/images and it reads/sees them.
- **Win+Shift+S** then **Ctrl+V** pastes screenshots straight into Gemini.
- Pasting error messages is the fastest way to fix computer problems.
- Never upload secrets or others' private data.

🌐 [Polski](../../pl/lessons/04-pliki-i-obrazy.md) · [← Prev](03-prompting-basics.md) · [Course home](../README.md) · [Next: Gemini in Chrome & Google →](05-gemini-in-chrome-and-google.md)
