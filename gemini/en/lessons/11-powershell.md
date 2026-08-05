# Lesson 11 — Call Gemini from PowerShell

⏱️ **10 minutes** · Level: Beginner · Needs: API key set (L9). **No Python required.**

🌐 [Polski](../../pl/lessons/11-powershell.md) · [← Prev](10-python-first-script.md) · [Course home](../README.md) · [Next: VS Code + Gemini Code Assist →](12-vscode-gemini-code-assist.md)

---

## 🧠 Theory (2 min)

**PowerShell** is already installed on every Windows PC. It can send web requests, so it can talk to Gemini's API **without installing anything**. Handy for quick scripts, automations, and scheduled tasks.

Under the hood, we send an **HTTP POST** to Gemini's API endpoint with:

- your **API key** in a header (`x-goog-api-key`),
- a small **JSON** body describing the message.

`Invoke-RestMethod` is PowerShell's built-in command for this.

---

## 🛠️ Practice (7 min)

### Step 1 — Check your key is available

Open a **new** PowerShell window and run:

```powershell
echo $env:GEMINI_API_KEY
```

You should see your key. (If blank, revisit Lesson 9 — `setx` only affects new windows.)

### Step 2 — Send your first request

Paste this whole block and press Enter:

```powershell
$headers = @{
    "x-goog-api-key" = $env:GEMINI_API_KEY
    "content-type"   = "application/json"
}

$body = @{
    contents = @(
        @{ parts = @( @{ text = "Give me a 3-step morning routine. Keep it short." } ) }
    )
} | ConvertTo-Json -Depth 6

$uri = "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent"

$response = Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body

$response.candidates[0].content.parts[0].text
```

You'll see Gemini's reply printed. 🎉 AI from a plain Windows terminal.

### Step 3 — Save it as a reusable script

```powershell
notepad $HOME\learn-ai-gemini\ask-gemini.ps1
```

Paste this and save:

```powershell
# ask-gemini.ps1 — ask Gemini a question from PowerShell
param(
    [string]$Question = "Tell me something interesting."
)

$headers = @{
    "x-goog-api-key" = $env:GEMINI_API_KEY
    "content-type"   = "application/json"
}

$body = @{
    contents = @(
        @{ parts = @( @{ text = $Question } ) }
    )
} | ConvertTo-Json -Depth 6

$uri = "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent"

$response = Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body

Write-Host ""
Write-Host $response.candidates[0].content.parts[0].text
```

### Step 4 — Run your script with a question

```powershell
cd $HOME\learn-ai-gemini
powershell -ExecutionPolicy Bypass -File .\ask-gemini.ps1 -Question "Explain what an API is, simply."
```

> `-ExecutionPolicy Bypass` lets this one script run. It's a common, safe way to run a script you wrote yourself. It doesn't change any system settings.

---

## 🧩 What each piece does

| Piece | Meaning |
|-------|---------|
| `x-goog-api-key` header | Sends your Google API key |
| `contents → parts → text` | Gemini's message structure |
| `ConvertTo-Json -Depth 6` | Turns PowerShell data into JSON (deep nesting needs a higher depth) |
| `Invoke-RestMethod` | Sends the request and reads the reply |
| `$response.candidates[0].content.parts[0].text` | Pulls out Gemini's text answer |

---

## ✅ Checkpoint

- [ ] The inline block printed a reply.
- [ ] `ask-gemini.ps1` runs with a custom `-Question`.
- [ ] You understand the `contents/parts/text` shape.

---

## 🎯 Homework

Change the model in the URL to `gemini-2.5-pro` and ask it to "write a short thank-you note to a coworker named Alex." PowerShell + AI = an instant text helper on any Windows machine.

---

## 💡 Key takeaways

- PowerShell talks to Gemini with `Invoke-RestMethod` — no install needed.
- Auth goes in the `x-goog-api-key` header; the message is nested `contents → parts → text`.
- The reply text is at `$response.candidates[0].content.parts[0].text`.
- Save it as a `.ps1` script and pass questions with `-Question`.

🌐 [Polski](../../pl/lessons/11-powershell.md) · [← Prev](10-python-first-script.md) · [Course home](../README.md) · [Next: VS Code + Gemini Code Assist →](12-vscode-gemini-code-assist.md)
