# OE5XRX Dashboard

Dieses Repository enthält das Projekt-Dashboard der [OE5XRX](https://github.com/OE5XRX) Organisation.

Die Seite wird mit [Jekyll](https://jekyllrb.com/) und dem [Just the Docs](https://just-the-docs.com/) Theme gebaut und automatisch über GitHub Pages deployed.

**Live:** wird nach Aktivierung von GitHub Pages unter der Repository-URL erreichbar sein.

## Lokaler Build

### Voraussetzungen

- Ruby (>= 3.0)
- Bundler (`gem install bundler`)

### Installation und Start

```bash
bundle install --path .bundle
bundle exec jekyll serve
```

Danach im Browser öffnen: [http://127.0.0.1:4000](http://127.0.0.1:4000)

Die Seite wird automatisch neu generiert, wenn Dateien geändert werden.

## Projekte pflegen

Die zentrale Datenquelle ist die Datei **`_data/projects.yml`**.

### Neues Projekt eintragen

Füge einen neuen Eintrag am Ende der Datei hinzu:

```yaml
- name: Mein-Neues-Projekt
  short_description: Kurze Beschreibung des Projekts
  state: active          # active | paused | ideas
  status: Aktueller Stand des Projekts
  next_step: Was als Nächstes geplant ist
  last_updated: 2026-03-15
  repo_url: https://github.com/OE5XRX/Mein-Neues-Projekt
  docs_url: https://example.com/docs   # optional
  tags:
    - tag1
    - tag2
```

### Unterprojekte eintragen

Unterprojekte werden als Liste innerhalb eines Projekts definiert:

```yaml
- name: Hauptprojekt
  short_description: ...
  state: active
  status: ...
  next_step: ...
  last_updated: 2026-03-15
  repo_url: https://github.com/OE5XRX/Hauptprojekt
  tags:
    - beispiel
  subprojects:
    - name: Unterprojekt A
      short_description: Beschreibung von Unterprojekt A
      repo_url: https://github.com/OE5XRX/Unterprojekt-A
      status: In Arbeit
    - name: Unterprojekt B
      short_description: Beschreibung von Unterprojekt B
      status: Geplant
```

### Verfügbare States

| State    | Bedeutung                        |
|----------|----------------------------------|
| `active` | Projekt wird aktiv bearbeitet    |
| `paused` | Projekt ist pausiert             |
| `ideas`  | Projektidee, noch nicht gestartet|

## Struktur

```
├── _config.yml                  # Jekyll-Konfiguration
├── _data/
│   └── projects.yml             # ← Projektdaten (hier pflegen!)
├── assets/
│   └── Icon.png                 # Logo
├── favicon.ico                  # Favicon
├── index.md                     # Startseite mit Dashboard-Template
├── Gemfile                      # Ruby-Abhängigkeiten
├── .github/
│   └── workflows/
│       └── jekyll.yml           # GitHub Actions Deployment
└── README.md                    # Diese Datei
```

## Lizenz

Siehe die jeweiligen Projekt-Repositories für Lizenzinformationen.