# F4 — Konektory produktywności (Drive, Gmail, Kalendarz, Slack, Notion)

⏱️ **15 minut** · Ścieżka: 🅵 Poza czatem · Potrzebne: konto Pro/Max + co najmniej jedno konto do podłączenia

🌐 [English](../../en/track-f/04-productivity-connectors.md) · [← Wstecz](03-badania-i-web.md) · [Indeks ścieżki](../README.md) · [Dalej: Pamięć, style i przepływ →](05-pamiec-style-i-przeplyw.md)

---

## 🧠 Teoria (4 min)

Ścieżka E omówiła programistyczne serwery MCP (GitHub, Atlassian, Azure). **Konektory produktywności** to te codzienne — i największy zysk jakości życia na abonamencie:

- **Google Drive** — znajduj i czytaj dokumenty/arkusze.
- **Gmail** — przeszukuj i streszczaj e-maile (szkicuj odpowiedzi z zatwierdzeniem).
- **Google Calendar** — widz swój kalendarz, znajduj wolne okna.
- **Slack** — nadrabiaj kanały, streszczaj wątki.
- **Notion** — przeszukuj strony, pobieraj notatki.

To **konektory zdalne**: włączasz jeden i logujesz przez OAuth — bez pliku konfiguracyjnego, nic do instalacji. Obowiązuje ta sama dyscyplina co w Ścieżce E: **najmniejsze uprawnienia, najpierw czytaj, zatwierdzaj każdy zapis.**

> Dostępne konektory zależą od planu i regionu, a katalog rośnie z czasem. Włączaj je w **Settings → Connectors**.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Podłącz jeden, którego faktycznie używasz

**Settings → Connectors** → wybierz jeden (zacznij od **Google Drive** lub **Calendar**) → **Connect** → przejdź OAuth i zatwierdź dostęp, o który prosi.

> Zatwierdź tylko potrzebny zakres. Konektor możesz później odłączyć.

### Krok 2 — Najpierw wygrane tylko-odczyt

Wypróbuj bezpieczne, wartościowe pytania:

```text
Znajdź mój dokument „Plan Q3” na Drive i streść jego 3 najważniejsze priorytety.
```
```text
Co mam w kalendarzu jutro i gdzie są luki dłuższe niż 45 minut?
```
```text
Streść ostatnie 20 wiadomości w kanale Slack #announcements.
```

Natychmiastowa dźwignia — Claude sięga do Twoich narzędzi zamiast kopiuj-wklej.

### Krok 3 — Szkicuj, nie wysyłaj automatycznie

Przy czymkolwiek, co wychodzi z Twoich rąk, trzymaj bramkę człowieka:

```text
Naszkicuj odpowiedź na ostatni e-mail od <imię> potwierdzającą spotkanie.
Pokaż mi szkic — NIE wysyłaj go.
```

Claude pisze; **Ty** wysyłasz. Nigdy nie pozwól mu pisać do ludzi bez Twojej recenzji.

### Krok 4 — Połącz konektory + inne funkcje

Magia to składanie:

```text
Znajdź notatki ze spotkań z tego tygodnia na Drive, potem naszkicuj krótką aktualizację Slack
streszczającą decyzje i właścicieli. Pokaż mi aktualizację przed publikacją.
```

Albo z narzędziem analizy (F2):

```text
Pobierz arkusz „Sprzedaż” z Drive i policz sumy na region z wykresem.
```

### Krok 5 — Zamień powtarzalne roboty w jeden prompt

Zapisuj prompty do ponownego użycia (biblioteka ze Ścieżki A):

```text
Poranny brief: mój kalendarz na dziś, pilne nieprzeczytane maile (tylko lista, bez odpowiedzi)
i wyróżnienia z nieprzeczytanego Slacka #team. Zmieść się w 150 słowach.
```

Jeden prompt, cały poranny kontekst.

---

## 🔒 Bezpieczeństwo konektorów

| Nawyk | Dlaczego |
|-------|-----|
| Włączaj tylko to, czego używasz | Mniej miejsc, do których Claude sięga |
| Przejrzyj zakres przy logowaniu | Ty zatwierdzasz dostęp |
| Tylko-odczyt, gdzie się da | Mniejszy zasięg szkód |
| Szkicuj, nigdy nie wysyłaj auto | Kontrolujesz, co wychodzi |
| Odłączaj stare konektory | Czysta, minimalna konfiguracja |

---

## 🧩 Wartościowe ruchy

| Poproś o… | Dostajesz |
|----------|---------|
| „Znajdź + streść mój dokument na Drive” | Brak polowania po folderach |
| „Mój kalendarz na dziś + wolne okna” | Natychmiastowy widok grafiku |
| „Streść ten kanał/wątek Slack” | Nadrobienie w sekundy |
| „Naszkicuj odpowiedź na e-mail (nie wysyłaj)” | Przejrzany szkic |
| „Poranny brief z moich narzędzi” | Kontekst dnia jednym promptem |

---

## ✅ Sprawdzenie

- [ ] Podłączyłeś co najmniej jeden konektor produktywności.
- [ ] Uruchomiłeś zapytania tylko-odczyt przeciw niemu.
- [ ] Kazałeś Claude **naszkicować** (nie wysłać) coś i to zatwierdziłeś.
- [ ] Połączyłeś konektor z inną funkcją (analiza, Slack itd.).

---

## 🎯 Zadanie

Zbuduj własny prompt „poranny brief” po konektorach, których używasz, trzymaj go tylko-odczyt i zapisz do ponownego użycia. Potem naszkicuj jedną prawdziwą wiadomość (e-mail lub Slack) i wyślij ją sam po recenzji.

---

## 💡 Najważniejsze wnioski

- **Konektory produktywności** (Drive, Gmail, Kalendarz, Slack, Notion) wpinają Claude w codzienną pracę — OAuth, bez instalacji.
- **Najpierw czytaj, szkicuj nie wysyłaj auto, najmniejsze uprawnienia** — ta sama dyscyplina co przy programistycznym MCP.
- Nagrodą jest **składanie** ich w rutyny jednego promptu jak poranny brief.

🌐 [English](../../en/track-f/04-productivity-connectors.md) · [← Wstecz](03-badania-i-web.md) · [Indeks ścieżki](../README.md) · [Dalej: Pamięć, style i przepływ →](05-pamiec-style-i-przeplyw.md)
