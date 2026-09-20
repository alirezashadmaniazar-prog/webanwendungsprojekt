# Dokumentation – Git und GitHub

## a) Lokales Git-Repository erstellen

Zuerst wurde ein neuer Projektordner erstellt und geöffnet:

```bash
mkdir webanwendungsprojekt
cd webanwendungsprojekt
```

Danach wurde das Git-Repository initialisiert:

```bash
git init
git branch -M main
```

Anschließend wurde eine Datei namens `README.md` erstellt. Sie enthält eine kurze Beschreibung des Projekts.

Die Datei wurde für den ersten Commit vorgemerkt und gespeichert:

```bash
git add README.md
git commit -m "Initial commit: README hinzugefügt"
```

## b) .gitignore-Datei erstellen

Die Datei `.gitignore` wurde erstellt, damit unnötige Dateien nicht von Git gespeichert werden.

Folgende Regeln wurden eingetragen:

```text
.DS_Store
.idea/
.vscode/
*.log
*.tmp
node_modules/
dist/
.env
```

Dadurch werden unter anderem temporäre Dateien, Protokolldateien, Einstellungen von Entwicklungsumgebungen und installierte Abhängigkeiten ignoriert.

Danach wurde die Datei gespeichert:

```bash
git add .gitignore
git commit -m "Gitignore hinzugefügt"
```

## c) Branches erstellen

Für die allgemeine Entwicklung wurde der Branch `develop` erstellt:

```bash
git switch -c develop
```

Danach wurde der Branch `feature-login` für die neue Login-Funktion erstellt:

```bash
git switch -c feature-login
```

Auf dem Branch `feature-login` wurde die Datei `login-feature.md` angelegt und gespeichert:

```bash
git add login-feature.md
git commit -m "Login-Funktionalität hinzugefügt"
```

Mit `git switch` kann zwischen den Branches gewechselt werden.

## d) Branches zusammenführen

Nach Fertigstellung der Login-Funktion wurde zurück zum Branch `develop` gewechselt:

```bash
git switch develop
```

Danach wurde `feature-login` mit `develop` zusammengeführt:

```bash
git merge feature-login
```

Das Zusammenführen war erfolgreich und wurde als Fast-Forward-Merge ausgeführt. Es gab keine Konflikte.

Falls Konflikte auftreten, zeigt Git die betroffenen Stellen in den Dateien an. Diese Stellen müssen manuell bearbeitet werden. Danach werden die gelösten Dateien erneut vorgemerkt und gespeichert:

```bash
git add DATEINAME
git commit -m "Merge-Konflikt gelöst"
```

## e) Remote-Repository auf GitHub

Auf GitHub wurde ein neues öffentliches Repository mit dem Namen `webanwendungsprojekt` erstellt.

Das lokale Repository wurde mit GitHub verbunden:

```bash
git remote add origin https://github.com/alirezashadmaniazar-prog/webanwendungsprojekt.git
```

Anschließend wurde der Branch `develop` zu GitHub hochgeladen:

```bash
git push -u origin develop
```

Das Remote-Repository ist unter folgender Adresse erreichbar:

https://github.com/alirezashadmaniazar-prog/webanwendungsprojekt

## f) Issue und Milestone erstellen

Auf GitHub wurde der Milestone `Version 1.0` mit der Beschreibung „Erste Version der Webanwendung“ erstellt.

Danach wurde ein Issue mit dem Titel `Passwort-zurücksetzen-Funktion entwickeln` angelegt. Das Issue beschreibt die Anforderung, dass Benutzer ihr vergessenes Passwort zurücksetzen können sollen.

Das Issue wurde dem Milestone `Version 1.0` zugeordnet. Dadurch kann die Anforderung einer geplanten Projektversion zugeordnet und ihr Fortschritt verfolgt werden.