# A2 — Zbuduj bibliotekę promptów

⏱️ **15 minut** · Ścieżka: 🅰️ Zaawansowany użytkownik · Potrzebne: edytor tekstu (Notatnik wystarczy)

🌐 [English](../../en/track-a/02-prompt-library.md) · [← Wstecz](01-mistrzostwo-projektow.md) · [Indeks ścieżki](../README.md) · [Dalej: Zaawansowane MCP →](03-zaawansowane-mcp.md)

---

## 🧠 Teoria (4 min)

Zapisywałeś prompty do `moje-prompty.txt`. To początek — ale **biblioteka** jest zorganizowana tak, byś znalazł i ponownie użył właściwego promptu w sekundy. Różnica między „kilkoma zapisanymi promptami” a prawdziwą biblioteką to **struktura + szablony + wersjonowanie**.

Trzy pomysły:

1. **Szablony z lukami.** Dobry prompt biblioteczny ma wyraźnie oznaczone puste miejsca (`<tak_o>`), które wypełniasz i strzelasz.
2. **Kategorie.** Grupuj według zadania (Pisz, Streszczaj, Analizuj, Decyduj), aby szybko przeglądać.
3. **Wersjonowanie.** Gdy ulepszasz prompt, zachowaj stary, aby móc porównać.

Zbudujesz to w zwykłym folderze plików tekstowych — bez aplikacji.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Utwórz folder biblioteki

W PowerShell:

```powershell
mkdir $HOME\prompt-library
cd $HOME\prompt-library
mkdir pisz, streszczaj, analizuj, decyduj
```

### Krok 2 — Napisz pierwszy szablon

Utwórz `pisz\odpowiedz-email.md`:

```powershell
notepad pisz\odpowiedz-email.md
```

Wklej ten szablon:

```text
# Odpowiedź na e-mail
# Wersja: 1  |  Ostatni dobry wynik: (data)

Rola: Jesteś moim asystentem komunikacji.
Zadanie: Napisz odpowiedź na poniższy e-mail.
Ograniczenia:
- Poniżej 5 zdań, ciepło-ale-profesjonalnie.
- Dwie wersje: zwięzła i cieplejsza.
- Nie obiecuj niczego, czego nie potwierdziłem.

E-MAIL:
<wklej e-mail>

MOJA INTENCJA:
<kilka słów>
```

Komentarze nagłówka (`# Wersja`, `# Ostatni dobry wynik`) to Twoje notatki wersjonowania.

### Krok 3 — Dodaj szablon „decyzji”

Utwórz `decyduj\wazenie-opcji.md`:

```text
# Ważenie opcji
# Wersja: 1

Pomóż mi zdecydować między poniższymi opcjami.
1. Wypisz 2 najważniejsze plusy i 2 najważniejsze minusy każdej.
2. Zaznacz największe ryzyko każdej.
3. Podaj rekomendację w jednym zdaniu i powiedz, co zmieniłoby Twoje zdanie.

OPCJE:
<opcja A>
<opcja B>
```

### Krok 4 — Zrób indeks

Utwórz `README.md` w katalogu głównym biblioteki:

```text
# Moja biblioteka promptów

## pisz/
- odpowiedz-email.md — odpowiedzi na e-maile, 2 wersje

## streszczaj/
- (dodawaj w miarę)

## analizuj/
- (dodawaj w miarę)

## decyduj/
- wazenie-opcji.md — porównaj 2+ opcje z rekomendacją
```

### Krok 5 — Zwersjonuj prompt (nawyk profesjonalisty)

Gdy ulepszasz `odpowiedz-email.md`, nie nadpisuj na ślepo. Podbij wersję i zostaw notatkę:

```powershell
copy pisz\odpowiedz-email.md pisz\odpowiedz-email-v1-backup.md
```

Potem edytuj główny plik do Wersji 2. Teraz możesz porównać, jeśli v2 kiedyś wyda się gorsza.

> 💡 **Bonus:** umieść cały ten folder w Projekcie Claude jako pliki wiedzy. Wtedy możesz zapytać Claude *„który z moich zapisanych promptów pasuje do tego zadania?”*, a on wybierze z Twojej biblioteki.

---

## 🧩 Jak wygląda „dobre”

| Oznaka słabej biblioteki | Oznaka mocnej |
|------------------------|----------------------|
| Jeden gigantyczny plik tekstowy | Foldery według zadania |
| Brak luk, trzeba przepisywać za każdym razem | Wyraźne `<luki>` do wypełnienia |
| Nadpisywanie przy ulepszaniu | Wersjonowanie z kopiami zapasowymi |
| Nie można znaleźć właściwego promptu | Indeks, który przeglądasz w sekundy |

---

## ✅ Sprawdzenie

- [ ] Masz folder `prompt-library` z podfolderami kategorii.
- [ ] Co najmniej dwa szablony z wyraźnymi `<lukami>`.
- [ ] Plik indeksu wymieniający zawartość.

---

## 🎯 Zadanie

Przenieś każdy prompt zebrany dotąd do biblioteki, posortowany do kategorii. Usuń duplikaty. Dodaj jeden nowy szablon dla zadania, które robisz najczęściej.

---

## 💡 Najważniejsze wnioski

- Biblioteka = **szablony z lukami + kategorie + wersjonowanie**, w zwykłym folderze.
- Wersjonuj prompty (zachowuj kopie), aby ulepszenia były odwracalne.
- Wczytaj bibliotekę do Projektu, aby Claude mógł wybrać właściwy prompt.

🌐 [English](../../en/track-a/02-prompt-library.md) · [← Wstecz](01-mistrzostwo-projektow.md) · [Indeks ścieżki](../README.md) · [Dalej: Zaawansowane MCP →](03-zaawansowane-mcp.md)
