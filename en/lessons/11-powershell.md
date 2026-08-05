# Lesson 11 — Call Claude from PowerShell

⏱️ **10 minutes** · Level: Beginner · Needs: API key set (L9). **No Python required.**

[← Prev](10-python-first-script.md) · [Course home](../README.md) · [Next: VS Code setup →](12-vscode-setup.md)

---

## 🧠 Theory (2 min)

**PowerShell** is already installed on every Windows PC. It can send web requests, which means it can talk to Claude's API **without installing anything**. This is handy for quick scripts, automations, and scheduled tasks.

Under the hood, we send an **HTTP POST** request to Claude's API endpoint with:

- your **API key** in a header,
- a small **JSON** body describing the model and message.

`Invoke-RestMethod` is PowerShell's built-in command for this.

---

## 🛠️ Practice (7 min)

### Step 1 — Check your key is available

Open a **new** PowerShell window and run:

```powershell
echo $env:ANTHROPIC_API_KEY
```

You should see your key. (If blank, revisit Lesson 9 — `setx` only affects new windows.)

### Step 2 — Send your first request

Paste this whole block into PowerShell and press Enter:

```powershell
$headers = @{
    "x-api-key"         = $env:ANTHROPIC_API_KEY
    "anthropic-version" = "2023-06-01"
    "content-type"      = "application/json"
}

$body = @{
    model      = "claude-haiku-4-5"
    max_tokens = 300
    messages   = @(
        @{ role = "user"; content = "Give me a 3-step morning routine. Keep it short." }
    )
} | ConvertTo-Json -Depth 5

$response = Invoke-RestMethod -Uri "https://api.anthropic.com/v1/messages" `
    -Method Post -Headers $headers -Body $body

$response.content[0].text
```

You'll see Claude's reply printed. 🎉 That's AI from a plain Windows terminal.

### Step 3 — Save it as a reusable script

Let's turn it into a file you can run anytime. Create it:

```powershell
notepad $HOME\learn-ai-claude\ask-claude.ps1
```

Paste this and save:

```powershell
# ask-claude.ps1 — ask Claude a question from PowerShell
param(
    [string]$Question = "Tell me something interesting."
)

$headers = @{
    "x-api-key"         = $env:ANTHROPIC_API_KEY
    "anthropic-version" = "2023-06-01"
    "content-type"      = "application/json"
}

$body = @{
    model      = "claude-haiku-4-5"
    max_tokens = 500
    messages   = @(
        @{ role = "user"; content = $Question }
    )
} | ConvertTo-Json -Depth 5

$response = Invoke-RestMethod -Uri "https://api.anthropic.com/v1/messages" `
    -Method Post -Headers $headers -Body $body

Write-Host ""
Write-Host $response.content[0].text
```

### Step 4 — Run your script with a question

```powershell
cd $HOME\learn-ai-claude
powershell -ExecutionPolicy Bypass -File .\ask-claude.ps1 -Question "Explain what an API is, simply."
```

> `-ExecutionPolicy Bypass` lets this one script run. It's a common, safe way to run a script you wrote yourself. It doesn't change any system settings.

Try different questions by changing the `-Question "..."` part.

---

## 🧩 What each piece does

| Piece | Meaning |
|-------|---------|
| `$headers` | Includes your API key + required version header |
| `$body` | The model, length limit, and your message, turned into JSON |
| `ConvertTo-Json -Depth 5` | Turns PowerShell data into JSON the API expects |
| `Invoke-RestMethod` | Sends the web request and reads the reply |
| `$response.content[0].text` | Pulls out Claude's text answer |

---

## ✅ Checkpoint

- [ ] The inline block printed a reply.
- [ ] `ask-claude.ps1` runs with a custom `-Question`.
- [ ] You understand headers vs. body.

---

## 🎯 Homework

Change `model` in the script to `claude-sonnet-5` and ask it to "write a short thank-you note to a coworker named Alex." PowerShell + AI = instant text helper on any Windows machine.

---

## 💡 Key takeaways

- PowerShell talks to Claude with `Invoke-RestMethod` — no install needed.
- The request = **headers** (key + version) + **JSON body** (model + message).
- Save it as a `.ps1` script and pass questions with `-Question`.
- The reply text is at `$response.content[0].text`.

[← Prev](10-python-first-script.md) · [Course home](../README.md) · [Next: VS Code setup →](12-vscode-setup.md)
