# Kundentermine – Todo-App fürs iPhone

Eine einzelne Web-App (`index.html`). Es gibt kein Backend, keinen Build-Schritt und keine Installation aus dem App Store.
Alle Daten bleiben **nur lokal auf dem iPhone** (im Speicher der Web-App).

## Funktionen
- **Termine:** Kunde, Beginn/Ende, Ort und Teilnehmer. Die Liste ist in „anstehend“ und „vergangen“ aufgeteilt und durchsuchbar.
- **Aus Outlook-Einladung übernehmen:** Einladungstext einfügen oder eine `.ics`-Datei wählen. Betreff, Datum, Uhrzeit, Ort und Teilnehmer werden automatisch erkannt.
- **Stichpunkte:** Return erzeugt einen neuen Stichpunkt, Rücktaste in einer leeren Zeile löscht ihn.
  Eine Zeile, die mit `#` beginnt, wird zum Thema und damit zur Überschrift im Bericht.
- **→ Todo:** macht aus einem Stichpunkt ein Todo, das mit dem Kunden verknüpft ist.
- **Todos** haben optional:
  - **Wer**: Person oder Abteilung, leer bedeutet du selbst.
  - **Fällig am**
  - **Ergebnis**: was du in Erfahrung gebracht hast.
  - **Rückmeldung an Kunden nötig**: Das Todo hat dann zwei Schritte. Der erste Haken bedeutet „geklärt“, der zweite „Kunde informiert“.
- **Meine Todos** in drei Ansichten:
  - **Ich:** deine eigenen Todos und Termine, für die noch ein Bericht fehlt.
  - **Klären:** nach Person oder Abteilung gruppiert, mit „Liste teilen“.
  - **Rückmeldung:** geklärte Punkte je Kunde, mit „Antwort-Entwurf“.
- **Bericht-Entwurf:** gegliederter Text aus Kopfdaten, Themen, Stichpunkten und den vereinbarten Maßnahmen mit Zuständigkeit. Zum Kopieren nach Word oder Mail.
  Nach dem Termin steht der Bericht so lange in deinen Todos, bis du ihn abhakst.
- **Teilen:** Termin samt Stichpunkten und Todos oder alle offenen Todos als Text an Mail, Notizen, Teams usw.
- **Kalender:** Termin als `.ics`-Datei exportieren.

Die Abstimmung mit anderen läuft bewusst außerhalb der App. Die App ist nur dein persönlicher Überblick.
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
