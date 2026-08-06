# Lesson 08 — Install Python on Windows

⏱️ **10 minutes** · Level: Beginner · Needs: Windows 10/11, internet

🌐 [Polski](../../pl/lessons/08-instalacja-python.md) · [← Prev](07-custom-gpts-and-projects.md) · [Course home](../README.md) · [Next: Get your API key →](09-get-api-key.md)

---

## 🧠 Theory (2 min)

**Python** is a programming language that reads almost like English. It's the #1 language for AI, and OpenAI provides an official Python library (`openai`) that makes talking to GPT easy. You won't need to "become a programmer" — you'll copy small scripts and run them.

Two words you'll see:
- **Python** — the program that runs your code.
- **pip** — Python's tool for installing add-on libraries. It comes *with* Python.

---

## 🛠️ Practice (7 min)

### Step 1 — Install Python

**Easiest (winget):** open **PowerShell** (Start → type *PowerShell* → Enter) and run:

```powershell
winget install --id Python.Python.3.12 -e
```

**Or the classic way:**
1. Go to **https://www.python.org/downloads/**
2. Click the big **Download Python** button.
3. Run the installer, and **‼️ CHECK THE BOX "Add python.exe to PATH"** at the bottom before clicking **Install Now**. This one checkbox prevents 90% of beginner headaches.

### Step 2 — Close and reopen PowerShell

After installing, **close PowerShell and open a fresh window** so it picks up the new Python.

### Step 3 — Verify it works

```powershell
python --version
```

You should see something like `Python 3.12.x`. Then:

```powershell
pip --version
```

You should see a `pip 24.x ...` line. ✅ Both working = you're set.

> **If `python` opens the Microsoft Store** instead: Start → **Manage app execution aliases** → turn **OFF** the toggles for **python.exe** and **python3.exe**. Reopen PowerShell and try again. (Or reinstall with the *Add to PATH* box checked.)

### Step 4 — Run your first line of Python

```powershell
python -c "print('Hello from Python! You are ready for AI.')"
```

If you see the message printed, everything works. 🎉

---

## 🗂️ Make a folder for this course

```powershell
mkdir $HOME\learn-ai-gpt
cd $HOME\learn-ai-gpt
```

`$HOME` is your user folder (like `C:\Users\YourName`). You'll put all lesson scripts here.

---

## ✅ Checkpoint

- [ ] `python --version` shows Python 3.x.
- [ ] `pip --version` works.
- [ ] The "Hello from Python" line printed.
- [ ] You created a `learn-ai-gpt` folder.

---

## 🎯 Homework

If anything threw an error, use the Lesson-4 trick: snip the error (**Win+Shift+S**), paste it into ChatGPT, and ask *"How do I fix this Python install error on Windows? I'm a beginner."*

---

## 💡 Key takeaways

- Install Python via `winget install --id Python.Python.3.12 -e` **or** python.org (check **Add to PATH**).
- Always **reopen** your terminal after installing.
- Verify with `python --version` and `pip --version`.
- `pip` installs libraries; it comes with Python.

🌐 [Polski](../../pl/lessons/08-instalacja-python.md) · [← Prev](07-custom-gpts-and-projects.md) · [Course home](../README.md) · [Next: Get your API key →](09-get-api-key.md)
