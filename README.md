# Kundentermine – Todo-App fürs iPhone

Eine einzelne Web-App (`index.html`). Es gibt kein Backend, keinen Build-Schritt und keine Installation aus dem App Store.
Alle Daten bleiben **nur lokal auf dem iPhone** (im Speicher der Web-App).

## Funktionen
- **Termine:** Kunde, Datum/Uhrzeit, Ort/Ansprechpartner. Die Liste ist in „anstehend“ und „vergangen“ aufgeteilt und durchsuchbar.
- **Stichpunkte:** Return erzeugt einen neuen Stichpunkt, Rücktaste in einer leeren Zeile löscht ihn.
- **→ Todo:** macht aus einem Stichpunkt ein Todo, das mit dem Kunden verknüpft ist.
- **Meine Todos:** alle Todos über alle Kunden hinweg, gruppiert nach überfällig, heute, demnächst und ohne Datum.
- **Teilen:** Termin samt Stichpunkten und Todos oder alle offenen Todos als Text an Mail, Notizen, Teams usw.
- **Kalender:** Termin als `.ics`-Datei exportieren.
- **Backup:** Export und Import als JSON-Datei. Die App erinnert dich, wenn das letzte Backup länger als 14 Tage zurückliegt.

## Online stellen (GitHub Pages, kostenlos)
1. Auf github.com ein Konto anlegen und ein neues Repository erstellen, z. B. `kundentermine`.
2. Diese Dateien hochladen: `index.html`, `manifest.json`, `icon-180.png`, `icon-512.png`.
3. Im Repository unter **Settings → Pages** als Quelle „Deploy from a branch“ und den Branch `main` mit Ordner `/ (root)` wählen.
4. Nach etwa einer Minute ist die App unter `https://<dein-name>.github.io/kundentermine/` erreichbar.

Das Repository ist öffentlich, enthält aber **nur den Code und keine Kundendaten**.
Alternativ funktioniert jeder Webserver, z. B. der der Firma.

## Aufs iPhone holen
1. Die Adresse in **Safari** öffnen.
2. Auf **Teilen** und dann **„Zum Home-Bildschirm“** tippen.
3. Die App ab jetzt **immer über das Icon** starten.
   Bei normalen Safari-Tabs kann iOS lokale Daten nach längerer Nichtnutzung löschen.

## Datensicherung
Mehr → **Backup erstellen** öffnet das Teilen-Menü. Dort „In Dateien sichern“ wählen oder dir die Datei per Mail schicken.
Mit **Backup wiederherstellen** lädst du die Datei wieder. Das funktioniert auch auf einem neuen Handy.

## Lokal testen
```sh
cd todo-app && python3 -m http.server 8000
# dann http://localhost:8000 im Browser öffnen
```
