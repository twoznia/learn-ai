# Capstone 02 — Set Up Your Agent

⏱️ **15 minutes** · Level: Capstone · Needs: Windows, a Claude Pro/Max account, Node.js + Python

🌐 [Polski](../../pl/lessons/02-skonfiguruj-agenta.md) · [← Prev](01-overview-and-architecture.md) · [Capstone home](../README.md) · [Next: Design your Second Brain →](03-design-your-second-brain.md)

---

## 🧠 Theory (3 min)

Our agent host is **Claude Code** — Anthropic's command-line agent. The key point for this capstone: you **sign in with your Claude account**, so it runs on your **Pro/Max subscription** with **no API key and no per-token bill**.

We'll install Claude Code, sign in, confirm Python is ready (for the MCP server in Lesson 4), and create the project folder that becomes your Second Brain.

> Prefer **Claude Desktop**? It can host MCP servers too (via its config file, as in Advanced Claude Track E). This capstone uses **Claude Code** because it's a true agent and keeps everything — server, Skills, notes — in one project folder you can ship to GitHub.

---

## 🛠️ Practice (11 min)

### Step 1 — Check Node.js and Python

In **PowerShell**:

```powershell
node --version
python --version
```

If either is missing, install it (the beginner course covers both; or `winget install OpenJS.NodeJS.LTS` and `winget install Python.Python.3.12`).

### Step 2 — Install Claude Code

```powershell
npm install -g @anthropic-ai/claude-code
```

### Step 3 — Create your project folder

```powershell
mkdir $HOME\second-brain
cd $HOME\second-brain
mkdir notes
git init
```

The `notes\` folder will hold your Markdown notes; `git` gives you a safety net (and later, a GitHub home).

### Step 4 — Start Claude Code and sign in

```powershell
claude
```

On first run, choose to **sign in with your Claude account** and complete it in the browser. This uses your **Pro/Max subscription** — decline any "use an API key" path for this capstone.

### Step 5 — Say hello to your agent

At the prompt, try:

```text
What files are in this folder? Keep it brief.
```

It should see your `notes\` folder. You're talking to your agent.

### Step 6 — Install the MCP SDK (for Lesson 4)

In a separate PowerShell (or the VS Code terminal), install the Python MCP package now so it's ready:

```powershell
pip install "mcp[cli]"
```

---

## 🧩 What you just set up

| Piece | Status |
|-------|--------|
| **Claude Code** (the agent) | Installed, signed in on your subscription |
| **Node.js / Python** | Confirmed working |
| **Project folder** + `notes\` | Created, under git |
| **MCP SDK** | Installed, ready for the server |

> ⚠️ You're on your **subscription** — usage counts against your plan's limits (see Advanced Claude Track D). Clear, focused sessions keep it efficient.

---

## ✅ Checkpoint

- [ ] `node --version` and `python --version` both work.
- [ ] Claude Code is installed and signed in **with your Claude account** (no API key).
- [ ] You created `second-brain\` with a `notes\` folder and `git init`.
- [ ] `pip install "mcp[cli]"` succeeded.

---

## 🎯 Homework

Have a short conversation with Claude Code inside your project folder — ask it to create a test file in `notes\`, then delete it. Get comfortable with approving its actions. That approval habit is your safety control for the whole capstone.

---

## 💡 Key takeaways

- **Claude Code** is your agent, signed in on your **Pro/Max subscription** — no API key, no per-token cost.
- Everything lives in one **project folder** (`second-brain\`) under **git**.
- The **MCP SDK** is installed, ready to build tools next.

🌐 [Polski](../../pl/lessons/02-skonfiguruj-agenta.md) · [← Prev](01-overview-and-architecture.md) · [Capstone home](../README.md) · [Next: Design your Second Brain →](03-design-your-second-brain.md)
