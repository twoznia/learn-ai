# Lesson 08 — Install Python on Windows

⏱️ **10 minutes** · Level: Beginner · Needs: Windows 10/11, internet

[← Prev](07-projects-and-memory.md) · [Course home](../README.md) · [Next: Get your API key →](09-get-api-key.md)

---

## 🧠 Theory (2 min)

**Python** is a programming language that reads almost like English. It's the #1 language for AI, and Anthropic provides an official Python library that makes talking to Claude easy. Don't worry — you won't need to "become a programmer." You'll copy small scripts and run them.

Two words you'll see:
- **Python** — the language/program that runs your code.
- **pip** — Python's tool for installing add-on libraries (like the Anthropic one). It comes *with* Python.

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

Important: after installing, **close PowerShell and open a fresh window** so it picks up the new Python.

### Step 3 — Verify it works

Paste each line and press Enter:

```powershell
python --version
```

You should see something like `Python 3.12.x`. Then:

```powershell
pip --version
```

You should see a `pip 24.x ...` line. ✅ Both working = you're set.

> **If `python` opens the Microsoft Store** instead: Windows has "app execution aliases" hijacking the command. Fix: Start → **Manage app execution aliases** → turn **OFF** the toggles for **App Installer / python.exe** and **python3.exe**. Reopen PowerShell and try again. (Or reinstall with the *Add to PATH* box checked.)

### Step 4 — Run your first line of Python

```powershell
python -c "print('Hello from Python! You are ready for AI.')"
```

If you see the message printed, everything works. 🎉

---

## 🗂️ Make a folder for this course

Keep your scripts tidy. Run:

```powershell
mkdir $HOME\learn-ai-claude
cd $HOME\learn-ai-claude
```

`$HOME` is your user folder (like `C:\Users\YourName`). You'll put all lesson scripts here.

---

## ✅ Checkpoint

- [ ] `python --version` shows Python 3.x.
- [ ] `pip --version` works.
- [ ] The "Hello from Python" line printed.
- [ ] You created a `learn-ai-claude` folder.

---

## 🎯 Homework

If anything above threw an error, do the Lesson-4 trick: snip the error (**Win+Shift+S**), paste it into Claude, and ask *"How do I fix this Python install error on Windows? I'm a beginner."* Fixing your own setup with Claude's help is great practice.

---

## 💡 Key takeaways

- Install Python via `winget install --id Python.Python.3.12 -e` **or** python.org (check **Add to PATH**).
- Always **reopen** your terminal after installing.
- Verify with `python --version` and `pip --version`.
- `pip` installs libraries; it comes with Python.

[← Prev](07-projects-and-memory.md) · [Course home](../README.md) · [Next: Get your API key →](09-get-api-key.md)
