# Lesson 12 — VS Code + Gemini Code Assist

⏱️ **10 minutes** · Level: Beginner · Needs: Windows, a Google account

🌐 [Polski](../../pl/lessons/12-vscode-gemini-code-assist.md) · [← Prev](11-powershell.md) · [Course home](../README.md) · [Next: Gemini CLI →](13-gemini-cli.md)

---

## 🧠 Theory (2 min)

**VS Code** (Visual Studio Code) is a free, hugely popular code editor from Microsoft. **Gemini Code Assist** is Google's AI extension for it: it explains code, suggests completions, and answers questions in a chat panel — with a **free tier** for individuals.

We'll install VS Code, then add Gemini Code Assist so you have AI help right where you write code.

---

## 🛠️ Practice (7 min)

### Step 1 — Install VS Code

**Easiest (winget):** in PowerShell:

```powershell
winget install --id Microsoft.VisualStudioCode -e
```

**Or download:** go to **https://code.visualstudio.com**, click **Download for Windows**, run the installer. Tick **"Add to PATH"** and **"Open with Code"** on the tasks screen.

### Step 2 — Open your course folder

1. Launch **VS Code** (Start → type *Code* → Enter).
2. **File → Open Folder…** → pick `C:\Users\YourName\learn-ai-gemini`.
3. You'll see the files from earlier lessons in the left sidebar. 🎉

### Step 3 — Install the Python extension

1. Click **Extensions** (four squares, or **Ctrl+Shift+X**).
2. Search **Python** and install the official one by **Microsoft** (nice colors + a Run button).

### Step 4 — Install Gemini Code Assist

1. Still in Extensions (**Ctrl+Shift+X**), search **Gemini Code Assist**.
2. Install the one published by **Google**.
3. Click the **Gemini icon** that appears in the left bar and **sign in with your Google account** when prompted. Choose the free individual option if asked.

### Step 5 — Try it

1. Open `first_gemini.py` from earlier.
2. In the Gemini Code Assist chat, ask: *"Explain what this file does, line by line, for a beginner."*
3. Put your cursor in the file and try asking it to *"add a comment above each line explaining it."*

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

> **Tip:** Press **Ctrl+`** to open a terminal *inside* VS Code — it's a PowerShell, so all your earlier commands work there.

---

## ✅ Checkpoint

- [ ] VS Code is installed and opened your course folder.
- [ ] Python extension installed.
- [ ] Gemini Code Assist installed and signed in.
- [ ] Gemini explained one of your files.

---

## 🎯 Homework

Ask Gemini Code Assist: *"Suggest one small improvement to first_gemini.py and show me the changed code."* Read the suggestion and decide whether to apply it.

---

## 💡 Key takeaways

- VS Code = the free, standard editor; install via winget or code.visualstudio.com.
- Add the **Python** extension and **Gemini Code Assist** (free tier for individuals).
- The AI explains and suggests code right inside the editor.
- **Ctrl+`** opens a terminal inside the editor.

🌐 [Polski](../../pl/lessons/12-vscode-gemini-code-assist.md) · [← Prev](11-powershell.md) · [Course home](../README.md) · [Next: Gemini CLI →](13-gemini-cli.md)
