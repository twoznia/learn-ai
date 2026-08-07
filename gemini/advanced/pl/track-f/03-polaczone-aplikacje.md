# F3 — Połączone aplikacje i Google Workspace

⏱️ **15 minut** · Ścieżka: 🅵 Poza czatem · Potrzebne: aplikacja Gemini (zalecane Pro), konto Google

🌐 [English](../../en/track-f/03-connected-apps.md) · [← Wstecz](02-analiza-danych.md) · [Indeks ścieżki](../README.md) · [Dalej: Twórz z Gemini →](04-tworz-z-gemini.md)

---

## 🧠 Teoria (4 min)

Ścieżka E łączyła narzędzia programistyczne przez MCP w **CLI**. W **aplikacji Gemini** codzienne integracje to **rozszerzenia / połączone aplikacje** — a ponieważ jesteś już w świecie Google, to największy zysk jakości życia:

- **Google Workspace** — Gmail, Drive, Docs, Kalendarz (znajdź, streść, naszkicuj).
- **Google Maps** — miejsca, trasy, pomoc w podróży.
- **YouTube** — streść lub znajdź filmy.
- Plus inne rozszerzenia w miarę pojawiania się.

Włączasz je w aplikacji i używają Twojego logowania Google — bez konfiguracji, bez instalacji. Ta sama dyscyplina co przy MCP: **najpierw czytaj, szkicuj nie wysyłaj auto, najmniejsze uprawnienia.**

> Dostępne rozszerzenia/połączone aplikacje zależą od planu i regionu i zmieniają się z czasem. Włączaj je w menu **narzędzia / rozszerzenia / połączone aplikacje** aplikacji.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Włącz te, których używasz

W aplikacji Gemini otwórz menu **rozszerzenia / połączone aplikacje** i włącz **Google Workspace** (i Maps/YouTube, jeśli przydatne). Zatwierdź dostęp, o który prosi.

### Krok 2 — Najpierw wygrane tylko-odczyt

```text
Znajdź mój dokument „Plan Q3” na Drive i streść jego 3 najważniejsze priorytety.
```
```text
Co mam w kalendarzu jutro i gdzie są luki dłuższe niż 45 minut?
```
```text
Streść ostatni wątek e-mailowy od <imię> i wypisz zadania do zrobienia.
```

Natychmiastowa dźwignia — Gemini sięga do Twoich aplikacji Google zamiast kopiuj-wklej.

### Krok 3 — Szkicuj, nie wysyłaj auto

Przy czymkolwiek, co wychodzi z rąk, trzymaj bramkę:

```text
Naszkicuj odpowiedź na ostatni e-mail od <imię> potwierdzającą spotkanie.
Pokaż mi szkic — NIE wysyłaj go.
```

Gemini pisze; **Ty** wysyłasz.

### Krok 4 — Połącz aplikacje + inne funkcje

```text
Znajdź notatki ze spotkań z tego tygodnia na Drive, potem naszkicuj krótki e-mail
podsumowujący decyzje i właścicieli. Pokaż szkic, zanim wyślę.
```

Albo z analizą danych (F2):

```text
Pobierz arkusz „Sprzedaż” z Drive i policz sumy na region z wykresem.
```

### Krok 5 — Zamień powtarzalne roboty w jeden prompt

Zapisuj prompty do ponownego użycia (Ścieżka A2):

```text
Poranny brief: mój kalendarz na dziś, pilne nieprzeczytane maile (tylko lista, bez odpowiedzi)
i cokolwiek do zrobienia w Docs, które udostępniam. Zmieść się w 150 słowach.
```

Jeden prompt, cały poranny kontekst.

### Krok 6 — Gemini wprost w Workspace

Nie zapomnij o bocznym panelu **wewnątrz** Gmaila/Docs/Sheets. Ta sama moc, w aplikacji, gdzie już pracujesz — „streść ten wątek”, „pomóż napisać tę sekcję”.

---

## 🔒 Bezpieczeństwo połączonych aplikacji

| Nawyk | Dlaczego |
|-------|-----|
| Włączaj tylko to, czego używasz | Mniej miejsc, do których Gemini sięga |
| Przejrzyj dostęp przy włączaniu | Ty zatwierdzasz zakres |
| Tylko-odczyt, gdzie się da | Mniejszy zasięg szkód |
| Szkicuj, nigdy nie wysyłaj auto | Kontrolujesz, co wychodzi |
| Wyłącz aplikacje, których przestałeś używać | Czysta, minimalna konfiguracja |

---

## 🧩 Wartościowe ruchy

| Poproś o… | Dostajesz |
|----------|---------|
| „Znajdź + streść mój dokument na Drive” | Brak polowania po folderach |
| „Mój kalendarz na dziś + wolne okna” | Natychmiastowy widok grafiku |
| „Streść ten wątek e-mailowy” | Nadrobienie w sekundy |
| „Naszkicuj odpowiedź na e-mail (nie wysyłaj)” | Przejrzany szkic |
| „Poranny brief z moich aplikacji” | Kontekst dnia jednym promptem |

---

## ✅ Sprawdzenie

- [ ] Włączyłeś co najmniej jedną połączoną aplikację (Workspace).
- [ ] Uruchomiłeś zapytania tylko-odczyt przeciw niej.
- [ ] Kazałeś Gemini **naszkicować** (nie wysłać) coś i to zatwierdziłeś.
- [ ] Połączyłeś aplikację z inną funkcją (analiza danych itd.).

---

## 🎯 Zadanie

Zbuduj prompt „poranny brief” po aplikacjach Google, których używasz, trzymaj go tylko-odczyt i zapisz. Potem naszkicuj jeden prawdziwy e-mail i wyślij go sam po recenzji.

---

## 💡 Najważniejsze wnioski

- **Połączone aplikacje / rozszerzenia** wpinają Gemini w Gmaila, Drive, Kalendarz, Maps, YouTube — logowaniem Google, bez instalacji.
- **Najpierw czytaj, szkicuj nie wysyłaj auto, najmniejsze uprawnienia** — to samo bezpieczeństwo co MCP.
- Składaj je w **rutyny jednego promptu** i pamiętaj, że Gemini żyje też **wewnątrz** Workspace.

🌐 [English](../../en/track-f/03-connected-apps.md) · [← Wstecz](02-analiza-danych.md) · [Indeks ścieżki](../README.md) · [Dalej: Twórz z Gemini →](04-tworz-z-gemini.md)
