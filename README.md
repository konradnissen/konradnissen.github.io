# Deine Wissenschaftsseite

Eine persönliche Website mit Startseite, Publikationsliste, Lebenslauf und
Blog, gebaut mit [Jekyll](https://jekyllrb.com/) – der Software, die GitHub
Pages nativ unterstützt. Du brauchst **keine Programmierkenntnisse**, um
Inhalte zu pflegen: fast alles ist einfacher Text bzw. Markdown.

## Inhaltsverzeichnis
- [1. Struktur der Seite](#1-struktur-der-seite)
- [2. Schnellstart: Auf GitHub veröffentlichen](#2-schnellstart-auf-github-veröffentlichen)
- [3. Eigene Angaben eintragen](#3-eigene-angaben-eintragen)
- [4. Blogbeiträge schreiben](#4-blogbeiträge-schreiben)
- [5. Publikationen & Lebenslauf pflegen](#5-publikationen--lebenslauf-pflegen)
- [6. Porträtfoto & Lebenslauf-PDF hinzufügen](#6-porträtfoto--lebenslauf-pdf-hinzufügen)
- [7. Lokale Vorschau (optional)](#7-lokale-vorschau-optional)
- [8. Eigene Domain (optional)](#8-eigene-domain-optional)

---

## 1. Struktur der Seite

```
academic-site/
├── _config.yml         ← Grundeinstellungen (Name, Fach, Links)
├── index.md             ← Startseite
├── publikationen.md      ← Publikationsliste
├── lebenslauf.md         ← Lebenslauf
├── blog.md               ← Blog-Übersicht (wird automatisch befüllt)
├── _posts/               ← Hier liegt ein Blogbeitrag pro Datei
├── _layouts/              ← Design-Vorlagen (i.d.R. nicht anfassen)
└── assets/
    ├── css/style.css      ← Gestaltung
    └── img/                ← Bilder (Porträtfoto etc.)
```

## 2. Schnellstart: Auf GitHub veröffentlichen

1. **GitHub-Konto** erstellen, falls noch nicht vorhanden: https://github.com/join
2. **Neues Repository** anlegen: oben rechts auf **+** → *New repository*.
   - Für eine Seite unter `https://DEINNAME.github.io` muss das Repository
     **exakt** `DEINNAME.github.io` heißen (dein GitHub-Benutzername).
   - Alternativ ein beliebiger Name, dann ist die Seite unter
     `https://DEINNAME.github.io/REPO-NAME` erreichbar (siehe Schritt 5).
   - Sichtbarkeit: **Public** (bei privaten Repos ist GitHub Pages
     kostenpflichtig).
3. **Dateien hochladen**: Im neuen, leeren Repository auf
   *„uploading an existing file"* klicken, den kompletten Inhalt dieses
   Ordners (`academic-site/`, also alle Dateien **innerhalb** des Ordners,
   nicht den Ordner selbst) per Drag & Drop hochladen und committen.
   - Alternativ mit Git über die Kommandozeile:
     ```bash
     cd academic-site
     git init
     git add .
     git commit -m "Erste Version meiner Wissenschaftsseite"
     git branch -M main
     git remote add origin https://github.com/DEINNAME/DEINNAME.github.io.git
     git push -u origin main
     ```
4. **GitHub Pages aktivieren**: Im Repository auf **Settings → Pages**.
   Unter *„Build and deployment"* → *Source* **„Deploy from a branch"**
   auswählen, Branch **main**, Ordner **/(root)**, dann **Save**.
5. Nach ein bis zwei Minuten ist die Seite live unter der oben angezeigten
   Adresse (z. B. `https://deinname.github.io`).
   - Falls dein Repository **nicht** `DEINNAME.github.io` heißt, trage den
     Repo-Namen zusätzlich in `_config.yml` bei `baseurl: "/REPO-NAME"` ein
     und committe die Änderung erneut.

## 3. Eigene Angaben eintragen

Öffne `_config.yml` und ersetze:
- `title`, `tagline`, `email`, `author`
- optional `orcid`, `google_scholar`, `github_username`, `linkedin`

Öffne danach `index.md` und `lebenslauf.md` und ersetze alle Texte in
eckigen Klammern `[wie hier]` durch deine eigenen Angaben.

## 4. Blogbeiträge schreiben

Neuer Beitrag = neue Datei im Ordner `_posts/`.

- **Dateiname zwingend im Format**: `JAHR-MONAT-TAG-titel.md`
  Beispiel: `2026-09-01-konferenz-in-wien.md`
- **Kopf der Datei** (sog. Front Matter):
  ```yaml
  ---
  title: "Mein Beitrag zur Konferenz in Wien"
  tags: [Konferenz, Reisebericht]
  ---
  ```
- Darunter ganz normal Text in Markdown schreiben (Überschriften mit `##`,
  Fettschrift mit `**fett**`, Links mit `[Text](https://...)`).

Der Beitrag erscheint automatisch auf `/blog/` und auf der Startseite –
kein weiterer Schritt nötig. Du kannst neue Beiträge auch direkt im Browser
anlegen: im Ordner `_posts/` auf GitHub.com auf **Add file → Create new
file** klicken.

## 5. Publikationen & Lebenslauf pflegen

- In `publikationen.md`: Jeder Eintrag ist ein Block
  `<li class="pub-entry">…</li>`. Zum Hinzufügen eines Eintrags einen
  bestehenden Block kopieren und Titel, Autor:innen, Jahr, Journal und
  Link anpassen.
- In `lebenslauf.md`: Jede Station ist ein Block `<div class="cv-row">…
  </div>`. Ebenso kopieren und anpassen.

## 6. Porträtfoto & Lebenslauf-PDF hinzufügen

1. Foto als `portrait.jpg` in `assets/img/` ablegen.
2. In `index.md` den auskommentierten `<img>`-Block aktivieren (die
   `<!-- -->`-Zeichen entfernen) und den Platzhalter-Block darüber löschen.
3. Für den Download-Button: Lebenslauf-PDF als `cv.pdf` in `assets/`
   ablegen – der Button auf der Lebenslauf-Seite funktioniert dann
   automatisch.

## 7. Lokale Vorschau (optional)

Falls du Ruby installiert hast, kannst du die Seite vor dem Hochladen lokal
ansehen:

```bash
bundle install
bundle exec jekyll serve
```

Danach ist die Vorschau unter `http://localhost:4000` erreichbar. Änderungen
werden bei den meisten Dateien automatisch neu geladen.

## 8. Eigene Domain (optional)

Unter **Settings → Pages → Custom domain** kannst du eine eigene Domain
(z. B. `deinname.de`) hinterlegen. GitHub zeigt dir dort die nötigen
DNS-Einträge für deinen Domain-Anbieter an.
