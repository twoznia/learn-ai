# G5 — Skryptowanie CLI (tryb nieinteraktywny)

⏱️ **15 minut** · Ścieżka: 🅶 Gemini CLI w głąb · Potrzebne: Gemini CLI zainstalowany i zalogowany

🌐 [English](../../en/track-g/05-scripting-the-cli.md) · [← Wstecz](04-checkpointy-i-cofanie.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)

---

## 🧠 Teoria (4 min)

Wszystko dotąd używało CLI **interaktywnie** — piszesz, on odpowiada. Ale Gemini CLI może też działać **nieinteraktywnie**: podaj prompt w wierszu poleceń, odbierz odpowiedź i idź dalej. To odblokowuje **automatyzację** — umieść Gemini w skryptach, zaplanowanych zadaniach (Ścieżka C1) i potokach (Ścieżka C2), wszystko na Twoim koncie.

Dwa kształty:

- **Prompt jednorazowy:** `gemini -p "twój prompt"` zwraca odpowiedź i kończy.
- **Wejście z potoku:** podaj plik lub wyjście polecenia do Gemini przez potok.

Tak Gemini CLI staje się klockiem, nie tylko okienkiem czatu.

> Dokładne flagi ewoluują — uruchom `gemini --help` po aktualne opcje nieinteraktywne (flaga promptu, format wyjścia, auto-zatwierdzanie).

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Uruchom prompt jednorazowy

W PowerShell:

```powershell
gemini -p "Daj mi trzy zwięzłe wskazówki do pisania jasnych wiadomości commit."
```

Dostajesz odpowiedź wypisaną wprost do terminala, a CLI kończy — idealne do skryptów.

### Krok 2 — Podaj plik przez potok

Przekaż zawartość potokiem i poproś Gemini o pracę na niej:

```powershell
Get-Content notes.txt | gemini -p "Streść to w 3 punktach."
```

Gemini czyta tekst z potoku i zwraca streszczenie. Zamień `notes.txt` na dowolny plik.

### Krok 3 — Przechwyć wyjście

Zapisz wynik do pliku, by skrypt mógł go użyć:

```powershell
gemini -p "Napisz jednoakapitowy status projektu z tych notatek: (brak — zaimprowizuj szablon)" > status.txt
```

Teraz `status.txt` trzyma odpowiedź Gemini, gotową na kolejny krok potoku.

### Krok 4 — Umieść to w małym skrypcie

Utwórz `daily.ps1`:

```powershell
$date = Get-Date -Format "yyyy-MM-dd"
gemini -p "Napisz krótką, pogodną notatkę fokusową na dziś ($date). Poniżej 80 słów." `
  | Out-File "$HOME\daily-notes\focus-$date.txt"
```

Uruchom — notatka napisana przez Gemini pojawia się, bez okna czatu. Połącz to z **Harmonogramem zadań (Ścieżka C1)**, by uruchamiać co rano automatycznie.

### Krok 5 — Automatyzuj bezpiecznie

Uruchomienia nieinteraktywne mogą wymagać pominięcia prośby o zatwierdzenie (auto-zatwierdzanie), by działać bez nadzoru. To wygodne, ale **usuwa Twoją bramkę bezpieczeństwa**, więc:
- Używaj auto-zatwierdzania **tylko** dla promptów, które nie edytują plików ani nie uruchamiają ryzykownych poleceń (streszczenia, szkice, tekst na wyjście).
- Jeśli skrypt musi edytować pliki, uruchamiaj go w **dedykowanym folderze / gałęzi git**, by każda zmiana była odwracalna (G4).
- Nigdy nie kieruj nienadzorowanego, auto-zatwierdzającego zadania na wrażliwe dane ani cały dysk.

### Krok 6 — Połącz kropki ze Ścieżką C

Masz teraz obie połowy: **Gemini CLI jako polecenie** (ta lekcja) i **harmonogram/potoki** (Ścieżka C). Razem pozwalają Gemini wykonywać powtarzalną pracę za Ciebie — bez rąk, na Twoim koncie.

---

## 🧩 Interaktywnie vs skryptowo

| Użycie | Tryb |
|-----|------|
| Eksploracja, edycja, tam i z powrotem | Interaktywnie (`gemini`) |
| Jedna odpowiedź w skrypcie | `gemini -p "..."` |
| Przetwórz plik/wyjście | Potok do `gemini -p "..."` |
| Powtarzalne zadanie bez rąk | Skrypt + Harmonogram zadań (C1) |

> ⚠️ **Automatyzacja usuwa bramkę człowieka.** Auto-zatwierdzaj tylko bezpieczne prompty odczyt/generowanie; trzymaj skrypty edytujące pliki w odwracalnym (git) folderze; nigdy nie celuj nienadzorowanym zadaniem we wrażliwe dane.

---

## ✅ Sprawdzenie

- [ ] Uruchomiłeś prompt jednorazowy przez `gemini -p`.
- [ ] Podałeś plik do Gemini przez potok i dostałeś wynik.
- [ ] Zapisałeś wyjście do pliku i uruchomiłeś z małego skryptu.
- [ ] Umiesz podać zasady bezpieczeństwa dla nienadzorowanych, auto-zatwierdzających uruchomień.

---

## 🎯 Zadanie

Napisz mały skrypt, który podaje jeden z Twoich prawdziwych plików do `gemini -p` i zapisuje streszczenie. Jeśli zrobiłeś Ścieżkę C1, zaplanuj bezpieczną, tylko odczyt/generowanie wersję do uruchamiania codziennie. Trzymaj każdą automatyzację edytującą pliki w folderze śledzonym gitem.

---

## 💡 Najważniejsze wnioski

- Gemini CLI działa **nieinteraktywnie** (`gemini -p "..."` lub wejście z potoku) — klucz do umieszczenia Gemini w **skryptach i potokach**.
- Przechwytuj wyjście do plików i łącz z **Harmonogramem zadań (C1)** dla powtarzalnej pracy bez rąk.
- **Automatyzacja usuwa bramkę zatwierdzania** — auto-zatwierdzaj tylko bezpieczne prompty, trzymaj edycje plików w odwracalnym folderze git i nigdy nie celuj we wrażliwe dane bez nadzoru.

🌐 [English](../../en/track-g/05-scripting-the-cli.md) · [← Wstecz](04-checkpointy-i-cofanie.md) · [Indeks ścieżki](../README.md) · [↩ Strona zaawansowana](../README.md)
