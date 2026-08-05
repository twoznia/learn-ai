# Lekcja 04 — Praca z plikami i obrazami

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: gemini.google.com + dowolny PDF/obraz

🌐 [English](../../en/lessons/04-files-and-images.md) · [← Wstecz](03-podstawy-promptow.md) · [Strona kursu](../README.md) · [Dalej: Gemini w Chrome i Google →](05-gemini-w-chrome-i-google.md)

---

## 🧠 Teoria (3 min)

Gemini jest **natywnie multimodalny** — rozumienie tekstu i obrazów jest wbudowane w ten sam model, a nie dodane z boku. Możesz **wysyłać pliki**, a Gemini je przeczyta:

- **PDF-y, dokumenty, arkusze, pliki tekstowe** → Gemini czyta treść.
- **Obrazy i zrzuty ekranu** → Gemini je *widzi* (wykresy, zdjęcia, pismo odręczne, komunikaty błędów).

Dla początkujących to ogromne: wskaż Gemini prawdziwy dokument i powiedz „wyjaśnij to” zamiast przepisywać.

> ⚠️ **Uwaga o prywatności:** wysyłaj tylko pliki, które możesz udostępnić usłudze w chmurze. Nie wysyłaj haseł, cudzych danych prywatnych ani poufnych informacji służbowych. Więcej w Lekcji 17.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Streść PDF

1. Znajdź dowolny PDF (instrukcję, raport, paragon). Nie masz? W Chrome otwórz dowolną stronę → **menu ⋮ → Drukuj → Zapisz jako PDF**.
2. W gemini.google.com kliknij ikonę **➕ / wyślij** obok pola wiadomości.
3. Wybierz swój PDF.
4. Wyślij:

```text
Streść ten dokument w 5 punktach. Następnie wypisz wszelkie daty, nazwiska
lub kwoty, których nie powinienem przeoczyć. Jeśli coś jest niejasne, powiedz to.
```

### Krok 2 — Zadawaj pytania o plik

W tej samej rozmowie:
```text
Jaka jest jedna najważniejsza rzecz, którą muszę zrobić na podstawie tego dokumentu?
```

### Krok 3 — Pozwól Gemini odczytać zrzut ekranu

1. Naciśnij **Windows + Shift + S**, aby wyciąć fragment ekranu (to go kopiuje).
2. Wklej do pola wiadomości Gemini przez **Ctrl + V**.
3. Wypróbuj:

```text
Oto zrzut ekranu. Wyjaśnij, na co patrzę i do czego służy każdy przycisk.
```

### Krok 4 — Sztuczka dla początkujących: rozszyfruj błąd

Następnym razem, gdy **cokolwiek** pokaże komunikat błędu:
1. Wytnij go (**Windows + Shift + S**).
2. Wklej do Gemini z:

```text
Dostałem ten błąd na Windows. Wyjaśnij prostym językiem, co znaczy, i podaj
najbezpieczniejsze kroki naprawy. Załóż, że nie jestem techniczny.
```

Ta sztuczka oszczędzi Ci mnóstwo godzin.

---

## 📋 Co możesz wysłać — ściąga

| Typ pliku | Gemini potrafi… |
|-----------|-------------|
| PDF / Dokumenty / TXT | Streszczać, odpowiadać, wyciągać informacje |
| Arkusze / CSV | Wyjaśniać dane, wykrywać trendy, sugerować formuły |
| PNG / JPG (zrzut ekranu) | Odczytać tekst, wyjaśnić interfejs, rozszyfrować błędy |
| Zdjęcie dokumentu | Przepisać i streścić |
| Zdjęcie pisma odręcznego | Odczytać i przepisać |

> 💡 Gemini radzi sobie też z **długimi** dokumentami dzięki dużemu oknu kontekstu — wypróbuj cały raport, nie tylko stronę.

---

## ✅ Sprawdzenie

- [ ] Wysłałeś PDF i dostałeś streszczenie.
- [ ] Wkleiłeś zrzut ekranu (**Win+Shift+S**, potem **Ctrl+V**) i Gemini go opisał.
- [ ] Znasz sztuczkę „wklej komunikat błędu”.

---

## 🎯 Zadanie

Znajdź prawdziwy dokument, którego unikałeś (regulamin, formularz, gęsty wątek e-maili). Wyślij go i poproś Gemini, aby *„wyjaśnił, co to dla mnie znaczy i co muszę zrobić”*.

---

## 💡 Najważniejsze wnioski

- Gemini jest multimodalny — wysyłaj PDF-y/dokumenty/obrazy, a je czyta/widzi.
- **Win+Shift+S**, potem **Ctrl+V** wkleja zrzuty ekranu prosto do Gemini.
- Wklejanie komunikatów błędów to najszybszy sposób rozwiązywania problemów.
- Nigdy nie wysyłaj sekretów ani cudzych danych prywatnych.

🌐 [English](../../en/lessons/04-files-and-images.md) · [← Wstecz](03-podstawy-promptow.md) · [Strona kursu](../README.md) · [Dalej: Gemini w Chrome i Google →](05-gemini-w-chrome-i-google.md)
