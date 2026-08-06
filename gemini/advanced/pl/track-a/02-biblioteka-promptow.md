# A2 — Zbuduj bibliotekę promptów

⏱️ **15 minut** · Ścieżka: 🅰️ Zaawansowany użytkownik · Potrzebne: edytor tekstu (Notatnik wystarczy)

🌐 [English](../../en/track-a/02-prompt-library.md) · [← Wstecz](01-mistrzostwo-gems.md) · [Indeks ścieżki](../README.md) · [Dalej: Deep Research i Canvas →](03-deep-research-canvas.md)

---

## 🧠 Teoria (4 min)

Zapisywałeś prompty do `moje-prompty.txt`. **Biblioteka** jest zorganizowana tak, byś znalazł i ponownie użył właściwego promptu w sekundy. Różnica to **struktura + szablony + wersjonowanie**.

1. **Szablony z lukami** — wyraźnie oznaczone puste miejsca (`<tak_o>`), które wypełniasz.
2. **Kategorie** — grupuj według zadania (Pisz, Streszczaj, Analizuj, Decyduj).
3. **Wersjonowanie** — zachowaj stare wersje, aby porównać po ulepszeniu.

Wystarczy zwykły folder plików tekstowych.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Utwórz folder biblioteki

```powershell
mkdir $HOME\prompt-library
cd $HOME\prompt-library
mkdir pisz, streszczaj, analizuj, decyduj
```

### Krok 2 — Napisz pierwszy szablon

Utwórz `pisz\odpowiedz-email.md`:

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

### Krok 3 — Dodaj szablon „decyzji”

Utwórz `decyduj\wazenie-opcji.md`:

```text
# Ważenie opcji
# Wersja: 1

Pomóż mi zdecydować między poniższymi opcjami.
1. Wypisz 2 najważniejsze plusy i 2 minusy każdej.
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

## decyduj/
- wazenie-opcji.md — porównaj 2+ opcje z rekomendacją
```

### Krok 5 — Zwersjonuj prompt

Ulepszając szablon, najpierw zachowaj kopię:

```powershell
copy pisz\odpowiedz-email.md pisz\odpowiedz-email-v1-backup.md
```

Potem podbij główny plik do Wersji 2 — ulepszenia są odwracalne.

> 💡 **Bonus:** dołącz ten folder do Gema jako referencję. Wtedy zapytaj *„który z moich zapisanych promptów pasuje do tego zadania?”*, a Gemini wybierze z Twojej biblioteki.

---

## 🧩 Jak wygląda „dobre”

| Słaba biblioteka | Mocna biblioteka |
|--------------|----------------|
| Jeden gigantyczny plik | Foldery według zadania |
| Trzeba przepisywać za każdym razem | Wyraźne `<luki>` do wypełnienia |
| Nadpisywanie przy ulepszaniu | Wersjonowanie z kopiami |
| Nie można znaleźć promptu | Indeks przeglądany w sekundy |

---

## ✅ Sprawdzenie

- [ ] Folder `prompt-library` z podfolderami kategorii.
- [ ] Co najmniej dwa szablony z wyraźnymi `<lukami>`.
- [ ] Plik indeksu wymieniający zawartość.

---

## 🎯 Zadanie

Przenieś każdy zebrany prompt do biblioteki, posortowany do kategorii. Usuń duplikaty. Dodaj nowy szablon dla zadania, które robisz najczęściej.

---

## 💡 Najważniejsze wnioski

- Biblioteka = **szablony + kategorie + wersjonowanie**, w zwykłym folderze.
- Wersjonuj prompty (kopie), aby ulepszenia były odwracalne.
- Dołącz bibliotekę do Gema, aby Gemini wybierał właściwy prompt.

🌐 [English](../../en/track-a/02-prompt-library.md) · [← Wstecz](01-mistrzostwo-gems.md) · [Indeks ścieżki](../README.md) · [Dalej: Deep Research i Canvas →](03-deep-research-canvas.md)
