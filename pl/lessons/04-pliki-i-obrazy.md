# Lekcja 04 — Praca z plikami i obrazami

⏱️ **10 minut** · Poziom: Początkujący · Potrzebne: claude.ai + dowolny PDF/obraz na komputerze

🌐 [English](../../en/lessons/04-files-and-images.md) · [← Wstecz](03-podstawy-promptow.md) · [Strona kursu](../README.md) · [Dalej: Instalacja Claude Desktop →](05-instalacja-claude-desktop.md)

---

## 🧠 Teoria (3 min)

Claude nie ogranicza się do tekstu, który wpisujesz. Możesz **wysyłać pliki**, a Claude je przeczyta:

- **PDF-y, dokumenty Word, arkusze, pliki tekstowe** → Claude czyta treść.
- **Obrazy i zrzuty ekranu** → Claude potrafi je *zobaczyć* (wykresy, zdjęcia, pismo odręczne, komunikaty błędów).

To ogromne ułatwienie dla początkujących, bo możesz wskazać Claude prawdziwy dokument i powiedzieć „wyjaśnij to” zamiast przepisywać wszystko.

> ⚠️ **Uwaga o prywatności:** wysyłaj tylko pliki, które możesz udostępnić usłudze w chmurze. Nie wysyłaj haseł, cudzych danych prywatnych ani poufnych informacji firmowych, których nie wolno Ci udostępniać. Więcej w Lekcji 17.

---

## 🛠️ Praktyka (6 min)

### Krok 1 — Streść PDF

1. Znajdź dowolny PDF na komputerze (instrukcję, raport, paragon). Nie masz PDF-a? W Edge otwórz dowolną stronę → **menu ⋯ → Drukuj → Zapisz jako PDF**.
2. W claude.ai kliknij ikonę **📎 załącz** obok pola wiadomości.
3. Wybierz swój PDF.
4. Wyślij taki prompt:

```text
Streść ten dokument w 5 punktach. Następnie wypisz wszelkie daty, nazwiska
lub kwoty, których nie powinienem przeoczyć. Jeśli coś jest niejasne, powiedz to.
```

### Krok 2 — Zadawaj pytania o plik

W tej samej rozmowie dopytaj:
```text
Jaka jest jedna najważniejsza rzecz, którą muszę zrobić na podstawie tego dokumentu?
```

### Krok 3 — Pozwól Claude odczytać zrzut ekranu

1. Naciśnij **Windows + Shift + S**, aby wyciąć fragment ekranu (to go kopiuje).
2. Wklej bezpośrednio do pola wiadomości claude.ai przez **Ctrl + V**.
3. Wypróbuj:

```text
Oto zrzut ekranu. Wyjaśnij, na co patrzę i do czego służy każdy przycisk.
```

### Krok 4 — Sztuczka dla początkujących: rozszyfruj błąd

Następnym razem, gdy **cokolwiek** na komputerze pokaże komunikat błędu:
1. Wytnij go (**Windows + Shift + S**).
2. Wklej do Claude z:

```text
Dostałem ten błąd na Windows. Wyjaśnij prostym językiem, co znaczy, i podaj
najbezpieczniejsze kroki naprawy. Załóż, że nie jestem techniczny.
```

Ta jedna sztuczka oszczędzi Ci mnóstwo godzin.

---

## 📋 Co możesz wysłać — ściąga

| Typ pliku | Claude potrafi… |
|-----------|-------------|
| PDF / Word / TXT | Streszczać, odpowiadać na pytania, wyciągać informacje |
| Excel / CSV | Wyjaśniać dane, wykrywać trendy, sugerować formuły |
| PNG / JPG (zrzut ekranu) | Odczytać tekst, wyjaśnić interfejs, rozszyfrować błędy |
| Zdjęcie dokumentu | Przepisać i streścić |
| Zdjęcie pisma odręcznego | Odczytać i przepisać |

---

## ✅ Sprawdzenie

- [ ] Wysłałeś PDF i dostałeś streszczenie.
- [ ] Wkleiłeś zrzut ekranu (**Win+Shift+S**, potem **Ctrl+V**) i Claude go opisał.
- [ ] Znasz sztuczkę „wklej komunikat błędu”.

---

## 🎯 Zadanie

Znajdź prawdziwy dokument, którego unikałeś (regulamin, formularz, gęsty wątek e-maili). Wyślij go i poproś Claude, aby *„wyjaśnił, co to dla mnie znaczy i co muszę zrobić”*.

---

## 💡 Najważniejsze wnioski

- 📎 Wysyłaj PDF-y/dokumenty; Claude je czyta.
- **Win+Shift+S**, potem **Ctrl+V** wkleja zrzuty ekranu prosto do Claude.
- Wklejanie komunikatów błędów to najszybszy sposób rozwiązywania problemów z komputerem.
- Nigdy nie wysyłaj sekretów ani cudzych danych prywatnych.

🌐 [English](../../en/lessons/04-files-and-images.md) · [← Wstecz](03-podstawy-promptow.md) · [Strona kursu](../README.md) · [Dalej: Instalacja Claude Desktop →](05-instalacja-claude-desktop.md)
