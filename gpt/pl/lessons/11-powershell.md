# Lekcja 11 — Wywołaj GPT z PowerShell

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: ustawiony klucz API (L9). **Python niepotrzebny.**

🌐 [English](../../en/lessons/11-powershell.md) · [← Wstecz](10-python-pierwszy-skrypt.md) · [Strona kursu](../README.md) · [Dalej: VS Code + AI →](12-vscode-ai.md)

---

## 🧠 Teoria (2 min)

**PowerShell** jest już zainstalowany na każdym komputerze z Windows. Potrafi wysyłać zapytania sieciowe, więc może rozmawiać z API OpenAI **bez instalowania czegokolwiek**. Przydatne do szybkich skryptów, automatyzacji i zadań zaplanowanych.

Pod maską wysyłamy **HTTP POST** do punktu końcowego OpenAI z:

- Twoim **kluczem API** w nagłówku `Authorization`,
- małym ciałem **JSON** z modelem i wiadomościami.

`Invoke-RestMethod` to wbudowana komenda PowerShell do tego.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Sprawdź, że klucz jest dostępny

Otwórz **nowe** okno PowerShell i uruchom:

```powershell
echo $env:OPENAI_API_KEY
```

Powinieneś zobaczyć klucz. (Jeśli puste, wróć do Lekcji 9 — `setx` działa tylko dla nowych okien.)

### Krok 2 — Wyślij pierwsze zapytanie

Wklej cały ten blok i naciśnij Enter:

```powershell
$headers = @{
    "Authorization" = "Bearer $env:OPENAI_API_KEY"
    "content-type"  = "application/json"
}

$body = @{
    model    = "gpt-5-mini"
    messages = @(
        @{ role = "user"; content = "Podaj 3-krokowy poranny rytuał. Krótko." }
    )
} | ConvertTo-Json -Depth 6

$response = Invoke-RestMethod -Uri "https://api.openai.com/v1/chat/completions" `
    -Method Post -Headers $headers -Body $body

$response.choices[0].message.content
```

Zobaczysz wypisaną odpowiedź GPT. 🎉 AI z poziomu zwykłego terminala Windows.

### Krok 3 — Zapisz jako skrypt wielokrotnego użytku

```powershell
notepad $HOME\learn-ai-gpt\ask-gpt.ps1
```

Wklej to i zapisz:

```powershell
# ask-gpt.ps1 — zadaj GPT pytanie z PowerShell
param(
    [string]$Question = "Powiedz mi coś ciekawego."
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

### Krok 4 — Uruchom skrypt z pytaniem

```powershell
cd $HOME\learn-ai-gpt
powershell -ExecutionPolicy Bypass -File .\ask-gpt.ps1 -Question "Wyjaśnij prosto, czym jest API."
```

> `-ExecutionPolicy Bypass` pozwala uruchomić ten jeden skrypt. To częsty, bezpieczny sposób uruchamiania skryptu, który sam napisałeś. Nie zmienia żadnych ustawień systemu.

---

## 🧩 Co robi każdy element

| Element | Znaczenie |
|-------|---------|
| `Authorization: Bearer ...` | Wysyła Twój klucz API OpenAI |
| `model` + `messages` | Który GPT + Twoja wiadomość |
| `ConvertTo-Json -Depth 6` | Zamienia dane PowerShell na JSON oczekiwany przez API |
| `Invoke-RestMethod` | Wysyła zapytanie i czyta odpowiedź |
| `$response.choices[0].message.content` | Wyciąga tekstową odpowiedź GPT |

---

## ✅ Sprawdzenie

- [ ] Wklejony blok wypisał odpowiedź.
- [ ] `ask-gpt.ps1` działa z własnym `-Question`.
- [ ] Rozumiesz strukturę `messages`.

---

## 🎯 Zadanie

Zmień `model` w skrypcie na `gpt-5` i poproś o „napisanie krótkiego podziękowania dla współpracownika o imieniu Alex”. PowerShell + AI = natychmiastowy pomocnik tekstowy na każdym komputerze z Windows.

---

## 💡 Najważniejsze wnioski

- PowerShell rozmawia z GPT przez `Invoke-RestMethod` — bez instalacji.
- Uwierzytelnianie w nagłówku `Authorization: Bearer`; ciało ma `model` + `messages`.
- Tekst odpowiedzi jest w `$response.choices[0].message.content`.
- Zapisz jako skrypt `.ps1` i przekazuj pytania przez `-Question`.

🌐 [English](../../en/lessons/11-powershell.md) · [← Wstecz](10-python-pierwszy-skrypt.md) · [Strona kursu](../README.md) · [Dalej: VS Code + AI →](12-vscode-ai.md)
