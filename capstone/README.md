# Capstone: Second Brain Agent · Projekt końcowy: Agent Drugiego Mózgu

[↩ All courses · Wszystkie kursy](../README.md)

The capstone that ties the whole repo together: **build a real AI agent** — a **Second Brain** that captures your notes, searches them, and answers questions grounded in your own knowledge. It runs on your **Claude Pro/Max subscription** (no paid API), on your Windows PC, using a custom **MCP server with tools** and your own **Skills**.

Projekt końcowy spinający całe repo: **zbuduj prawdziwego agenta AI** — **Drugi Mózg**, który przechwytuje notatki, przeszukuje je i odpowiada na pytania osadzone w Twojej wiedzy. Działa na Twoim **abonamencie Claude Pro/Max** (bez płatnego API), na Twoim PC z Windows, używając własnego **serwera MCP z narzędziami** i własnych **Skilli**.

> **Free on your subscription · Darmowe na abonamencie:** the agent runs on Claude Pro/Max — no API key, no per-token cost. · Agent działa na Claude Pro/Max — bez klucza API, bez kosztu za tokeny.

---

## Choose your language · Wybierz język

| Language · Język | |
|------------------|---|
| 🇬🇧 **English** | [Start the capstone →](en/README.md) |
| 🇵🇱 **Polski** | [Rozpocznij projekt →](pl/README.md) |

---

## What you'll build · Co zbudujesz

```
You ⇄ Claude Code (agent) ── loads ──▶ Skills (note-style, weekly-review)
            └── calls tools (MCP) ──▶ your Python server ──▶ notes/ (Markdown)
```

- **Agent** — Claude Code on your subscription (no API key).
- **Tools** — `save_note`, `search_notes`, `get_note`, `list_notes` (a FastMCP server you write).
- **Skills** — note-style (how to capture) + weekly-review (a workflow).
- **Data** — plain Markdown notes on disk: free, private, portable.

8 guided lessons: overview → set up → design → build the server → connect & test → author Skills → run the agent → test, harden & ship to GitHub.

8 prowadzonych lekcji: przegląd → konfiguracja → projekt → budowa serwera → podłączenie i test → napisanie Skilli → uruchomienie agenta → testy, utwardzenie i wydanie na GitHub.

---

## How it ties the courses together · Jak spina kursy

This capstone puts the whole repo into practice: **Prompt Engineering** (tool docstrings & Skill descriptions), **Advanced Claude** Tracks D–E (Skills, MCP, Claude Code on a subscription), and the **GitHub/Copilot** workflow (README, testing, shipping). Do those courses first if a step feels unfamiliar.

Ten projekt wprowadza całe repo w praktykę: **Inżynieria promptów** (docstringi narzędzi i opisy Skilli), **Claude zaawansowany** Ścieżki D–E (Skille, MCP, Claude Code na abonamencie) oraz przepływ **GitHub/Copilot** (README, testy, wydanie). Zrób najpierw te kursy, jeśli jakiś krok wydaje się nieznany.

---

*Educational material. Product names and CLI details change over time — the architecture (agent + MCP tools + Skills + local notes) still applies.*
*Materiał edukacyjny. Nazwy produktów i szczegóły CLI zmieniają się z czasem — architektura (agent + narzędzia MCP + Skille + lokalne notatki) nadal obowiązuje.*
