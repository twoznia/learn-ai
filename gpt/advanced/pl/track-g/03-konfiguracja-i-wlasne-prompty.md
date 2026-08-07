# G3 — Konfiguracja i własne prompty

⏱️ **15 minut** · Ścieżka: 🅶 Codex CLI w głąb · Wymagania: Codex CLI zainstalowany i zalogowany

🌐 [English](../../en/track-g/03-config-and-custom-prompts.md) · [← Poprzedni](02-tryby-zatwierdzania-i-sandbox.md) · [Spis ścieżki](../README.md) · [Dalej: Bezpieczna edycja z git →](04-bezpieczna-edycja-z-git.md)

---

## 🧠 Teoria (4 min)

Dwie funkcje zmieniają Codeksa z „dobrego" w „Twojego":

- **Konfiguracja** — plik ustawień (`~/.codex/config.toml`), który ustawia Twoje domyślne: który model, domyślny poziom zatwierdzania/piaskownicy, serwery MCP i więcej. Ustaw raz, a każda sesja startuje tak, jak lubisz.
- **Własne prompty** — wielokrotnego użytku instrukcje zapisywane jako pliki w `~/.codex/prompts/` i wywoływane po nazwie. Twoje osobiste „przepisy" na zadania, które robisz raz za razem.

Oba mieszkają w Twoim domowym folderze `~/.codex/`, obok globalnego `AGENTS.md` z G1.

> Dokładne klucze configu i funkcje promptów ewoluują. Gdy coś się nie zgadza, sprawdź bieżącą dokumentację Codeksa — *idee* tutaj pozostają te same.

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Otwórz swój config

```powershell
notepad $HOME\.codex\config.toml
```

Prosty config ustawia Twoje domyślne. Na przykład:

```toml
# Domyślny model i zachowanie zatwierdzania
model = "gpt-5-codex"
approval_policy = "on-request"

# Serwer MCP (zob. Ścieżka E)
[mcp_servers.my-tools]
command = "python"
args = ["C:/sciezka/do/server.py"]
```

Zapisz, zrestartuj Codeksa, a Twoje domyślne obowiązują — bez flag do zapamiętania.

> Nie znasz dokładnych nazw kluczy? Zapytaj Codeksa: „Pokaż mi minimalny `config.toml`, który ustawia mój domyślny model i tryb zatwierdzania", potem zweryfikuj z dokumentacją.

### Krok 2 — Utwórz własny prompt

Zrób folder promptów i dodaj jeden:

```powershell
mkdir $HOME\.codex\prompts -Force
notepad $HOME\.codex\prompts\review.md
```

Umieść w środku wielokrotnego użytku instrukcję:

```markdown
Przejrzyj bieżące zmiany pod kątem błędów, niejasnych nazw i braku obsługi
błędów. Wypisz znaleziska jako krótką listę kontrolną, najważniejsze pierwsze.
Nie zmieniaj żadnego kodu — tylko raportuj.
```

### Krok 3 — Uruchom go po nazwie

W sesji wywołaj zapisany prompt (własne prompty pojawiają się jako komendy):

```text
/review
```

Codex uruchamia Twój zapisany przepis. Jedno słowo zastępuje akapit, który inaczej przepisywałbyś/aś.

### Krok 4 — Zbuduj małą bibliotekę

Dodaj kilka, których użyjesz ponownie:

- `explain.md` — „Wyjaśnij prostym językiem, co robi ten plik".
- `tests.md` — „Zaproponuj testy jednostkowe dla bieżących zmian; nie pisz jeszcze kodu".
- `commit.md` — „Napisz jasny, konwencjonalny komunikat commita dla zmian w staging".

### Krok 5 — Config vs prompty — co jest czym?

- **Config** zmienia *jak Codex się zachowuje* (model, zatwierdzenia, serwery).
- **Prompty** to *zadania, które powtarzasz* (review, wyjaśnij, testuj).

Trzymaj je osobno, a oba pozostaną proste.

---

## 🧩 Twój folder `~/.codex/`

| Plik | Cel |
|------|---------|
| `config.toml` | Domyślne: model, zatwierdzenia, serwery MCP |
| `AGENTS.md` | Twój globalny kontekst/preferencje (G1) |
| `prompts/*.md` | Wielokrotnego użytku, nazwane przepisy zadań |

---

## ✅ Sprawdzian

- [ ] Ustawiłeś/aś co najmniej jedno domyślne w `config.toml` (np. model lub tryb zatwierdzania).
- [ ] Utworzyłeś/aś własny prompt w `~/.codex/prompts/`.
- [ ] Uruchomiłeś/aś go po nazwie w sesji.
- [ ] Umiesz wyjaśnić różnicę między configiem a promptami.

---

## 🎯 Praca domowa

Ustaw dwa najbardziej pożądane domyślne w `config.toml`, potem utwórz trzy własne prompty na zadania, które powtarzasz (review, wyjaśnij, testy). Użyj jednego w prawdziwej sesji i dopracuj jego brzmienie.

---

## 💡 Najważniejsze wnioski

- **`config.toml`** ustawia Twoje domyślne — model, zatwierdzenia, serwery MCP — by każda sesja startowała po Twojemu.
- **Własne prompty** w `~/.codex/prompts/` to wielokrotnego użytku, nazwane przepisy wywoływane jednym słowem.
- Config kontroluje **zachowanie**; prompty to wielokrotnego użytku **zadania** — trzymaj je osobno i prosto.

🌐 [English](../../en/track-g/03-config-and-custom-prompts.md) · [← Poprzedni](02-tryby-zatwierdzania-i-sandbox.md) · [Spis ścieżki](../README.md) · [Dalej: Bezpieczna edycja z git →](04-bezpieczna-edycja-z-git.md)
