# Projekt końcowy 06 — Napisz swoje Skille

⏱️ **15 minut** · Poziom: Projekt końcowy · Wymagania: działający agent + narzędzia (Lekcja 5)

🌐 [English](../../en/lessons/06-author-your-skills.md) · [← Poprzednia](05-podlacz-i-przetestuj-narzedzia.md) · [Strona projektu](../README.md) · [Dalej: Uruchom agenta →](07-uruchom-agenta.md)

---

## 🧠 Teoria (4 min)

Narzędzia dają agentowi **zasięg**; **Skille** dają **wiedzę**. Skill to mały folder z plikiem `SKILL.md`: trochę **instrukcji** plus **nazwa** i **opis** w nagłówku. Agent czyta opis i **auto-ładuje Skill, gdy jest istotny** — nie wywołujesz go ręcznie.

Napiszemy dwa:

- **note-style** — Twoje reguły dobrej notatki (ładuje się, gdy agent tworzy/edytuje notatki).
- **weekly-review** — Twój przepływ przeglądu (ładuje się, gdy prosisz o przegląd).

W Claude Code Skille projektu mieszkają w folderze `.claude\skills\` w projekcie, więc płyną z repo.

> Dokładna lokalizacja Skilli i format pliku ewoluują, a Claude Desktop/aplikacje zarządzają Skillami przez własne ustawienia — sprawdź bieżącą dokumentację. Koncepcja jest stabilna: **nazwany, opisany zestaw instrukcji, który agent ładuje, gdy pasuje do zadania.**

---

## 🛠️ Praktyka (10 min)

### Krok 1 — Utwórz folder Skilli

W projekcie:

```powershell
mkdir .claude\skills\note-style
mkdir .claude\skills\weekly-review
```

### Krok 2 — Napisz Skill note-style

```powershell
notepad .claude\skills\note-style\SKILL.md
```

```markdown
---
name: note-style
description: Rules for writing and tagging notes in this Second Brain. Use
  whenever creating, editing, or saving a note with save_note.
---

# Note style

When saving a note, follow these rules:

- **One idea per note.** If the user dumps several topics, split them into
  separate notes with `save_note`.
- **Title** is a specific, searchable phrase — not "Notes" or "Stuff".
- **Tags**: choose 1–3 from this taxonomy: `work`, `idea`, `person`,
  `decision`, `learning`, `todo`. Add a new tag only if none fit.
- **Action line**: if there's a follow-up, end the note with `TODO: …`.
- Keep the user's own words; tidy lightly, don't rewrite their meaning.

After saving, confirm the title and tags you used.
```

### Krok 3 — Napisz Skill weekly-review

```powershell
notepad .claude\skills\weekly-review\SKILL.md
```

```markdown
---
name: weekly-review
description: A workflow to review the week's notes. Use when the user asks for
  a weekly review, a recap, or "what did I capture this week?".
---

# Weekly review

Run these steps in order:

1. Use `list_notes` (and `search_notes` if needed) to gather notes, focusing on
   recent ones.
2. Group them into 2–4 themes. Name each theme.
3. Collect every `TODO:` line into one "Open loops" list.
4. Propose the **3 most important priorities** for next week, each one line.
5. Offer to save the summary as a note titled "Weekly review — <date>"
   (tags: `review`) — but ask first.

Keep it concise and grounded ONLY in the actual notes. If something is unclear
or missing, say so rather than inventing it.
```

> Zawartość `SKILL.md` zostawiamy po angielsku — to instrukcje dla modelu i działają tak samo. Możesz je przetłumaczyć, jeśli wolisz.

### Krok 4 — Potwierdź, że Skille są widziane

Zrestartuj Claude Code w projekcie. Poproś o coś, co powinno wyzwolić note-style:

```text
Zapisz notatkę: „spotkałem się z Alexem o nowym flow onboardingu, przyślą
szkic w piątek, muszę go przejrzeć."
```

Dobry wynik: agent nadaje dobry tytuł, taguje (`work`, `person`, może `todo`) i dodaje linię `TODO:` — bo **Skill note-style się załadował**.

### Krok 5 — Zauważ, że opis wyzwala

**Opis** Skilla to, co sprawia, że agent ładuje go we właściwym momencie — dokładnie jak docstring narzędzia. Niejasny opis → nie wyzwoli. Precyzyjne „use when…" → odpala niezawodnie. (Inżynieria promptów, znów zastosowana.)

---

## 🧩 Narzędzia vs Skille (podsumowanie)

| | Narzędzia (Lekcja 4) | Skille (ta lekcja) |
|--|------------------|----------------------|
| Dają agentowi | Zasięg (robienie rzeczy) | Wiedzę (jak robić je dobrze) |
| Definiowane przez | `@mcp.tool()` + docstring | `SKILL.md` + opis |
| Wyzwalane przez | Agent wybierający działanie | Opis pasujący do zadania |
| Przykład | `save_note(...)` | reguły formatu „note-style" |

---

## ✅ Sprawdzian

- [ ] `.claude\skills\note-style\SKILL.md` i `weekly-review\SKILL.md` istnieją.
- [ ] Każdy ma **nazwę** i precyzyjny **opis** („use when…").
- [ ] Zapisywanie notatki teraz podąża za regułami note-style automatycznie.
- [ ] Umiesz wyjaśnić, jak **opis** Skilla wyzwala auto-ładowanie.

---

## 🎯 Praca domowa

Dopracuj Skill note-style po użyciu go na 3–4 prawdziwych notatkach: czy tytuły są wyszukiwalne? Czy tagi spójne? Dociśnij reguły (i opis), aż notatki agenta wychodzą tak, jak *Ty* chcesz, domyślnie.

---

## 💡 Najważniejsze wnioski

- **Skille** pakują wiedzę w `SKILL.md`; agent **auto-ładuje** je, gdy **opis** pasuje do zadania.
- Napisałeś/aś **note-style** (jak przechwytywać) i **weekly-review** (przepływ) — oba płyną w `.claude\skills\`.
- **Opis** Skilla to jego wyzwalacz — pisz go tak precyzyjnie jak docstring narzędzia.

🌐 [English](../../en/lessons/06-author-your-skills.md) · [← Poprzednia](05-podlacz-i-przetestuj-narzedzia.md) · [Strona projektu](../README.md) · [Dalej: Uruchom agenta →](07-uruchom-agenta.md)
