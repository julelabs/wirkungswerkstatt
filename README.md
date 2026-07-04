# Wirkungswerkstatt Website

Statische Website fuer die Wirkungswerkstatt. Es gibt keinen Build-Schritt, kein Backend und keine externen Tracking- oder Analyse-Skripte.

## Lokal ansehen

Aus diesem Ordner starten:

```sh
python3 -m http.server 8080
```

Dann im Browser oeffnen:

```text
http://localhost:8080
```

## Struktur

- `index.html` - Startseite und Einstiegspfade
- `wirkungsversprechen.html` - interaktives Werkzeug mit lokaler Speicherung im Browser
- `steuerungs-check.html` - interaktives Werkzeug mit lokaler Speicherung im Browser
- `fuehrungspfad.html` - Fuehrungspfad mit Druck-/Kopierfunktionen
- `impressum.html` und `datenschutz.html` - Rechtliches, vor Veroeffentlichung pruefen
- `shared/style.css` - gemeinsames Stylesheet fuer die statischen Inhaltsseiten
- `assets/fonts/` - lokal eingebundene Schriften

## Hosting-Empfehlung

Der aktuelle Datenschutztext ist auf GitHub Pages plus vorgeschaltetes Cloudflare formuliert. Daher ist der sauberste Weg:

1. Neues GitHub-Repository anlegen, zum Beispiel `wirkungswerkstatt`.
2. Den Inhalt dieses `site`-Ordners als Repository-Inhalt verwenden.
3. In GitHub unter `Settings -> Pages` als Source `GitHub Actions` einstellen.
4. Auf `main` pushen. Der Workflow `.github/workflows/pages.yml` veroeffentlicht die Site automatisch.
5. Wenn eine eigene Domain genutzt wird, diese in GitHub Pages eintragen und DNS ueber Cloudflare verbinden.
6. Nach der ersten Veroeffentlichung `datenschutz.html` und `impressum.html` mit der echten Domain und Kontaktadresse gegenlesen.

Ohne GitHub Actions geht es auch: Unter `Settings -> Pages` als Source `Deploy from a branch`, Branch `main`, Folder `/root` waehlen.

## Pflege-Workflow

1. Inhalt lokal in den HTML-Dateien bearbeiten.
2. Lokal mit `python3 -m http.server 8080` testen.
3. Jede Seite kurz anklicken: Startseite, Wirkungsversprechen, Steuerungs-Check, Fuehrungspfad, Impressum, Datenschutz.
4. Aenderungen committen und pushen. GitHub Pages veroeffentlicht danach automatisch.

## Vor Veroeffentlichung klaeren

- Soll die Kontaktadresse `kontakt@okr-werkstatt.org` bleiben oder bekommt die Wirkungswerkstatt eine eigene Adresse?
- Welche Domain soll genutzt werden?
- Soll der Footer weiterhin auf `okr-werkstatt.org` verweisen?
- Datenschutztext passt nur, wenn tatsaechlich GitHub Pages und Cloudflare genutzt werden.
