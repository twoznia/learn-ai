# Lesson 05 — Install the ChatGPT Desktop App

⏱️ **10 minutes** · Level: Beginner · Needs: Windows 10/11, your ChatGPT account

🌐 [Polski](../../pl/lessons/05-instalacja-chatgpt-desktop.md) · [← Prev](04-files-and-images.md) · [Course home](../README.md) · [Next: Everyday tasks →](06-everyday-tasks.md)

---

## 🧠 Theory (2 min)

**ChatGPT for Windows** is a free desktop app — the same ChatGPT, but as a dedicated program instead of a browser tab. Why bother?

- **Always a keystroke away** — pin it to your taskbar, launch with a shortcut.
- **Feels focused** — no browser tabs or distractions.
- **Handy extras** — a quick launcher hotkey, and "work with apps" that can read what's on your screen (like a code editor) to help in context.

---

## 🛠️ Practice (7 min)

### Option A — Microsoft Store (simplest)

1. Open the **Microsoft Store** (Start → type *Store*).
2. Search **ChatGPT** (published by **OpenAI**).
3. Click **Get / Install**.
4. Launch it and **sign in** with the same account you made in Lesson 2.

### Option B — Download from OpenAI

1. Go to **https://openai.com/chatgpt/download**
2. Download the **Windows** app and run the installer.
3. If Windows shows a blue **"Windows protected your PC"** SmartScreen box: click **More info → Run anyway** (normal for freshly downloaded apps from legit sites).
4. Sign in when it opens.

### Option C — winget (the pro way)

In PowerShell, search for the package first, then install what it finds:

```powershell
winget search ChatGPT
```

If an official **OpenAI ChatGPT** entry appears, install it with (replace the id with the one shown):

```powershell
winget install --id OpenAI.ChatGPT -e
```

> If winget can't find it, just use Option A (Microsoft Store) — that's the easiest path.

### Step — Pin it for instant access

1. Once the app is open, **right-click its icon** on the taskbar.
2. Click **Pin to taskbar**.
3. Now it's one click away, forever.

### Step — Test it

Type into the app:
```text
Give me a 3-item checklist to start my workday productively.
```

Same brain as the website — now in a tidy app. ✅

---

## 🆚 Web vs. Desktop — which to use?

| Situation | Use |
|-----------|-----|
| Quick question, any device | **Web** (chatgpt.com) |
| Daily driver on your PC | **Desktop** |
| Helping with what's on your screen | **Desktop** ("work with apps") |
| Public/shared computer | **Web**, then sign out |

You can use both with the same account — chats sync.

---

## ✅ Checkpoint

- [ ] The ChatGPT app is installed and you're signed in.
- [ ] It's pinned to your taskbar.
- [ ] You sent one message from the app.

---

## 🎯 Homework

Learn the launch habit: press the **Windows key**, type **ChatGPT**, press **Enter**. Do it 3 times so it becomes muscle memory. Fast access = you'll actually use it.

---

## 💡 Key takeaways

- ChatGPT for Windows = the same ChatGPT in a focused app.
- Install via **Microsoft Store**, **openai.com/chatgpt/download**, or winget.
- SmartScreen "Run anyway" is normal for new downloads.
- Pin it to the taskbar for one-click access.

🌐 [Polski](../../pl/lessons/05-instalacja-chatgpt-desktop.md) · [← Prev](04-files-and-images.md) · [Course home](../README.md) · [Next: Everyday tasks →](06-everyday-tasks.md)
