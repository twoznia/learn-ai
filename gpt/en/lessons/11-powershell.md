# Lesson 11 — Call GPT from PowerShell

⏱️ **10 minutes** · Level: Beginner · Needs: API key set (L9). **No Python required.**

🌐 [Polski](../../pl/lessons/11-powershell.md) · [← Prev](10-python-first-script.md) · [Course home](../README.md) · [Next: VS Code + AI →](12-vscode-ai.md)

---

## 🧠 Theory (2 min)

**PowerShell** is already installed on every Windows PC. It can send web requests, so it can talk to the OpenAI API **without installing anything**. Handy for quick scripts, automations, and scheduled tasks.

Under the hood, we send an **HTTP POST** to OpenAI's endpoint with:

- your **API key** in an `Authorization` header,
- a small **JSON** body with the model and messages.

`Invoke-RestMethod` is PowerShell's built-in command for this.

---

## 🛠️ Practice (7 min)

### Step 1 — Check your key is available

Open a **new** PowerShell window and run:

```powershell
echo $env:OPENAI_API_KEY
```

You should see your key. (If blank, revisit Lesson 9 — `setx` only affects new windows.)

### Step 2 — Send your first request

Paste this whole block and press Enter:

```powershell
$headers = @{
    "Authorization" = "Bearer $env:OPENAI_API_KEY"
    "content-type"  = "application/json"
}

$body = @{
    model    = "gpt-5-mini"
    messages = @(
        @{ role = "user"; content = "Give me a 3-step morning routine. Keep it short." }
    )
} | ConvertTo-Json -Depth 6

$response = Invoke-RestMethod -Uri "https://api.openai.com/v1/chat/completions" `
    -Method Post -Headers $headers -Body $body

$response.choices[0].message.content
```

You'll see GPT's reply printed. 🎉 AI from a plain Windows terminal.

### Step 3 — Save it as a reusable script

```powershell
notepad $HOME\learn-ai-gpt\ask-gpt.ps1
```

Paste this and save:

```powershell
# ask-gpt.ps1 — ask GPT a question from PowerShell
param(
    [string]$Question = "Tell me something interesting."
)

$headers = @{
    "Authorization" = "Bearer $env:OPENAI_API_KEY"
    "content-type"  = "application/json"
}

$body = @{
    model    = "gpt-5-mini"
    messages = @(
        @{ role = "user"; content = $Question }
    )
} | ConvertTo-Json -Depth 6

$response = Invoke-RestMethod -Uri "https://api.openai.com/v1/chat/completions" `
    -Method Post -Headers $headers -Body $body

Write-Host ""
Write-Host $response.choices[0].message.content
```

### Step 4 — Run your script with a question

```powershell
cd $HOME\learn-ai-gpt
powershell -ExecutionPolicy Bypass -File .\ask-gpt.ps1 -Question "Explain what an API is, simply."
```

> `-ExecutionPolicy Bypass` lets this one script run. It's a common, safe way to run a script you wrote yourself. It doesn't change any system settings.

---

## 🧩 What each piece does

| Piece | Meaning |
|-------|---------|
| `Authorization: Bearer ...` | Sends your OpenAI API key |
| `model` + `messages` | Which GPT + your message |
| `ConvertTo-Json -Depth 6` | Turns PowerShell data into JSON the API expects |
| `Invoke-RestMethod` | Sends the request and reads the reply |
| `$response.choices[0].message.content` | Pulls out GPT's text answer |

---

## ✅ Checkpoint

- [ ] The inline block printed a reply.
- [ ] `ask-gpt.ps1` runs with a custom `-Question`.
- [ ] You understand the `messages` shape.

---

## 🎯 Homework

Change `model` in the script to `gpt-5` and ask it to "write a short thank-you note to a coworker named Alex." PowerShell + AI = an instant text helper on any Windows machine.

---

## 💡 Key takeaways

- PowerShell talks to GPT with `Invoke-RestMethod` — no install needed.
- Auth goes in the `Authorization: Bearer` header; the body has `model` + `messages`.
- The reply text is at `$response.choices[0].message.content`.
- Save it as a `.ps1` script and pass questions with `-Question`.

🌐 [Polski](../../pl/lessons/11-powershell.md) · [← Prev](10-python-first-script.md) · [Course home](../README.md) · [Next: VS Code + AI →](12-vscode-ai.md)
