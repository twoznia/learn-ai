# Lesson 02 — Set Up VS Code + Copilot (First Completions)

⏱️ **12 minutes** · Level: Beginner · Needs: Windows, a GitHub account (Lesson 1)

🌐 [Polski](../../pl/lessons/02-konfiguracja-vscode-i-copilot.md) · [← Prev](01-what-is-github-copilot.md) · [Course home](../README.md) · [Next: Copilot Chat basics →](03-copilot-chat-basics.md)

---

## 🧠 Theory (3 min)

**VS Code** (Visual Studio Code) is Microsoft's free, hugely popular code editor — and the best place to use Copilot. We'll install VS Code, add the Copilot extensions, sign in, and watch Copilot suggest code as **grey "ghost text"** you accept with a keystroke.

Two extensions work together:
- **GitHub Copilot** — the inline code completions.
- **GitHub Copilot Chat** — the chat panel and inline chat (next lesson).

Installing one usually offers the other; get both.

---

## 🛠️ Practice (8 min)

### Step 1 — Install VS Code

In **PowerShell**:

```powershell
winget install --id Microsoft.VisualStudioCode -e
```

Or download from **https://code.visualstudio.com** → **Download for Windows** → run the installer (tick **"Add to PATH"**).

### Step 2 — Make a practice folder and open it

```powershell
mkdir $HOME\copilot-course
```

In VS Code: **File → Open Folder…** → pick `C:\Users\YourName\copilot-course`.

### Step 3 — Install the Copilot extensions

1. Click the **Extensions** icon (**Ctrl+Shift+X**).
2. Search **GitHub Copilot** and install it (publisher **GitHub**).
3. Also install **GitHub Copilot Chat** if it isn't added automatically.

### Step 4 — Sign in

When prompted (or via the **Copilot** icon / the account menu, bottom-left), **Sign in to GitHub** and authorize Copilot. A browser window confirms it. When the Copilot status icon shows it's active, you're ready.

### Step 5 — Your first completion

1. Create a new file: **File → New File** → save as `demo.py`.
2. Type this and then **wait**:

```python
# A function that returns the first n Fibonacci numbers
def fibonacci(n):
```

3. Copilot shows **grey ghost text** suggesting the function body.
4. Press **Tab** to accept, or **Esc** to dismiss.

You just wrote code with AI. 🎉

### Step 6 — Steer the suggestions

- Write a **comment** describing what you want, then start the line — Copilot uses it.
- See alternatives: hover the suggestion or use **Alt+]** / **Alt+[** to cycle (shortcuts may vary).
- Accept **word by word** with **Ctrl+→** if you only want part.

---

## 🗺️ Copilot completion shortcuts (bookmark)

| Action | Shortcut |
|--------|----------|
| Accept suggestion | Tab |
| Dismiss | Esc |
| Next / previous suggestion | Alt+] / Alt+[ |
| Accept one word | Ctrl+→ |
| Trigger inline chat | Ctrl+I |

> Shortcuts can differ by version/keymap — check **File → Preferences → Keyboard Shortcuts** and search "Copilot".

---

## ✅ Checkpoint

- [ ] VS Code is installed and opened your `copilot-course` folder.
- [ ] The GitHub Copilot (and Chat) extensions are installed.
- [ ] You signed in and Copilot is active.
- [ ] You accepted at least one ghost-text completion.

---

## 🎯 Homework

In `demo.py`, write a comment `# A function that checks if a word is a palindrome` and let Copilot write it. Accept it, then write a second comment asking for a test, and accept that too. Notice how a clear comment produces better code.

---

## 💡 Key takeaways

- Install **VS Code** + the **GitHub Copilot** and **Copilot Chat** extensions, then sign in.
- Copilot suggests **grey ghost text**; **Tab** accepts, **Esc** dismisses.
- A short **comment describing intent** dramatically improves the suggestion.

🌐 [Polski](../../pl/lessons/02-konfiguracja-vscode-i-copilot.md) · [← Prev](01-what-is-github-copilot.md) · [Course home](../README.md) · [Next: Copilot Chat basics →](03-copilot-chat-basics.md)
