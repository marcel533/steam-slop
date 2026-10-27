# Steam Slop

**How much of a Steam game is AI-generated?** Enter a title, get a slop score.

[English](#english) | [Deutsch](#deutsch)

> **Running the app:** see [USE.md](USE.md).

---

<a id="english"></a>

## English

A web app that estimates how heavily a Steam game relies on AI-generated assets — a "slop score" from 0–100%, a category breakdown, the evidence behind the number, and a link to the store page.

### Contents

- [Features](#features)
- [How the score works](#how-the-score-works)
- [Scoring weights](#scoring-weights)
- [Estimation signals](#estimation-signals)
- [Limitations](#limitations)
- [Tech stack](#tech-stack)
- [Getting started](#getting-started)
- [Credits](#credits)

### Features

| Feature | Description |
| --- | --- |
| **Live search** | Query every game on Steam, with cover art, developer and release date. Fully keyboard-navigable autocomplete. |
| **Slop score** | 0–100%, classified as *AI Slop*, *Mixed*, or *Legitimate*. |
| **Breakdown** | Per-category detail for store/capsule graphics, text & patch notes, and asset flips. |
| **Evidence list** | The specific signals that produced the score. |
| **Community consensus** | Votes, example quotes and tags — curated entries only. |
| **Steam link** | Jump straight to the store page from any game view. |
| **Bilingual UI** | EN \| DE toggle, dark-mode design. |

### How the score works

Entries come from two sources:

1. **Curated entries** (homepage) — scored from publicly known information, such as AI usage disclosed by the developer.
2. **Every other Steam game** — automatically estimated from public store data (see below).

The overall score is a weighted average of the measurable categories.

### Scoring weights

| Category | Weight | Notes |
| --- | --- | --- |
| Store & capsule graphics | 40% | Images are **not** analysed, so this reads `n/a` unless the developer explicitly disclosed AI use. |
| Store text & patch notes | 30% | Looks for LLM-typical phrasing. |
| Asset flips | 30% | Indicators of reused or repackaged assets. |

### Estimation signals

For non-curated games, the estimate draws on:

- LLM-typical phrasing in the store description
- No developer website or support contact
- Very few user reviews
- An unusually low price
- Steam's own "AI Generated Content Disclosure", where present *(best-effort, no guarantee)*

### Limitations

> ⚠️ **The score is an indicator, not proof.** It can be wrong in either direction.

- Do not use it to accuse a studio or developer.
- Community-contributed data exists only for curated entries; real community reporting would require a dedicated database.

### Tech stack

| Layer | Choice |
| --- | --- |
| Framework | Next.js 15 (App Router) |
| UI | React 19, Tailwind CSS 3 |
| Icons | Lucide React |
| Animation | GSAP + `@gsap/react` (hero reveal and score counter; disabled under reduced-motion settings) |
| Data | Steam requests proxied through server routes (browser CORS restriction). **No API key required.** |

### Getting started

Setup and run instructions live in [USE.md](USE.md). The commands are the usual Next.js ones (`npm install`, then the `dev` / `build` script from `package.json`) — adjust to match the scripts actually defined in this repo.

### Download

The complete archive is roughly **250 MB**. GitHub rejects individual files
above 100 MB, so it can't live in this repository. Get it here instead:

**→ [Download the archive (pCloud)](https://e.pcloud.link/publink/show?code=XZY41X7ZKtTbdQEL7dbphM60hAJoVkneB2c7)**

Unzip it into the project root before running the app — see [USE.md](USE.md).

### Credits

Created by **marcel533**. Game data and images belong to Valve, Steam, and the respective developers.

**AI note:** this project was generated entirely using AI.

---

<a id="deutsch"></a>

## Deutsch

Eine Web-App, die einschätzt, wie stark ein Steam-Spiel auf KI-generierte Assets setzt. Gib einen Titel ein und du erhältst einen Slop-Wert mit Aufschlüsselung, den zugrunde liegenden Belegen und einem Link zur Steam-Seite.

### Inhalt

- [Funktionen](#funktionen)
- [So entsteht der Wert](#so-entsteht-der-wert)
- [Gewichtung](#gewichtung)
- [Signale der Schätzung](#signale-der-schätzung)
- [Grenzen](#grenzen)
- [Technik](#technik)
- [Erste Schritte](#erste-schritte)
- [Credits](#credits-1)

### Funktionen

| Funktion | Beschreibung |
| --- | --- |
| **Live-Suche** | Durchsucht alle Steam-Spiele inklusive Cover, Entwickler und Erscheinungsdatum – mit per Tastatur bedienbarer Autovervollständigung. |
| **Slop-Wert** | 0 bis 100 % mit Urteil: *KI-Slop*, *Gemischt* oder *Legitim*. |
| **Aufschlüsselung** | Getrennt nach Store-Grafiken und Kapselbildern, Beschreibungen und Patchnotes sowie Asset-Flip-Hinweisen. |
| **Belege** | Die konkreten Hinweise, die zum Wert geführt haben. |
| **Community-Urteil** | Stimmen, Beispielzitat und Tags – nur bei kuratierten Einträgen. |
| **Steam-Link** | Direkt zur Store-Seite aus jeder Spielansicht. |
| **Zweisprachig** | EN \| DE Umschalter, dunkles Design. |

### So entsteht der Wert

Es gibt zwei Arten von Einträgen:

1. **Kuratierte Einträge** (Startseite) – Werte auf Basis öffentlich bekannter Angaben, etwa von Entwicklern offengelegter KI-Nutzung.
2. **Alle anderen Steam-Spiele** – automatische Schätzung aus öffentlichen Store-Daten (siehe unten).

Der Gesamtwert ist ein gewichteter Durchschnitt der messbaren Kategorien.

### Gewichtung

| Kategorie | Gewicht | Hinweis |
| --- | --- | --- |
| Store-Grafiken & Kapselbilder | 40 % | Bilder werden **nicht** analysiert, daher steht hier `n/a`, außer der Entwickler hat KI-Nutzung ausdrücklich angegeben. |
| Beschreibung & Patchnotes | 30 % | Sucht nach typischen LLM-Floskeln. |
| Asset-Flip | 30 % | Hinweise auf wiederverwendete oder neu verpackte Assets. |

### Signale der Schätzung

Bei nicht kuratierten Spielen fließen ein:

- typische LLM-Floskeln in der Store-Beschreibung
- keine Entwickler-Website oder kein Support-Kontakt
- sehr wenige Nutzerreviews
- ein sehr niedriger Preis
- Steams „AI Generated Content Disclosure“, sofern vorhanden *(ohne Garantie)*

### Grenzen

> ⚠️ **Der Wert ist ein Indikator, kein Beweis.** Er kann in beide Richtungen falsch liegen.

- Nicht verwenden, um ein Studio oder einen Entwickler zu beschuldigen.
- Community-Daten gibt es nur für kuratierte Einträge; echte Community-Meldungen bräuchten eine Datenbank.

### Technik

| Ebene | Wahl |
| --- | --- |
| Framework | Next.js 15 (App Router) |
| UI | React 19, Tailwind CSS 3 |
| Icons | Lucide React |
| Animation | GSAP mit `@gsap/react` (Hero-Einblendung und Hochzählen des Werts; bei reduzierter Bewegung abgeschaltet) |
| Daten | Steam-Anfragen laufen über Server-Routen, weil Browser Steam nicht direkt abfragen dürfen (CORS). **Kein API-Key nötig.** |

### Erste Schritte

Anleitung zum Starten steht in [USE.md](USE.md). Verwendet werden die üblichen Next.js-Befehle (`npm install`, danach das `dev`-/`build`-Skript aus der `package.json`) – bitte an die tatsächlichen Skripte im Repo anpassen.

### Herunterladen

Das vollständige Archiv ist rund **250 MB** groß. GitHub lehnt einzelne Dateien
über 100 MB ab, deshalb liegt es nicht im Repository. Stattdessen hier:

**→ [Archiv herunterladen (pCloud)](https://e.pcloud.link/publink/show?code=XZY41X7ZKtTbdQEL7dbphM60hAJoVkneB2c7)**

Vor dem Start ins Projektverzeichnis entpacken – siehe [USE.md](USE.md).

### Credits

Erstellt von **marcel533**. Spieldaten und Bilder gehören Valve, Steam und den jeweiligen Entwicklern.

**KI-Hinweis:** Dieses Projekt ist vollständig mit KI generiert.
