# G3 — Wbudowane narzędzia i przepływ zatwierdzania

⏱️ **15 minut** · Ścieżka: 🅶 Gemini CLI w głąb · Potrzebne: Gemini CLI zainstalowany i zalogowany

🌐 [English](../../en/track-g/03-tools-and-approvals.md) · [← Wstecz](02-wlasne-komendy.md) · [Indeks ścieżki](../README.md) · [Dalej: Checkpointy i cofanie →](04-checkpointy-i-cofanie.md)

---

## 🧠 Teoria (5 min)

Gemini CLI jest agentowy, bo ma **wbudowane narzędzia** — potrafi czytać i zapisywać pliki, uruchamiać polecenia powłoki i pobierać/przeszukiwać web. Zrozumienie tych narzędzi i, co kluczowe, **przepływu zatwierdzania** czyni CLI potężnym i bezpiecznym.

Typowe wbudowane narzędzia:

| Narzędzie | Robi |
|------|------|
| **Odczyt pliku** | Czyta zawartość pliku |
| **Zapis / Edycja** | Tworzy lub zmienia plik |
| **Powłoka (Shell)** | Uruchamia polecenie terminala |
| **Pobierz / szukaj web** | Pobiera stronę lub przeszukuje web |

Model bezpieczeństwa: przy czymkolwiek, co **zmienia system** (zapis pliku, uruchomienie polecenia), CLI **wstrzymuje się i pyta** — zatwierdzasz, edytujesz lub odrzucasz. Akcje tylko-odczyt zwykle działają swobodnie. Twoje zadanie: **zostać recenzentem**.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Wypisz narzędzia

```text
/tools
```

Zobacz dokładnie, co CLI potrafi od ręki. To jego „ręce”.

### Krok 2 — Zobacz działanie narzędzia tylko-odczyt

Poproś o coś, co wymaga tylko czytania:

```text
Przeczytaj README w tym folderze i streść, co robi projekt.
```

Czyta i odpowiada — bez zatwierdzenia dla bezpiecznej akcji tylko-odczyt.

### Krok 3 — Wywołaj prośbę o zatwierdzenie

Teraz poproś o zmianę:

```text
Utwórz plik hello.txt zawierający przyjazne jednolinijkowe powitanie.
```

CLI pokazuje, co chce zrobić, i **pyta o zatwierdzenie**. Przeczytaj proponowaną akcję, potem zatwierdź. Jesteś bramką na każdej zmianie.

### Krok 4 — Poznaj wybory zatwierdzania

Gdy zapytany, zwykle możesz:
- **Zatwierdź raz** — pozwól tylko na tę akcję.
- **Zatwierdź zawsze** (dla tego rodzaju/polecenia) — przestań być pytany o to samo bezpieczne.
- **Odrzuć** — odmów i powiedz, co zrobić zamiast tego.

Przyznawaj „zawsze” tylko akcjom, których jesteś pewny (np. formater). Zatwierdzaj każdą, która usuwa, wdraża lub wysyła.

### Krok 5 — Zobacz polecenie powłoki

```text
Wypisz pliki w tym folderze i powiedz mi, który jest największy.
```

Proponuje polecenie powłoki; zatwierdź je i zobacz wynik. Ponieważ najpierw zobaczyłeś dokładne polecenie, nie ma niespodzianek.

### Krok 6 — Trzymaj bramkę uczciwą

- Czytaj proponowaną akcję **przed** zatwierdzeniem — nie przybijaj pieczątki.
- Bądź szczególnie ostrożny z **powłoką** i **zapisem** przy czymkolwiek ważnym.
- CLI ma szybsze tryby „auto-zatwierdzania” (kolejna lekcja dotyka bezpieczeństwa) — nie włączaj ich, aż zaufasz konfiguracji i jesteś w bezpiecznym folderze.

---

## 🧩 Bezpieczeństwo narzędzi w skrócie

| Akcja | Zatwierdzenie |
|--------|----------|
| Odczyt pliku, szukanie w web | Zwykle działa swobodnie (bezpieczne) |
| Zapis / edycja pliku | Pyta najpierw — przejrzyj |
| Uruchomienie polecenia powłoki | Pyta najpierw — przeczytaj polecenie |
| Cokolwiek destrukcyjnego | Pyta najpierw — bądź rozważny |

> ⚠️ **Jesteś recenzentem.** CLI może dotknąć prawdziwych plików i uruchomić prawdziwe polecenia. Pracuj w dedykowanym folderze (lub gałęzi git), czytaj każdą proponowaną akcję i zatwierdzaj zmiany, zamiast uruchamiać wszystko automatycznie.

---

## ✅ Sprawdzenie

- [ ] Wypisałeś wbudowane narzędzia przez `/tools`.
- [ ] Zobaczyłeś akcję tylko-odczyt działającą bez zatwierdzenia.
- [ ] Zatwierdziłeś zapis pliku i polecenie powłoki po ich przeczytaniu.
- [ ] Rozumiesz zatwierdź-raz vs zatwierdź-zawsze vs odrzuć.

---

## 🎯 Zadanie

Daj CLI małe wieloetapowe zadanie w folderze roboczym (utwórz plik, wypisz go, edytuj). Zatwierdzaj każdą akcję rozważnie, czytając proponowane polecenie za każdym razem. Zanotuj, które akcje ustawiłbyś na „zawsze”.

---

## 💡 Najważniejsze wnioski

- Moc CLI bierze się z **wbudowanych narzędzi** (odczyt, zapis/edycja, powłoka, web) — zobacz je przez `/tools`.
- **Przepływ zatwierdzania** bramkuje każdą akcję zmieniającą system: zatwierdź raz, zatwierdź zawsze (tylko bezpieczne) lub odrzuć.
- **Zostań recenzentem** — czytaj każdą proponowaną akcję, pracuj w bezpiecznym folderze i nie auto-uruchamiaj, aż zaufasz.

🌐 [English](../../en/track-g/03-tools-and-approvals.md) · [← Wstecz](02-wlasne-komendy.md) · [Indeks ścieżki](../README.md) · [Dalej: Checkpointy i cofanie →](04-checkpointy-i-cofanie.md)
