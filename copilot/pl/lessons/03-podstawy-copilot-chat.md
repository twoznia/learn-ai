# Lekcja 03 — Podstawy Copilot Chat

⏱️ **12 minut** · Poziom: Początkujący · Wymagania: VS Code + Copilot (Lekcja 2)

🌐 [English](../../en/lessons/03-copilot-chat-basics.md) · [← Poprzednia](02-konfiguracja-vscode-i-copilot.md) · [Strona kursu](../README.md) · [Dalej: Dobre promptowanie Copilota →](04-dobre-promptowanie-copilota.md)

---

## 🧠 Teoria (3 min)

Uzupełnienia kończą Twoje linie. **Copilot Chat** pozwala *rozmawiać* z Copilotem o kodzie — zadawać pytania, prosić o zmiany, generować testy i rozumieć błędy. Dwa sposoby użycia:

- **Widok czatu** — panel boczny do rozmowy tam i z powrotem o projekcie.
- **Czat w linii** (**Ctrl+I**) — małe pole wprost w pliku, idealne do „zmień tę funkcję".

Czat rozumie **Twoje otwarte pliki i projekt**, więc odpowiedzi dotyczą *Twojego* kodu — nie ogólne. Ma też przydatne **komendy ze slashem** jak `/explain`, `/fix` i `/tests`, które pakują częste prośby.

---

## 🛠️ Praktyka (8 min)

### Krok 1 — Otwórz widok czatu

Kliknij ikonę **Copilot Chat** na pasku bocznym (lub **Ctrl+Alt+I**). Otworzy się panel czatu.

### Krok 2 — Zapytaj o swój kod

Otwórz `demo.py` z Lekcji 2, potem w czacie:

```text
Explain what fibonacci(n) does, step by step, for a beginner.
```

Zauważ, że odpowiedź odwołuje się do *Twojej rzeczywistej funkcji*.

### Krok 3 — Użyj komend ze slashem

W polu czatu wpisz `/`, by zobaczyć komendy. Wypróbuj:

```text
/explain
```
```text
/tests
```

- **/explain** — wyjaśnia bieżące zaznaczenie/plik.
- **/tests** — generuje testy jednostkowe.
- **/fix** — proponuje poprawkę problemu.

### Krok 4 — Czat w linii do szybkiej edycji

1. Zaznacz funkcję `fibonacci`.
2. Naciśnij **Ctrl+I** i wpisz:

```text
Add input validation: raise a ValueError if n is negative.
```

3. Copilot pokazuje **diff**. Kliknij **Accept**, by zastosować, lub **Discard**.

Czat w linii to najszybszy sposób zmiany kodu przed Tobą.

### Krok 5 — Napraw błąd z Copilotem

Zepsuj coś celowo (usuń dwukropek), uruchom plik, potem:
1. Zaznacz błąd w terminalu lub otwórz plik.
2. Zapytaj w czacie: `/fix` lub „Dlaczego ten błąd występuje i jak go naprawić?"

### Krok 6 — Wybierz model (opcjonalnie)

Niektóre konfiguracje pozwalają wybrać **model** z listy w polu czatu. Zdolniejszy model pomaga przy trudnych problemach; szybszy wystarczy do prostych próśb. Dostępność zależy od planu.

---

## 🧩 Komendy czatu do poznania

| Komenda | Robi |
|---------|------|
| `/explain` | Wyjaśnia zaznaczony kod lub plik |
| `/fix` | Proponuje poprawkę błędu/problemu |
| `/tests` | Generuje testy dla zaznaczenia |
| `/doc` | Dodaje dokumentację/komentarze |
| Czat w linii (**Ctrl+I**) | Edytuj kod w miejscu, jako diff |

> Dokładne komendy różnią się zależnie od wersji — wpisz `/` w czacie, by zobaczyć dostępne teraz.

---

## ✅ Sprawdzian

- [ ] Otworzyłeś/aś widok czatu i zapytałeś/aś o własny kod.
- [ ] Uruchomiłeś/aś `/explain` i `/tests`.
- [ ] Użyłeś/aś czatu w linii (**Ctrl+I**) i zaakceptowałeś/aś diff.
- [ ] Naprawiłeś/aś błąd przez `/fix` lub pytanie w czacie.

---

## 🎯 Praca domowa

Napisz mały skrypt z błędem (np. pętla z błędem o jeden). Użyj **/fix** do poprawy, **/tests** do wygenerowania testów i **/explain** do zrozumienia poprawki. Zachowaj plik — użyjesz go ponownie.

---

## 💡 Najważniejsze wnioski

- **Copilot Chat** rozmawia o *Twoim* kodzie — przez **widok czatu** i **czat w linii (Ctrl+I)**.
- **Komendy ze slashem** (`/explain`, `/fix`, `/tests`, `/doc`) pakują częste prośby.
- Czat w linii pokazuje zmiany jako **diff**, który akceptujesz lub odrzucasz — zostajesz w kontroli.

🌐 [English](../../en/lessons/03-copilot-chat-basics.md) · [← Poprzednia](02-konfiguracja-vscode-i-copilot.md) · [Strona kursu](../README.md) · [Dalej: Dobre promptowanie Copilota →](04-dobre-promptowanie-copilota.md)
