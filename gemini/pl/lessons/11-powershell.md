# Lekcja 11 — Wywołaj Gemini z PowerShell

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: ustawiony klucz API (L9). **Python niepotrzebny.**

🌐 [English](../../en/lessons/11-powershell.md) · [← Wstecz](10-python-pierwszy-skrypt.md) · [Strona kursu](../README.md) · [Dalej: VS Code + Gemini Code Assist →](12-vscode-gemini-code-assist.md)

---

## 🧠 Teoria (2 min)

**PowerShell** jest już zainstalowany na każdym komputerze z Windows. Potrafi wysyłać zapytania sieciowe, więc może rozmawiać z API Gemini **bez instalowania czegokolwiek**. Przydatne do szybkich skryptów, automatyzacji i zadań zaplanowanych.

Pod maską wysyłamy **HTTP POST** do punktu końcowego API Gemini z:

- Twoim **kluczem API** w nagłówku (`x-goog-api-key`),
- małym ciałem **JSON** opisującym wiadomość.

`Invoke-RestMethod` to wbudowana komenda PowerShell do tego.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Sprawdź, że klucz jest dostępny

Otwórz **nowe** okno PowerShell i uruchom:

```powershell
echo $env:GEMINI_API_KEY
```

Powinieneś zobaczyć klucz. (Jeśli puste, wróć do Lekcji 9 — `setx` działa tylko dla nowych okien.)

### Krok 2 — Wyślij pierwsze zapytanie

Wklej cały ten blok i naciśnij Enter:

```powershell
$headers = @{
    "x-goog-api-key" = $env:GEMINI_API_KEY
    "content-type"   = "application/json"
}

$body = @{
    contents = @(
        @{ parts = @( @{ text = "Podaj 3-krokowy poranny rytuał. Krótko." } ) }
    )
} | ConvertTo-Json -Depth 6

$uri = "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash:generateContent"

$response = Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body

$response.candidates[0].content.parts[0].text
```

Zobaczysz wypisaną odpowiedź Gemini. 🎉 AI z poziomu zwykłego terminala Windows.

### Krok 3 — Zapisz jako skrypt wielokrotnego użytku

```powershell
notepad $HOME\learn-ai-gemini\ask-gemini.ps1
```

Wklej to i zapisz:

```powershell
# ask-gemini.ps1 — zadaj Gemini pytanie z PowerShell
param(
    [string]$Question = "Powiedz mi coś ciekawego."
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

### Krok 4 — Uruchom skrypt z pytaniem

```powershell
cd $HOME\learn-ai-gemini
powershell -ExecutionPolicy Bypass -File .\ask-gemini.ps1 -Question "Wyjaśnij prosto, czym jest API."
```

> `-ExecutionPolicy Bypass` pozwala uruchomić ten jeden skrypt. To częsty, bezpieczny sposób uruchamiania skryptu, który sam napisałeś. Nie zmienia żadnych ustawień systemu.

---

## 🧩 Co robi każdy element

| Element | Znaczenie |
|-------|---------|
| Nagłówek `x-goog-api-key` | Wysyła Twój klucz API Google |
| `contents → parts → text` | Struktura wiadomości Gemini |
| `ConvertTo-Json -Depth 6` | Zamienia dane PowerShell na JSON (głębokie zagnieżdżenie wymaga większej głębokości) |
| `Invoke-RestMethod` | Wysyła zapytanie i czyta odpowiedź |
| `$response.candidates[0].content.parts[0].text` | Wyciąga tekstową odpowiedź Gemini |

---

## ✅ Sprawdzenie

- [ ] Wklejony blok wypisał odpowiedź.
- [ ] `ask-gemini.ps1` działa z własnym `-Question`.
- [ ] Rozumiesz strukturę `contents/parts/text`.

---

## 🎯 Zadanie

Zmień model w adresie URL na `gemini-2.5-pro` i poproś o „napisanie krótkiego podziękowania dla współpracownika o imieniu Alex”. PowerShell + AI = natychmiastowy pomocnik tekstowy na każdym komputerze z Windows.

---

## 💡 Najważniejsze wnioski

- PowerShell rozmawia z Gemini przez `Invoke-RestMethod` — bez instalacji.
- Uwierzytelnianie w nagłówku `x-goog-api-key`; wiadomość zagnieżdżona `contents → parts → text`.
- Tekst odpowiedzi jest w `$response.candidates[0].content.parts[0].text`.
- Zapisz jako skrypt `.ps1` i przekazuj pytania przez `-Question`.

🌐 [English](../../en/lessons/11-powershell.md) · [← Wstecz](10-python-pierwszy-skrypt.md) · [Strona kursu](../README.md) · [Dalej: VS Code + Gemini Code Assist →](12-vscode-gemini-code-assist.md)
