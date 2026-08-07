# D4 — Własne instrukcje i pamięć

⏱️ **15 minut** · Ścieżka: 🅳 Moc abonamentu · Wymagania: konto ChatGPT (zalecany Plus)

🌐 [English](../../en/track-d/04-custom-instructions-and-memory.md) · [← Poprzedni](03-oszczedzaj-uzycie-i-limity.md) · [Spis ścieżki](../README.md) · [Dalej: Agenci i Codex CLI →](05-agenci-i-codex-cli.md)

---

## 🧠 Teoria (4 min)

Możesz sprawić, że **każdy** czat ChatGPT będzie skrojony na miarę — bez powtarzania się — za pomocą dwóch wbudowanych kontrolek:

- **Własne instrukcje** — stałe „jak masz mi odpowiadać" (kim jesteś, ton, długość, format), które ChatGPT stosuje w każdym nowym czacie.
- **Pamięć** — fakty, które ChatGPT zapamiętuje o Tobie między czatami (preferencje, trwające projekty), byś przestał/a tłumaczyć od nowa. Możesz przeglądać, edytować i usuwać to, co zapisał.

I żeby odróżnić je od Custom GPT ze Ścieżki A:

| Potrzeba | Użyj |
|------|-----|
| Globalne „jak ze mną rozmawiać" | **Własne instrukcje** |
| Fakty, które ChatGPT ma po prostu znać o Tobie | **Pamięć** |
| Specjalista do jednego powtarzalnego zadania | **Custom GPT** (A1) |

> Dostępność i dokładne kontrolki pamięci różnią się w zależności od planu i są wdrażane z czasem. Własne instrukcje są szeroko dostępne.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Ustaw własne instrukcje

W ChatGPT → **Ustawienia → Personalizacja → Własne instrukcje**. Wypełnij pola, np.:

```text
O mnie: Jestem na Windowsie, pracuję w marketingu, wolę prosty język od żargonu.

Jak odpowiadać: Bądź zwięzły i zacznij od odpowiedzi. Numeruj kroki. Gdy proszę
o kod, podaj najpierw kod, potem krótkie wyjaśnienie.
```

Teraz nowe czaty startują z *Twoimi* domyślnymi ustawieniami — bez tłumaczenia za każdym razem.

### Krok 2 — Potwierdź, że zadziałało

Zacznij świeży czat i zadaj otwarte pytanie. Ton, długość i format powinny pasować do Twoich instrukcji. Dostrajaj sformułowania, aż będzie dobrze.

### Krok 3 — Zarządzaj pamięcią

W **Ustawienia → Personalizacja → Pamięć** przejrzyj, co ChatGPT zapisał. Możesz:
- **Dodać** fakt wprost („Zapamiętaj, że używam jednostek metrycznych").
- **Usunąć** cokolwiek nieaktualnego lub błędnego.
- **Wyłączyć** ją całkowicie lub użyć **czatu tymczasowego**, który nie czyta ani nie zapisuje pamięci.

Spróbuj powiedzieć ChatGPT coś trwałego („Uczę się Pythona") i sprawdź, czy pojawia się w Pamięci.

### Krok 4 — Steruj tonem także na bieżąco

Nawet bez ustawień ukształtuj dowolną pojedynczą odpowiedź:

```text
Przepisz to jako trzy zwięzłe punkty, które zabiegany menedżer przejrzy w mgnieniu oka.
```

Długość i ton są Twoje do ustawienia — a to również oszczędza użycie (D3).

### Krok 5 — Utrzymuj czystość i prywatność

- **Przeglądaj** pamięć od czasu do czasu; usuwaj to, co już nieaktualne.
- Nie pozwól, by pamięć trzymała **sekrety** lub wrażliwe dane osobowe.
- Użyj **czatu tymczasowego** do czegokolwiek, czego nie chcesz zapamiętać.

> ⚠️ Własne instrukcje i pamięć kształtują każdą odpowiedź. Przycinaj je, by nic nieaktualnego ani prywatnego nie wpływało na przyszłe czaty.

---

## 🧩 Kontrolki dopasowania

| Kontrolka | Użyj do |
|---------|-----------|
| **Własne instrukcje** | Ustaw globalny głos i format |
| **Pamięć** | Przestań tłumaczyć kontekst (przeglądaj/przycinaj) |
| **Custom GPT** | Specjalista do jednego powtarzalnego zadania |
| **Czat tymczasowy** | Jednorazowy bez odczytu/zapisu pamięci |

---

## ✅ Sprawdzian

- [ ] Ustawiłeś/aś własne instrukcje i widziałeś/aś, jak nowy czat ich przestrzega.
- [ ] Przejrzałeś/aś pamięć i dodałeś/aś lub usunąłeś/ęłaś element.
- [ ] Umiesz wyjaśnić różnicę: własne instrukcje vs pamięć vs Custom GPT.
- [ ] Wiesz, jak użyć czatu tymczasowego dla prywatności.

---

## 🎯 Praca domowa

Napisz własne instrukcje ujmujące, jak lubisz odpowiedzi (długość, ton, format). Dodaj jeden trwały fakt do pamięci o tym, jak pracujesz, potem przejrzyj Pamięć i usuń nieaktualne. Wypróbuj czat tymczasowy i potwierdź, że nic nie zapisuje.

---

## 💡 Najważniejsze wnioski

- **Własne instrukcje** ustawiają globalny głos; **pamięć** oszczędza tłumaczenie od nowa (przeglądaj i przycinaj).
- **Custom GPT** to specjalista do jednego zadania — inny niż globalna personalizacja.
- Trzymaj oba **czyste i bez sekretów** i używaj **czatu tymczasowego**, gdy nie chcesz czegoś zapamiętać.

🌐 [English](../../en/track-d/04-custom-instructions-and-memory.md) · [← Poprzedni](03-oszczedzaj-uzycie-i-limity.md) · [Spis ścieżki](../README.md) · [Dalej: Agenci i Codex CLI →](05-agenci-i-codex-cli.md)
