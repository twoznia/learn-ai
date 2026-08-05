# Lekcja 11 — Wywołaj Claude z PowerShell

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: ustawiony klucz API (L9). **Python niepotrzebny.**

🌐 [English](../../en/lessons/11-powershell.md) · [← Wstecz](10-python-pierwszy-skrypt.md) · [Strona kursu](../README.md) · [Dalej: VS Code →](12-vscode.md)

---

## 🧠 Teoria (2 min)

**PowerShell** jest już zainstalowany na każdym komputerze z Windows. Potrafi wysyłać zapytania sieciowe, co oznacza, że może rozmawiać z API Claude **bez instalowania czegokolwiek**. Przydatne do szybkich skryptów, automatyzacji i zadań zaplanowanych.

Pod maską wysyłamy zapytanie **HTTP POST** do punktu końcowego API Claude z:

- Twoim **kluczem API** w nagłówku,
- małym ciałem **JSON** opisującym model i wiadomość.

`Invoke-RestMethod` to wbudowana komenda PowerShell do tego.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Sprawdź, że klucz jest dostępny

Otwórz **nowe** okno PowerShell i uruchom:

```powershell
echo $env:ANTHROPIC_API_KEY
```

Powinieneś zobaczyć klucz. (Jeśli puste, wróć do Lekcji 9 — `setx` działa tylko dla nowych okien.)

### Krok 2 — Wyślij pierwsze zapytanie

Wklej cały ten blok do PowerShell i naciśnij Enter:

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
        @{ role = "user"; content = "Podaj 3-krokowy poranny rytuał. Krótko." }
    )
} | ConvertTo-Json -Depth 5

$response = Invoke-RestMethod -Uri "https://api.anthropic.com/v1/messages" `
    -Method Post -Headers $headers -Body $body

$response.content[0].text
```

Zobaczysz wypisaną odpowiedź Claude. 🎉 To AI z poziomu zwykłego terminala Windows.

### Krok 3 — Zapisz jako skrypt wielokrotnego użytku

Zamieńmy to na plik, który uruchomisz kiedykolwiek. Utwórz go:

```powershell
notepad $HOME\learn-ai-claude\ask-claude.ps1
```

Wklej to i zapisz:

```powershell
# ask-claude.ps1 — zadaj Claude pytanie z PowerShell
param(
    [string]$Question = "Powiedz mi coś ciekawego."
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

### Krok 4 — Uruchom skrypt z pytaniem

```powershell
cd $HOME\learn-ai-claude
powershell -ExecutionPolicy Bypass -File .\ask-claude.ps1 -Question "Wyjaśnij prosto, czym jest API."
```

> `-ExecutionPolicy Bypass` pozwala uruchomić ten jeden skrypt. To częsty, bezpieczny sposób uruchamiania skryptu, który sam napisałeś. Nie zmienia żadnych ustawień systemu.

Wypróbuj różne pytania, zmieniając część `-Question "..."`.

---

## 🧩 Co robi każdy element

| Element | Znaczenie |
|-------|---------|
| `$headers` | Zawiera klucz API + wymagany nagłówek wersji |
| `$body` | Model, limit długości i Twoja wiadomość, zamienione na JSON |
| `ConvertTo-Json -Depth 5` | Zamienia dane PowerShell na JSON oczekiwany przez API |
| `Invoke-RestMethod` | Wysyła zapytanie sieciowe i czyta odpowiedź |
| `$response.content[0].text` | Wyciąga tekstową odpowiedź Claude |

---

## ✅ Sprawdzenie

- [ ] Wklejony blok wypisał odpowiedź.
- [ ] `ask-claude.ps1` działa z własnym `-Question`.
- [ ] Rozumiesz różnicę między nagłówkami a ciałem.

---

## 🎯 Zadanie

Zmień `model` w skrypcie na `claude-sonnet-5` i poproś o „napisanie krótkiego podziękowania dla współpracownika o imieniu Alex”. PowerShell + AI = natychmiastowy pomocnik tekstowy na każdym komputerze z Windows.

---

## 💡 Najważniejsze wnioski

- PowerShell rozmawia z Claude przez `Invoke-RestMethod` — bez instalacji.
- Zapytanie = **nagłówki** (klucz + wersja) + **ciało JSON** (model + wiadomość).
- Zapisz jako skrypt `.ps1` i przekazuj pytania przez `-Question`.
- Tekst odpowiedzi jest w `$response.content[0].text`.

🌐 [English](../../en/lessons/11-powershell.md) · [← Wstecz](10-python-pierwszy-skrypt.md) · [Strona kursu](../README.md) · [Dalej: VS Code →](12-vscode.md)
