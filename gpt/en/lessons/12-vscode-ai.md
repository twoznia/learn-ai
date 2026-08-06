# Lesson 12 — VS Code + AI (Codex / Copilot)

⏱️ **10 minutes** · Level: Beginner · Needs: Windows

🌐 [Polski](../../pl/lessons/12-vscode-ai.md) · [← Prev](11-powershell.md) · [Course home](../README.md) · [Next: Codex CLI →](13-codex-cli.md)

---

## 🧠 Theory (2 min)

**VS Code** (Visual Studio Code) is a free, hugely popular code editor from Microsoft. AI assistants live inside it and can *see your files* to help you write and edit code.

For OpenAI models, two great options:

- **Codex (OpenAI)** — OpenAI's coding assistant, available as a VS Code extension that pairs with your ChatGPT account.
- **GitHub Copilot** — Microsoft's AI pair-programmer (powered by OpenAI/other models), with a free tier. Extremely popular and beginner-friendly.

Either works. We'll install VS Code, then add one.

---

## 🛠️ Practice (7 min)

### Step 1 — Install VS Code

**Easiest (winget):** in PowerShell:

```powershell
winget install --id Microsoft.VisualStudioCode -e
```

**Or download:** go to **https://code.visualstudio.com**, click **Download for Windows**, run the installer. Tick **"Add to PATH"** and **"Open with Code"**.

### Step 2 — Open your course folder

1. Launch **VS Code** (Start → type *Code* → Enter).
2. **File → Open Folder…** → pick `C:\Users\YourName\learn-ai-gpt`.
3. You'll see files from earlier lessons in the left sidebar. 🎉

### Step 3 — Install the Python extension

1. Click **Extensions** (four squares, or **Ctrl+Shift+X**).
2. Search **Python** and install the official one by **Microsoft**.

### Step 4 — Add an AI assistant

Pick one:

**Option A — Codex (OpenAI):**
1. In Extensions (**Ctrl+Shift+X**), search **Codex** (by **OpenAI**).
2. Install it and **sign in with your ChatGPT account** (or API key) when prompted.

**Option B — GitHub Copilot:**
1. In Extensions, search **GitHub Copilot**.
2. Install it and **sign in with a GitHub account**. Enable the free tier if offered.

### Step 5 — Try it

1. Open `first_gpt.py` from earlier.
2. In the AI chat/side panel, ask: *"Explain what this file does, line by line, for a beginner."*
3. Start typing a new function and watch inline suggestions appear (press **Tab** to accept).

You now have AI help inside your editor.

---

## 🗺️ VS Code essentials (bookmark)

| Action | Shortcut |
|--------|----------|
| Command palette (do anything) | Ctrl+Shift+P |
| Extensions | Ctrl+Shift+X |
| Toggle terminal | Ctrl+` (backtick) |
| Save | Ctrl+S |
| Run Python file | ▶ button (top-right) |
| Accept AI suggestion | Tab |

> **Tip:** Press **Ctrl+`** to open a terminal *inside* VS Code — it's a PowerShell, so all your earlier commands work there.

---

## ✅ Checkpoint

- [ ] VS Code is installed and opened your course folder.
- [ ] Python extension installed.
- [ ] Codex or Copilot installed and signed in.
- [ ] The AI explained a file or suggested code.

---

## 🎯 Homework

Ask your AI assistant: *"Suggest one small improvement to first_gpt.py and show me the changed code."* Read the suggestion and decide whether to apply it.

---

## 💡 Key takeaways

- VS Code = the free, standard editor; install via winget or code.visualstudio.com.
- Add the **Python** extension, then **Codex** (OpenAI) or **GitHub Copilot**.
- The AI explains and suggests code right inside the editor.
- **Ctrl+`** opens a terminal inside the editor.

🌐 [Polski](../../pl/lessons/12-vscode-ai.md) · [← Prev](11-powershell.md) · [Course home](../README.md) · [Next: Codex CLI →](13-codex-cli.md)
