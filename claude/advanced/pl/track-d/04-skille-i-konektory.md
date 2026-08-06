# D4 — Skille i konektory (MCP na abonamencie)

⏱️ **15 minut** · Ścieżka: 🅳 Moc abonamentu · Potrzebne: konto Claude.ai Pro/Max

🌐 [English](../../en/track-d/04-skills-and-connectors.md) · [← Wstecz](03-oszczedzaj-tokeny-i-limity.md) · [Indeks ścieżki](../README.md) · [Dalej: Agenci i Claude Code →](05-agenci-i-claude-code.md)

---

## 🧠 Teoria (5 min)

Dwie funkcje zamieniają Claude z „okienka czatu” w coś, co wpina się w Twoją realną pracę — i obie są **wliczone w abonament**, bez klucza API:

- **Skille** — pakiety wiedzy, które Claude ładuje, **gdy zadanie tego wymaga**. Na przykład Skille do budowania **Excela**, prezentacji **PowerPoint**, dokumentów **Word** i **PDF-ów**. Nie wołasz ich ręcznie; Claude sam sięga po właściwy Skill do zadania.
- **Konektory (MCP)** — połączenia Claude z **innymi narzędziami i danymi**: Twoim Google Drive, kalendarzem, bazą wiedzy czy serwerem programistycznym. MCP (Model Context Protocol) to otwarty standard za nimi. W Ścieżce A dodawałeś MCP do **Claude Desktop** przez edycję pliku konfiguracyjnego; tu używasz **wbudowanych konektorów** w aplikacjach Claude — kilka kliknięć, bez JSON-a.

Ujmij to tak: **Skille** dają Claude know-how; **konektory** dają Claude zasięg.

---

## 🛠️ Praktyka (9 min)

### Część 1 — Skille

1. Zacznij zadanie tworzące prawdziwy dokument, np.:

```text
Utwórz 3-slajdową prezentację PowerPoint streszczającą te notatki: <wklej kilka punktów>.
Daj mi plik .pptx do pobrania.
```

2. Claude rozpoznaje zadanie i używa **Skilla PowerPoint**, by zbudować prawdziwy `.pptx` do pobrania — nie tylko tekst opisujący slajdy.

3. Wypróbuj inny format, by poczuć zakres:

```text
Zamień te dane w schludny plik Excel z wierszem sumy i prostym wykresem:
<wklej małą tabelę>.
```

Opisujesz wynik; pasujący Skill tworzy plik.

> Skille ładują się **automatycznie** na podstawie zadania. Nie włączasz ich per wiadomość — po prostu poproś o rezultat, a Claude sięgnie po właściwy.

### Część 2 — Konektory (MCP)

1. Otwórz **Settings → Connectors** (nazwa może się różnić zależnie od aplikacji/planu). Zobaczysz dostępne konektory do włączenia.
2. Włącz taki, którego faktycznie używasz — np. **Google Drive** — i przejdź logowanie, o które poprosi. To autoryzuje Claude do dostępu **tylko** do tego, co zatwierdzisz.
3. W czacie użyj go:

```text
Znajdź mój dokument „Plan Q3” na Drive i streść jego 3 najważniejsze priorytety.
```

Claude sięga przez konektor, pobiera dokument i odpowiada — bez kopiuj-wklej.

### Część 3 — Połącz Skill i konektor

Nagroda to ich złożenie:

```text
Pobierz najnowsze liczby z mojego arkusza „Sprzedaż” na Drive, potem zbuduj
jednostronicowe podsumowanie PDF z krótkim wykresem. Daj mi plik.
```

Konektor pobiera dane; Skill buduje rezultat. To prawdziwy przepływ, w całości na Twoim abonamencie.

---

## 🔒 Bezpieczeństwo konektorów

| Nawyk | Dlaczego |
|-------|-----|
| Włączaj tylko konektory, których używasz | Mniej miejsc, do których Claude sięga |
| Przejrzyj dostęp, o który prosi przy logowaniu | Ty zatwierdzasz zakres |
| Preferuj tylko-odczyt, gdy dostępny | Mniejszy zasięg szkód |
| Odłączaj konektory, których przestałeś używać | Czysta, minimalna konfiguracja |
| Ty pozostajesz recenzentem tego, co robi | Człowiek w pętli |

---

## 🧩 Skille vs konektory

| | **Skille** | **Konektory (MCP)** |
|---|---|---|
| Dają Claude… | Know-how (zbuduj prezentację, arkusz, PDF) | Zasięg (Twój Drive, kalendarz, narzędzia) |
| Włączasz przez… | Nic — auto-ładowanie per zadanie | Włączenie + jednorazowe logowanie |
| Przykład | „Zrób mi PowerPoint” | „Znajdź mój dokument na Drive” |

---

## ✅ Sprawdzenie

- [ ] Skill wyprodukował prawdziwy plik do pobrania (Excel / PPTX / Word / PDF).
- [ ] Włączyłeś jeden konektor i użyłeś go w czacie.
- [ ] Połączyłeś konektor + Skill w jednym zadaniu.

---

## 🎯 Zadanie

Wybierz jeden powtarzalny rezultat, który robisz ręcznie (tygodniowa prezentacja, raport, tracker). Włącz konektor, który trzyma jego dane źródłowe, potem poproś Claude o pobranie danych i utworzenie pliku. Zapisz prompt do ponownego użycia.

---

## 💡 Najważniejsze wnioski

- **Skille** dają Claude know-how i ładują się **automatycznie** do zadania — prawdziwe pliki Excel/PPTX/Word/PDF, bez klucza API.
- **Konektory (MCP)** dają Claude zasięg w Twoje narzędzia; włączaj tylko to, czego używasz, i przeglądaj dostęp.
- **Składaj** je — konektor pobiera, Skill buduje — dla pełnych przepływów na abonamencie.

🌐 [English](../../en/track-d/04-skills-and-connectors.md) · [← Wstecz](03-oszczedzaj-tokeny-i-limity.md) · [Indeks ścieżki](../README.md) · [Dalej: Agenci i Claude Code →](05-agenci-i-claude-code.md)
