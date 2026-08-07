# Lekcja 08 — Dawanie Copilotowi właściwego kontekstu

⏱️ **11 minut** · Poziom: Średni · Wymagania: VS Code + Copilot, projekt wieloplikowy

🌐 [English](../../en/lessons/08-context-participants-references.md) · [← Poprzednia](07-wlasne-instrukcje.md) · [Strona kursu](../README.md) · [Dalej: Podstawy Git i GitHub →](09-podstawy-git-i-github.md)

---

## 🧠 Teoria (4 min)

Copilot odpowiada najlepiej, gdy patrzy na **właściwy kontekst**. VS Code daje precyzyjne sposoby, by na niego wskazać:

- **@ uczestnicy** — specjaliści, do których się zwracasz, jak **@workspace** (cały projekt), **@vscode** (sam edytor), **@terminal** (powłoka/polecenia). Wciągają istotny kontekst.
- **# referencje** — dołącz konkretny **#file**, zaznaczenie, symbol lub inny zasób, by Copilot użył dokładnie tego.
- **Zestaw roboczy** — w trybie Edit/Agent pliki, które dodałeś/aś.

Zamiast liczyć, że Copilot zgadnie, **mówisz mu, gdzie patrzeć**. To różnica między ogólną odpowiedzią a osadzoną w Twoim kodzie.

> Nazwy uczestników i referencji (np. `@workspace`, `#file`) różnią się zależnie od wersji. Wpisz **@** lub **#** w czacie, by zobaczyć dostępne u Ciebie.

---

## 🛠️ Praktyka (7 min)

### Krok 1 — Zapytaj o cały projekt

```text
@workspace Where is the greeting text defined, and which files would I change
to add a new language?
```

`@workspace` przeszukuje projekt i odpowiada **prawdziwymi nazwami plików**.

### Krok 2 — Odwołaj się do konkretnego pliku

Wpisz `#` i wybierz plik (lub `#file`):

```text
Using #greetings.py, add a "fr" (French) greeting consistent with the others.
```

Teraz Copilot pracuje z *tego* pliku konkretnie.

### Krok 3 — Poproś edytor o pomoc

```text
@vscode How do I change my keyboard shortcut for accepting a Copilot suggestion?
```

`@vscode` zna ustawienia i polecenia VS Code.

### Krok 4 — Uzyskaj pomoc z poleceniami

```text
@terminal How do I find and kill the process using port 5000 on Windows?
```

`@terminal` świetnie sprawdza się przy poleceniach powłoki, których nie pamiętasz.

### Krok 5 — Dołącz zaznaczenie

Zaznacz kilka linii, otwórz czat w linii (**Ctrl+I**) i zapytaj *tylko o to* — zaznaczenie jest kontekstem.

### Krok 6 — Łącz dla precyzji

```text
@workspace #app.py Add a --language command-line flag and pass it through to
get_greeting. Show diffs for every file you change.
```

Konkretny uczestnik + konkretny plik + jasna prośba = osadzona, dająca się przejrzeć odpowiedź.

---

## 🧩 Narzędzia kontekstu

| Narzędzie | Użyj do |
|------|-----------|
| **@workspace** | Pytać o / zmieniać cały projekt |
| **@vscode** | Ustawienia edytora, skróty, polecenia |
| **@terminal** | Pomoc z powłoką/poleceniami |
| **#file / #selection** | Wskazać dokładne pliki lub kod |
| Zestaw roboczy (Edit/Agent) | Ograniczyć zmianę wieloplikową |

> Im precyzyjniej ograniczysz kontekst, tym lepiej — i tym mniej niespodzianek przy przeglądaniu diffa.

---

## ✅ Sprawdzian

- [ ] Użyłeś/aś **@workspace** i dostałeś/aś odpowiedzi z prawdziwymi nazwami plików.
- [ ] Odwołałeś/aś się do konkretnego pliku przez **#**.
- [ ] Użyłeś/aś **@vscode** i **@terminal** do pomocy z edytorem/powłoką.
- [ ] Połączyłeś/aś uczestnika + referencję pliku w jednej prośbie.

---

## 🎯 Praca domowa

W projekcie wieloplikowym użyj `@workspace`, by zapytać „jak dane przepływają przez tę aplikację?" Potem zrób jedną zmianę ograniczoną referencją `#file` i przejrzyj diff. Zauważ, jak ograniczanie kontekstu poprawia trafność.

---

## 💡 Najważniejsze wnioski

- **@uczestnicy** (`@workspace`, `@vscode`, `@terminal`) wnoszą właściwy rodzaj kontekstu.
- **# referencje** wskazują Copilotowi dokładne pliki, zaznaczenia lub symbole.
- Precyzyjne ograniczanie kontekstu zamienia ogólne odpowiedzi w osadzone w **Twoim** kodzie.

🌐 [English](../../en/lessons/08-context-participants-references.md) · [← Poprzednia](07-wlasne-instrukcje.md) · [Strona kursu](../README.md) · [Dalej: Podstawy Git i GitHub →](09-podstawy-git-i-github.md)
