# Steam Slop

[English](#english) | [Deutsch](#deutsch)

How to run it: see [USE.md](USE.md).

---

<a id="english"></a>

# English

A satirical but practical web app that helps you judge whether a Steam game leans on AI-generated assets ("AI slop"). Search any game on Steam, get a slop score with a breakdown, the evidence behind it, and a link to the Steam page.

## Features

- **Live search** across all Steam games: cover, developer and release date, with keyboard-accessible autocomplete.
- **Slop score** from 0 to 100% with a verdict: AI slop, Mixed or Legitimate.
- **Breakdown** into store art and capsule images, descriptions and patch notes, and asset-flip signals.
- **Evidence list** of the flags that led to the score.
- **Community verdict** with votes, a sample quote and tags (curated entries only).
- **Steam link** on every game page.
- **EN | DE** language switch, dark theme, responsive layout, reduced-motion support.

## How the score works

There are two kinds of entries:

1. **Curated entries** (home page): scores based on publicly known statements, such as AI use disclosed by the developer.
2. **Any other Steam game**: an automatic estimate from public store data:
   - stock LLM phrases in the store description
   - no developer website or support contact
   - very few user reviews
   - a very low price
   - Steam's "AI Generated Content Disclosure" on the store page (best effort)

The overall score is a weighted average of the categories that could be measured (art 40%, text 30%, asset flip 30%). Images are **not** analyzed, so store art shows "n/a" unless the developer disclosed AI use.

## Limitations

The score is an indicator, not proof of how a game was made. It can be wrong in both directions. Do not use it to accuse a studio or developer. Community data exists only for curated entries; real community reports would need a database.

## Tech stack

- Next.js 15 (App Router), React 19
- Tailwind CSS 3
- Lucide React (icons)
- GSAP with `@gsap/react` (hero entrance and score count-up, disabled for reduced motion)

Steam requests run in server routes, because browsers cannot call Steam directly (CORS). No API key is needed.

## AI disclosure

This project is fully generated with AI, because it is so difficult to build this by hand.

## Credits

Created by marcel533. Game data and images belong to Valve, Steam and the respective developers.

---

<a id="deutsch"></a>

# Deutsch

Eine satirische, aber praktische Web-App, die einschätzen hilft, ob ein Steam-Spiel stark auf KI-generierte Assets ("KI-Slop") setzt. Suche ein beliebiges Steam-Spiel und erhalte einen Slop-Wert mit Aufschlüsselung, den dahinterliegenden Belegen und einem Link zur Steam-Seite.

## Funktionen

- **Live-Suche** über alle Steam-Spiele: Cover, Entwickler und Erscheinungsdatum, mit per Tastatur bedienbarer Autovervollständigung.
- **Slop-Wert** von 0 bis 100 % mit Urteil: KI-Slop, Gemischt oder Legitim.
- **Aufschlüsselung** in Store-Grafiken und Kapselbilder, Beschreibungen und Patchnotes sowie Asset-Flip-Hinweise.
- **Belege-Liste** mit den Hinweisen, die zum Wert geführt haben.
- **Community-Urteil** mit Stimmen, Beispielzitat und Tags (nur bei kuratierten Einträgen).
- **Steam-Link** auf jeder Spielseite.
- **EN | DE** Sprachwechsel, dunkles Design, responsives Layout, Unterstützung für reduzierte Bewegung.

## So entsteht der Wert

Es gibt zwei Arten von Einträgen:

1. **Kuratierte Einträge** (Startseite): Werte auf Basis öffentlich bekannter Angaben, etwa von Entwicklern offengelegte KI-Nutzung.
2. **Jedes andere Steam-Spiel**: eine automatische Schätzung aus öffentlichen Store-Daten:
   - typische LLM-Floskeln in der Store-Beschreibung
   - keine Entwickler-Website oder kein Support-Kontakt
   - sehr wenige Nutzerreviews
   - ein sehr niedriger Preis
   - Steams "AI Generated Content Disclosure" auf der Store-Seite (Versuch, ohne Garantie)

Der Gesamtwert ist ein gewichteter Durchschnitt der messbaren Kategorien (Grafik 40 %, Text 30 %, Asset-Flip 30 %). Bilder werden **nicht** analysiert, daher zeigt die Store-Grafik "n/a", außer der Entwickler hat KI-Nutzung angegeben.

## Grenzen

Der Wert ist ein Indikator, kein Beweis dafür, wie ein Spiel entstanden ist. Er kann in beide Richtungen falsch liegen. Nicht verwenden, um ein Studio oder einen Entwickler zu beschuldigen. Community-Daten gibt es nur für kuratierte Einträge; echte Community-Meldungen bräuchten eine Datenbank.

## Technik

- Next.js 15 (App Router), React 19
- Tailwind CSS 3
- Lucide React (Icons)
- GSAP mit `@gsap/react` (Hero-Einblendung und Hochzählen des Werts, bei reduzierter Bewegung abgeschaltet)

Steam-Anfragen laufen in Server-Routen, weil Browser Steam nicht direkt abfragen dürfen (CORS). Ein API-Key ist nicht nötig.

## KI-Hinweis

Dieses Projekt ist vollständig mit KI generiert, weil es so schwierig ist, so etwas von Hand zu bauen.

## Credits

Erstellt von marcel533. Spieldaten und Bilder gehören Valve, Steam und den jeweiligen Entwicklern.
