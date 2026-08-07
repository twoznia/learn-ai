# G2 — Approval Modes & the Sandbox

⏱️ **15 minutes** · Track: 🅶 Codex CLI in Depth · Needs: the Codex CLI installed & signed in

🌐 [Polski](../../pl/track-g/02-tryby-zatwierdzania-i-sandbox.md) · [← Prev](01-agents-md-and-context.md) · [Track index](../README.md) · [Next: Config & custom prompts →](03-config-and-custom-prompts.md)

---

## 🧠 Theory (5 min)

This is the most important safety lesson in the track. Codex controls what an agent can do to your machine with **two dials**:

- **Approval mode** — *when Codex asks you before acting.* From "ask before everything" to "don't ask at all."
- **Sandbox** — *what Codex is even allowed to touch,* regardless of approvals. From read-only, to writing within the working folder, to full access.

Roughly, the levels you'll see:

| Level | What it means |
|-------|---------------|
| **Read Only** | Codex can read and plan, but not edit files or run commands that change things |
| **Auto / Workspace-write** | Codex can edit files **in the working folder** and run commands, asking when something reaches outside or looks risky |
| **Full Access** | Codex acts without asking and without the sandbox — powerful and dangerous |

The safe default while learning is the middle: work **inside a project folder**, let it edit there, and **approve** anything that reaches outside. Save "Full Access" for throwaway sandboxes you don't care about.

---

## 🛠️ Practice (9 min)

### Step 1 — See the current mode

Start Codex in a project. It shows the active approval/sandbox mode at startup. You can change it with the `/approvals` command (or by restarting with a mode flag).

```text
/approvals
```

Pick a mode and read what each one allows.

### Step 2 — Try Read Only

Switch to **Read Only** and ask for a change:

```text
Add a "## Notes" section to the README.
```

Codex will *propose* it but can't write — proof that Read Only really is read only. Great for exploring an unfamiliar or sensitive project.

### Step 3 — Switch to the working mode

Move to the middle **Auto / workspace-write** mode. Ask again:

```text
Add a "## Notes" section to the README with two example bullets.
```

Now it can edit **within the folder** — and it still asks before anything outside it or anything risky (like a network command). Approve and check the file.

### Step 4 — Watch it ask at the boundary

Ask for something that reaches beyond the folder or the network:

```text
Install a new package for this project.
```

Notice Codex **pauses for approval** because that goes past the workspace sandbox. Read the proposed command before you say yes.

### Step 5 — Understand "Full Access" (and avoid it early)

Full Access removes the sandbox and the asking. It's occasionally useful in a **disposable** environment, but it can delete files or run anything. **Don't use it on a real project or your main machine while learning.**

### Step 6 — Pick a default and a working style

- **Exploring / sensitive code?** Read Only.
- **Normal work?** Auto / workspace-write, in a dedicated folder.
- **Throwaway sandbox only?** Full Access — deliberately, never by habit.

---

## 🧩 The two dials

| Dial | Controls | Safe starting point |
|------|----------|---------------------|
| **Approval mode** | When Codex asks before acting | Ask before edits/commands |
| **Sandbox** | What Codex may touch at all | Workspace-write (this folder) |
| Together | Your safety envelope | Middle mode, in a project folder |

> ⚠️ **The sandbox is your seatbelt.** Keep Codex scoped to a project folder, approve anything that reaches outside it, and reserve Full Access for environments you're willing to lose.

---

## ✅ Checkpoint

- [ ] You viewed and changed the approval/sandbox mode with `/approvals`.
- [ ] You confirmed Read Only can't edit files.
- [ ] In the middle mode, you saw it edit within the folder but ask at the boundary.
- [ ] You can explain approval mode vs sandbox and why Full Access is a last resort.

---

## 🎯 Homework

In a scratch project, try each mode on the same small task: Read Only (it proposes, can't act), Auto (it edits and asks at the boundary). Write down which mode you'll use for real work — and promise yourself Full Access is only for throwaway folders.

---

## 💡 Key takeaways

- Codex safety is **two dials**: **approval mode** (when it asks) and the **sandbox** (what it can touch).
- The safe default is the **middle**: edit within a dedicated folder, approve anything reaching outside.
- **Full Access** removes both guards — use it only in disposable environments, never on a real machine while learning.

🌐 [Polski](../../pl/track-g/02-tryby-zatwierdzania-i-sandbox.md) · [← Prev](01-agents-md-and-context.md) · [Track index](../README.md) · [Next: Config & custom prompts →](03-config-and-custom-prompts.md)
