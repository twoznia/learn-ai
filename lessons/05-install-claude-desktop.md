# Lesson 05 — Install Claude Desktop on Windows

⏱️ **10 minutes** · Level: Beginner · Needs: Windows 10/11, your Claude account

[← Prev](04-files-and-images.md) · [Course home](../README.md) · [Next: Everyday tasks →](06-desktop-daily-tasks.md)

---

## 🧠 Theory (2 min)

**Claude Desktop** is a free Windows app — the same Claude, but as a dedicated program instead of a browser tab. Why bother?

- **Always a keystroke away** — pin it to your taskbar, launch with a shortcut.
- **Feels focused** — no browser tabs, notifications, or distractions.
- **Unlocks MCP** later — Claude Desktop can safely connect to tools on your PC (Lesson 15). This is the big reason to install it.

---

## 🛠️ Practice (7 min)

### Option A — Download from the website (simplest)

1. Open your browser and go to **https://claude.ai/download**
2. Click the **Windows** download button. You'll get a file like `Claude-Setup.exe` in your **Downloads** folder.
3. Double-click the file.
4. If Windows shows a blue **"Windows protected your PC"** SmartScreen box: click **More info → Run anyway** (this is normal for freshly downloaded apps from legit sites).
5. Follow the installer. It's quick — no complicated options.
6. When it opens, **sign in** with the same account you made in Lesson 2.

### Option B — Install with `winget` (the pro way)

Windows has a built-in package manager called **winget**. It downloads and installs apps with one command — you'll use it a lot in this course.

1. Click **Start**, type **PowerShell**, open **Windows PowerShell**.
2. Paste this and press Enter:

```powershell
winget install --id Anthropic.Claude -e
```

3. If it asks to accept terms, type **Y** and Enter.

> If `winget` isn't found, install **App Installer** from the Microsoft Store, then try again. Or just use Option A.

### Step — Pin it for instant access

1. Once Claude Desktop is open, **right-click its icon** on the taskbar.
2. Click **Pin to taskbar**.
3. Now it's one click away, forever.

### Step — Test it

Type into Claude Desktop:
```text
Give me a 3-item checklist to start my workday productively.
```

Same brain as the website — now in a tidy app. ✅

---

## 🆚 Web vs. Desktop — which to use?

| Situation | Use |
|-----------|-----|
| Quick question, any device | **Web** (claude.ai) |
| Daily driver on your PC | **Desktop** |
| Connecting Claude to files/tools (MCP) | **Desktop** (Lesson 15) |
| Public/shared computer | **Web**, then sign out |

You can use both with the same account — chats sync.

---

## ✅ Checkpoint

- [ ] Claude Desktop is installed and you're signed in.
- [ ] It's pinned to your taskbar.
- [ ] You sent one message from the app.

---

## 🎯 Homework

Learn the launch habit: press the **Windows key**, type **Claude**, press **Enter**. Do it 3 times so it becomes muscle memory. Fast access = you'll actually use it.

---

## 💡 Key takeaways

- Claude Desktop = the same Claude in a focused Windows app.
- Install via **claude.ai/download** or `winget install --id Anthropic.Claude -e`.
- SmartScreen "Run anyway" is normal for new downloads.
- Desktop is required later for **MCP** (connecting Claude to your tools).

[← Prev](04-files-and-images.md) · [Course home](../README.md) · [Next: Everyday tasks →](06-desktop-daily-tasks.md)
