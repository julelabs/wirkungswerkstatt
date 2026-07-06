# Wirkungswerkstatt

Statische Website der Wirkungswerkstatt (Schwesterprodukt der OKR-Werkstatt): Wirkungsversprechen, Steuerungs-Check, Führungspfad, TOP-Triage. Zielgruppe: Führungskräfte und Steuerungsrunden in der Verwaltung.

## Rahmenbedingungen

- Reines HTML/CSS/Vanilla-JS. Kein Build-Schritt, keine Frameworks, keine externen Libraries, kein Tracking. Bewusste Entscheidung (Datenschutz, Wartbarkeit): nichts davon einführen.
- Jede Seite ist eine in sich geschlossene HTML-Datei. Gemeinsam sind `shared/style.css` und `assets/`.
- Interaktive Werkzeuge speichern ausschließlich in `localStorage`. Bestehende Storage-Keys und State-Formate nie brechen; bei Formatänderungen Migration schreiben.
- Hosting-Ziel: GitHub Pages (siehe README). Vor Veröffentlichung offene Punkte im README klären (Domain, Kontaktadresse, Datenschutztext). **Nie ungefragt committen oder pushen.**

## Lokal testen

```bash
python3 -m http.server 8080   # aus diesem Ordner
# http://localhost:8080
```

Vor "fertig": Seite im Browser prüfen (Desktop und 375px mobil), Druck-/Kopierfunktionen der Werkzeuge testen. Konsole muss fehlerfrei sein.

## Design-System

Referenz: `shared/style.css` (Kommentar-Header dort erklärt das Seitengerüst). Design-Familie der OKR-Werkstatt mit zwei bewussten Unterschieden: **dunkle Navigation** (`nav.top` auf `--dunkel`) und **kein Chevron-Motiv `›››`**.

- **Palette**: `--blau #36349D`, `--minze #4DFFB0` (Akzent/CTA), `--kirsche #DB0045` (sparsam), `--lavendel #E3E6F2`, `--dunkel #0D0C2B`. Keine Farben außerhalb der Tokens.
- **Typo**: Open Sans (`--display`) für Headlines/UI-Labels, BundesSans (`--body`) für Fließtext.
- **Seitengerüst**: `nav.top` (Brand links, Links rechts) → `main.page` mit `section`-Blöcken (`.wrap` / `.wrap-narrow`) → `footer.site`.
- **Grundhaltung** wie in der OKR-Werkstatt: ruhige Flächen statt Card-Stapel, Hairlines statt Boxen, Eingaben sehen aus wie Text bis zum Fokus, Details einklappen statt alles zeigen, Aktionen leise.

## Sprache und Ton

- Deutsch mit echten Umlauten, auch in JS-Strings und Seed-Daten (für, Übung; niemals fuer/Uebung). Achtung: README und ältere Dateien enthalten noch ue/ae-Schreibweisen, neue Texte trotzdem korrekt schreiben.
- Ton: klar, direkt, verwaltungsnah, kein Beratersprech. Fachbegriffe des Produkts konsistent verwenden (u. a. Begriffsleiter, Beobachtbarkeitstreppe; Konzeptnotizen liegen im übergeordneten Ordner `../`).

## Arbeitsteilung

Modellwahl und Subagent-Muster stehen in der globalen `~/.claude/CLAUDE.md`. Projektspezifisch gilt: Alles Sichtbare auf dieser Site ist Taste-Arbeit (Design-System oben), von Codex/gpt-5.5 gebautes UI vor Übernahme dagegen reviewen. Subagent-Ergebnisse immer im Browser verifizieren.

## Kontext drumherum

Der übergeordnete Ordner (`../`) enthält Produktkonzept, Onepager und Werkzeug-Notizen; dort liegt der inhaltliche Stand des Produkts. Die Website ist ein privates, unabhängiges Projekt (kein Behördenangebot), Impressum/Datenschutz nicht antasten ohne Rückfrage.
