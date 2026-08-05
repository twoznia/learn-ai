# Lesson 12 — Install VS Code + the Claude Extension

⏱️ **10 minutes** · Level: Beginner · Needs: Windows

[← Prev](11-powershell.md) · [Course home](../README.md) · [Next: Claude Code CLI →](13-claude-code-cli.md)

---

## 🧠 Theory (2 min)

**VS Code** (Visual Studio Code) is a free, hugely popular code editor from Microsoft. It's where most developers write code — and where AI coding assistants shine, because the AI can *see your files* and help edit them.

We'll install VS Code, then add **Claude Code**, Anthropic's official extension. It puts an AI coding assistant right in your editor that can read, write, and change files in your project (with your approval).

---

## 🛠️ Practice (7 min)

### Step 1 — Install VS Code

**Easiest (winget):** in PowerShell:

```powershell
winget install --id Microsoft.VisualStudioCode -e
```

**Or download:** go to **https://code.visualstudio.com**, click **Download for Windows**, run the installer. On the "Select Additional Tasks" screen, tick **"Add to PATH"** and **"Open with Code"** options — they make life easier.

### Step 2 — Open your course folder in VS Code

1. Launch **VS Code** (Start → type *Code* → Enter).
2. **File → Open Folder…** → pick `C:\Users\YourName\learn-ai-claude`.
3. You'll see the files you made in earlier lessons in the left sidebar. 🎉

### Step 3 — Meet the Extensions panel

1. Click the **Extensions** icon in the left bar (four squares, or press **Ctrl+Shift+X**).
2. In the search box, type **Python** and install the official **Python** extension by Microsoft. This gives you nice code coloring and a "Run" button.

### Step 4 — Install the Claude Code extension

1. Still in Extensions (**Ctrl+Shift+X**), search **Claude Code**.
2. Install the one published by **Anthropic**.
3. After installing, look for the Claude icon in the sidebar (or open the command palette with **Ctrl+Shift+P** and type "Claude").
4. Sign in when prompted — you can use your Claude account or your API key.

> The extension is a friendly front-end for **Claude Code**, which you'll also run from the terminal in the next lesson. Both use the same engine.

### Step 5 — Try it

1. Open `first_claude.py` from earlier.
2. Open the Claude panel and ask: *"Explain what this file does, line by line, for a beginner."*
3. Then ask: *"Add a comment above each line explaining it."* and approve the change.

Watch it edit your real file. That's AI-assisted coding.

---

## 🗺️ VS Code essentials (bookmark)

| Action | Shortcut |
|--------|----------|
| Open folder | Ctrl+K, Ctrl+O |
| Command palette (do anything) | Ctrl+Shift+P |
| Extensions | Ctrl+Shift+X |
| Toggle terminal | Ctrl+` (backtick) |
| Save | Ctrl+S |
| Run Python file | ▶ button (top-right) |

> **Tip:** Press **Ctrl+`** to open a terminal *inside* VS Code — it's a PowerShell, so all your earlier commands work right there.

---

## ✅ Checkpoint

- [ ] VS Code is installed and opened your course folder.
- [ ] Python extension installed.
- [ ] Claude Code extension installed and signed in.
- [ ] Claude explained (or edited) one of your files.

---

## 🎯 Homework

Ask Claude in VS Code: *"Create a new file called hello.py that prints a friendly greeting and today's motivational quote."* Approve it, then run it with the ▶ button.

---

## 💡 Key takeaways

- VS Code = the free, standard editor; install via winget or code.visualstudio.com.
- Add the **Python** extension and the **Claude Code** extension.
- The AI can read and edit your project files, with your approval.
- **Ctrl+`** opens a terminal inside the editor.

[← Prev](11-powershell.md) · [Course home](../README.md) · [Next: Claude Code CLI →](13-claude-code-cli.md)
