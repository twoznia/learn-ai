# G2 — Tryby zatwierdzania i sandbox

⏱️ **15 minut** · Ścieżka: 🅶 Codex CLI w głąb · Wymagania: Codex CLI zainstalowany i zalogowany

🌐 [English](../../en/track-g/02-approval-modes-and-sandbox.md) · [← Poprzedni](01-agents-md-i-kontekst.md) · [Spis ścieżki](../README.md) · [Dalej: Konfiguracja i własne prompty →](03-konfiguracja-i-wlasne-prompty.md)

---

## 🧠 Teoria (5 min)

To najważniejsza lekcja o bezpieczeństwie w tej ścieżce. Codex kontroluje, co agent może zrobić Twojej maszynie, za pomocą **dwóch pokręteł**:

- **Tryb zatwierdzania** — *kiedy Codex pyta Cię przed działaniem.* Od „pytaj przed wszystkim" po „nie pytaj wcale".
- **Sandbox (piaskownica)** — *czego Codex w ogóle może dotknąć,* niezależnie od zatwierdzeń. Od tylko-do-odczytu, przez zapis w folderze roboczym, po pełny dostęp.

Z grubsza, poziomy, które zobaczysz:

| Poziom | Co oznacza |
|-------|---------------|
| **Read Only** | Codex może czytać i planować, ale nie edytować plików ani uruchamiać poleceń, które coś zmieniają |
| **Auto / Workspace-write** | Codex może edytować pliki **w folderze roboczym** i uruchamiać polecenia, pytając, gdy coś sięga poza lub wygląda ryzykownie |
| **Full Access** | Codex działa bez pytania i bez piaskownicy — potężny i niebezpieczny |

Bezpieczny domyślny wybór podczas nauki to środek: pracuj **wewnątrz folderu projektu**, pozwól edytować tam i **zatwierdzaj** cokolwiek, co sięga poza. Zachowaj „Full Access" na jednorazowe piaskownice, na których Ci nie zależy.

---

## 🛠️ Praktyka (9 min)

### Krok 1 — Zobacz bieżący tryb

Uruchom Codeksa w projekcie. Pokazuje aktywny tryb zatwierdzania/piaskownicy przy starcie. Możesz go zmienić poleceniem `/approvals` (lub restartując z flagą trybu).

```text
/approvals
```

Wybierz tryb i przeczytaj, co każdy pozwala.

### Krok 2 — Wypróbuj Read Only

Przełącz na **Read Only** i poproś o zmianę:

```text
Dodaj sekcję „## Notatki" do README.
```

Codex *zaproponuje* to, ale nie może zapisać — dowód, że Read Only naprawdę jest tylko-do-odczytu. Świetne do eksploracji nieznanego lub wrażliwego projektu.

### Krok 3 — Przełącz na tryb roboczy

Przejdź na środkowy tryb **Auto / workspace-write**. Poproś ponownie:

```text
Dodaj sekcję „## Notatki" do README z dwoma przykładowymi punktami.
```

Teraz może edytować **wewnątrz folderu** — i wciąż pyta przed czymkolwiek poza nim lub ryzykownym (jak polecenie sieciowe). Zatwierdź i sprawdź plik.

### Krok 4 — Obserwuj, jak pyta na granicy

Poproś o coś, co sięga poza folder lub do sieci:

```text
Zainstaluj nowy pakiet dla tego projektu.
```

Zauważ, że Codex **wstrzymuje się dla zatwierdzenia**, bo to wykracza poza piaskownicę workspace. Przeczytaj proponowane polecenie, zanim powiesz tak.

### Krok 5 — Zrozum „Full Access" (i unikaj go na początku)

Full Access usuwa piaskownicę i pytanie. Bywa użyteczny w **jednorazowym** środowisku, ale może usunąć pliki lub uruchomić cokolwiek. **Nie używaj go na prawdziwym projekcie ani głównej maszynie podczas nauki.**

### Krok 6 — Wybierz domyślny i styl pracy

- **Eksplorujesz / wrażliwy kod?** Read Only.
- **Normalna praca?** Auto / workspace-write, w dedykowanym folderze.
- **Tylko jednorazowa piaskownica?** Full Access — celowo, nigdy z nawyku.

---

## 🧩 Dwa pokrętła

| Pokrętło | Kontroluje | Bezpieczny start |
|------|----------|---------------------|
| **Tryb zatwierdzania** | Kiedy Codex pyta przed działaniem | Pytaj przed edycjami/poleceniami |
| **Sandbox** | Czego Codex może w ogóle dotknąć | Workspace-write (ten folder) |
| Razem | Twoja koperta bezpieczeństwa | Środkowy tryb, w folderze projektu |

> ⚠️ **Piaskownica to Twój pas bezpieczeństwa.** Trzymaj Codeksa ograniczonego do folderu projektu, zatwierdzaj cokolwiek, co sięga poza, i rezerwuj Full Access na środowiska, które gotów/gotowa jesteś stracić.

---

## ✅ Sprawdzian

- [ ] Podejrzałeś/aś i zmieniłeś/aś tryb zatwierdzania/piaskownicy poleceniem `/approvals`.
- [ ] Potwierdziłeś/aś, że Read Only nie może edytować plików.
- [ ] W środkowym trybie widziałeś/aś, jak edytuje w folderze, ale pyta na granicy.
- [ ] Umiesz wyjaśnić tryb zatwierdzania vs sandbox i czemu Full Access to ostateczność.

---

## 🎯 Praca domowa

W projekcie-brudnopisie wypróbuj każdy tryb na tym samym małym zadaniu: Read Only (proponuje, nie może działać), Auto (edytuje i pyta na granicy). Zapisz, którego trybu użyjesz do prawdziwej pracy — i obiecaj sobie, że Full Access jest tylko dla jednorazowych folderów.

---

## 💡 Najważniejsze wnioski

- Bezpieczeństwo Codeksa to **dwa pokrętła**: **tryb zatwierdzania** (kiedy pyta) i **sandbox** (czego może dotknąć).
- Bezpieczny domyślny wybór to **środek**: edytuj w dedykowanym folderze, zatwierdzaj cokolwiek sięgającego poza.
- **Full Access** usuwa oba zabezpieczenia — używaj go tylko w jednorazowych środowiskach, nigdy na prawdziwej maszynie podczas nauki.

🌐 [English](../../en/track-g/02-approval-modes-and-sandbox.md) · [← Poprzedni](01-agents-md-i-kontekst.md) · [Spis ścieżki](../README.md) · [Dalej: Konfiguracja i własne prompty →](03-konfiguracja-i-wlasne-prompty.md)
