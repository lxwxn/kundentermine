# Kundentermine – Todo-App fürs iPhone

Eine einzelne Web-App (`index.html`). Es gibt kein Backend, keinen Build-Schritt und keine Installation aus dem App Store.
Alle Daten bleiben **nur lokal auf dem iPhone** (im Speicher der Web-App).

## Funktionen
- **Termine:** Kunde, Beginn/Ende, Ort und Teilnehmer. Die Liste ist in „anstehend“ und „vergangen“ aufgeteilt und durchsuchbar.
- **Aus Outlook-Einladung übernehmen:** Einladungstext einfügen oder eine `.ics`-Datei wählen. Betreff, Datum, Uhrzeit, Ort und Teilnehmer werden automatisch erkannt.
- **Stichpunkte:** Return erzeugt einen neuen Stichpunkt, Rücktaste in einer leeren Zeile löscht ihn.
  Eine Zeile, die mit `#` beginnt, wird zum Thema und damit zur Überschrift im Bericht.
- **Themen-Vorlage:** deine Standard-Gliederung, festgelegt unter Mehr. Im Termin per Knopf einfügen oder bei neuen Terminen automatisch. Themen, unter denen nichts steht, erscheinen nicht im Bericht.
- **→ Aufgabe:** macht aus einem Stichpunkt eine Aufgabe, die mit dem Termin und seinem Kunden verknüpft ist.
- **Aufgaben anlegen**
  - **Schnellfeld (1-Zeiler)** oben im Bereich „Aufgaben“. Kurzbefehle im Text werden erkannt und unter dem Feld angezeigt, bevor du Return drückst:
    - `heute`, `morgen`, `übermorgen`, `nächste Woche`, `Freitag`, `bis Fr` / `am Mo`, `12.12.` → Fälligkeit
      (Kurzformen wie „Fr“ nur nach „bis“ oder „am“, damit „Fr. Müller“ Text bleibt)
    - `@Einkauf` → Wer (bekannte Namen auch mit Leerzeichen, z. B. `@Hr. Schulz`) – die Aufgabe landet dann unter „Klären“
    - `#K-10471` → Kundennummer
    - `!` → wichtig
    - Beispiel: `Angebot schicken bis Fr #K-10471 @Einkauf !`
  - **„+“** öffnet das vollständige Formular.
- **Aufgaben** haben optional:
  - **Kundennr. und Kunde**: Eine bekannte Nummer ergänzt den Namen und umgekehrt. Aufgaben aus einem Termin übernehmen dessen Kunden automatisch, solange die Felder leer bleiben.
  - **Wer**: Person oder Abteilung, leer bedeutet du selbst.
  - **Fällig am** mit Schnellknöpfen „Heute“, „Morgen“, „Nächste Woche“ und „✕“.
  - **★ Wichtig**: Diese Aufgaben stehen oben in ihrer Gruppe. Auch direkt in der Liste per Stern umschaltbar.
  - **Ergebnis**: was du in Erfahrung gebracht hast.
  - **Rückmeldung an Kunden nötig**: Die Aufgabe hat dann zwei Schritte. Der erste Haken bedeutet „geklärt“, der zweite „Kunde informiert“.
- **Projekte** (eigener Tab): bündeln viele kleine Teilaufgaben, z. B. „Shopdesign“ mit Footer, Slider, Buttons anpassen …
  - Projekt mit Name, optional Kundennr./Kunde, Fälligkeit und Notiz. Teilaufgaben erben den Kunden.
  - **Schnellfeld im Projekt:** Return legt die Teilaufgabe an, der Cursor bleibt im Feld für die nächste. Kurzbefehle wie `morgen`, `@Wer` und `!` funktionieren auch hier.
  - **Liste einfügen:** Eine kopierte Liste mit mehreren Zeilen wird beim Einfügen in einzelne Teilaufgaben zerlegt. Aufzählungszeichen wie `-`, `•` oder `1.` fallen weg.
  - Teilaufgaben sind normale Aufgaben. Antippen öffnet Wer, Fälligkeit, ★ und Rückmeldung. Mit `@Wer` landen sie unter „Klären“.
  - In **„Ich“** erscheint jedes Projekt als **eine Zeile** mit Fortschritt (z. B. 4/12) und der nächsten Teilaufgabe. Einzeln stehen dort nur Teilaufgaben mit Fälligkeit oder ★.
  - **Projekt abschließen** hakt alle restlichen Teilaufgaben ab. Abgeschlossene Projekte findest du im Tab „Projekte“ unter „Abgeschlossen“.
  - Eine bestehende Aufgabe lässt sich im Formular über das Feld „Projekt“ einem Projekt zuordnen.
- **Kundenstamm:** Paare aus Kundennr. und Name werden gemerkt, sobald du sie bei einer Aufgabe oder einem Projekt einträgst. Unter Mehr → Kunden kannst du sie bearbeiten oder anlegen.
  Auch Termine haben eine optionale Kundennr.
- **Suche** im Bereich „Aufgaben“: nach Text, Kunde, Kundennr., Wer und Ergebnis, über alle drei Ansichten.
- **Aufgaben** in drei Ansichten:
  - **Ich:** deine eigenen Aufgaben und Termine, für die noch ein Bericht fehlt. Gruppiert „nach Fälligkeit“ oder „nach Kunde“.
  - **Klären:** nach Person oder Abteilung gruppiert, mit „Liste teilen“.
    Mit **„Angefragt“** merkst du dir, wann du gefragt hast. Nach 7 Tagen ohne Antwort wird der Punkt markiert, mit „Nachgehakt“ beginnt die Frist neu.
    „Liste teilen“ markiert die geteilten Punkte automatisch als angefragt.
  - **Rückmeldung:** geklärte Punkte je Kunde, mit „Antwort-Entwurf“.
- **Bericht-Entwurf:** gegliederter Text aus Kopfdaten, Themen, Stichpunkten und den vereinbarten Maßnahmen mit Zuständigkeit. Zum Kopieren nach Word oder Mail.
  Nach dem Termin steht der Bericht so lange in deinen Todos, bis du ihn abhakst.
- **Teilen:** Termin samt Stichpunkten und Aufgaben oder alle offenen Aufgaben (nach Kunde gruppiert) als Text an Mail, Notizen, Teams usw.
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
