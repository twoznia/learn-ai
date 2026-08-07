# F2 — Konektory i praca z Twoimi aplikacjami

⏱️ **15 minut** · Ścieżka: 🅵 Poza czatem · Wymagania: konto ChatGPT Plus/Pro + aplikacja do podłączenia

🌐 [English](../../en/track-f/02-connectors-and-apps.md) · [← Poprzedni](01-deep-research.md) · [Spis ścieżki](../README.md) · [Dalej: Generowanie obrazów →](03-generowanie-obrazow.md)

---

## 🧠 Teoria (4 min)

Ścieżka E omawiała narzędzia deweloperskie przez MCP w Codex CLI. W **aplikacji ChatGPT** codzienne integracje to **konektory** — łączą ChatGPT z Twoimi aplikacjami, by mógł znaleźć i użyć Twoich prawdziwych treści:

- **Google Drive** — znajdź i czytaj swoje dokumenty/arkusze.
- **Gmail / Kalendarz** — przeszukaj pocztę, zobacz harmonogram (gdzie dostępne).
- **GitHub, SharePoint i inne** — w zależności od planu i regionu.

Włączasz konektor i logujesz się przez OAuth — bez pliku konfiguracyjnego, bez instalacji. Obowiązuje ta sama dyscyplina co ze Ścieżki E: **najmniejszy przywilej, najpierw czytaj, zatwierdzaj każdy zapis.**

> Dostępne konektory zależą od planu i regionu i zmieniają się z czasem. Włącz je w **Ustawienia → Konektory** (lub menu „praca z aplikacjami" w aplikacji).

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Podłącz taki, którego naprawdę używasz

**Ustawienia → Konektory** → wybierz jeden (zacznij od **Google Drive**) → **Połącz** → dokończ OAuth i zatwierdź dostęp, o który prosi.

> Zatwierdź tylko zakres, którego potrzebujesz. Każdy konektor możesz później odłączyć.

### Krok 2 — Najpierw zwycięstwa tylko-do-odczytu

```text
Znajdź mój dokument „Plan Q3" na Drive i podsumuj jego 3 najważniejsze priorytety.
```
```text
Co mam jutro w kalendarzu i gdzie są luki dłuższe niż 45 minut?
```

Natychmiastowa dźwignia — ChatGPT sięga do Twoich treści zamiast kopiuj-wklej.

### Krok 3 — Szkicuj, nie wysyłaj automatycznie

Dla wszystkiego, co wychodzi z Twoich rąk, trzymaj bramkę człowieka:

```text
Naszkicuj odpowiedź na najnowszy e-mail od <imię> potwierdzającą spotkanie.
Pokaż mi szkic — NIE wysyłaj go.
```

ChatGPT go pisze; **Ty** go wysyłasz.

### Krok 4 — Łącz konektory + inne funkcje

```text
Znajdź notatki z tegotygodniowych spotkań na Drive, potem naszkicuj krótki e-mail
z podsumowaniem decyzji i odpowiedzialnych. Pokaż mi szkic, zanim wyślę.
```

Lub z Zaawansowaną analizą danych (A3):

```text
Pobierz arkusz „Sprzedaż" z Drive i policz sumy na region z wykresem.
```

### Krok 5 — Zamień powtarzalne roboty w jeden prompt

Zapisz prompty do ponownego użycia (A2):

```text
Poranny briefing: mój dzisiejszy kalendarz, pilne nieprzeczytane e-maile (tylko lista, bez odpowiedzi)
i cokolwiek na termin w moich współdzielonych dokumentach Drive. Zmieść się w 150 słowach.
```

Jeden prompt, cały poranny kontekst.

### Krok 6 — Konektory vs Akcje Custom GPT vs MCP

- **Konektory** — włączane kliknięciem, dla *Twoich* aplikacji w aplikacji ChatGPT (ta lekcja).
- **Akcje Custom GPT** (A1) — dają Custom GPT jedno konkretne API do wywołania.
- **MCP w Codeksie** (Ścieżka E) — deweloperska, uniwersalna droga w CLI.

---

## 🔒 Bezpieczeństwo konektorów

| Nawyk | Dlaczego |
|-------|-----|
| Włączaj tylko to, czego używasz | Mniej miejsc, do których ChatGPT sięga |
| Przejrzyj zakres przy logowaniu | Ty zatwierdzasz dostęp |
| Tylko-do-odczytu, gdzie możliwe | Niższy zasięg rażenia |
| Szkicuj, nigdy nie wysyłaj automatycznie | Kontrolujesz, co wychodzi |
| Odłączaj nieświeże konektory | Czysta, minimalna konfiguracja |

---

## ✅ Sprawdzian

- [ ] Podłączyłeś/aś co najmniej jeden konektor.
- [ ] Uruchomiłeś/aś wobec niego zapytania tylko-do-odczytu.
- [ ] Kazałeś/aś ChatGPT **naszkicować** (nie wysłać) coś i zatwierdziłeś/aś to.
- [ ] Skomponowałeś/aś konektor z inną funkcją (analiza danych itp.).

---

## 🎯 Praca domowa

Zbuduj prompt „poranny briefing" łączący konektory, których używasz, trzymaj go tylko-do-odczytu i zapisz. Potem naszkicuj jeden prawdziwy e-mail i wyślij go sam/a po przejrzeniu.

---

## 💡 Najważniejsze wnioski

- **Konektory** łączą ChatGPT z Twoimi aplikacjami (Drive, Gmail, Kalendarz…) — OAuth, bez instalacji.
- **Najpierw czytaj, szkicuj nie wysyłaj automatycznie, najmniejszy przywilej** — to samo bezpieczeństwo co przy deweloperskim MCP.
- Konektory (aplikacja) vs Akcje Custom GPT vs MCP (Codex) to trzy odrębne powierzchnie — wybieraj według zadania.

🌐 [English](../../en/track-f/02-connectors-and-apps.md) · [← Poprzedni](01-deep-research.md) · [Spis ścieżki](../README.md) · [Dalej: Generowanie obrazów →](03-generowanie-obrazow.md)
