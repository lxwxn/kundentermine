# Kundentermine – Todo-App fürs iPhone

Eine einzelne Web-App (`index.html`). Es gibt kein Backend, keinen Build-Schritt und keine Installation aus dem App Store.
Alle Daten bleiben **nur lokal auf dem iPhone** (im Speicher der Web-App).

## Aufbau
**Kunde › Projekt › Aufgabe › Teilaufgabe**, z. B. *Heide Sommer › eSHOP › Startseiten-Design › ☐ Button anpassen*

Unten gibt es vier Tabs: **Kunden · Heute · Termine · Mehr**. Beim Start öffnet die App den zuletzt genutzten Tab.

## Funktionen
- **Kunden** (Einstieg):
  - Name, optionale Kundennr. und Notiz.
  - In der Liste siehst du je Kunde aktive Projekte, offene Aufgaben und den nächsten Termin.
  - Ein Kunde enthält:
    - **Projekte** mit Fortschritt
    - **Aufgaben ohne Projekt** (mit Schnellfeld)
    - **Termine**
    - abgeschlossene Projekte (eingeklappt)
  - Einträge ohne Kunde sammeln sich unter **„Ohne Kunde“**. Wird ein Kunde gelöscht, landen seine Projekte, Aufgaben und Termine dort.
- **Projekte**:
  - Name, Kunde, Fälligkeit und Notiz.
  - **Schnellfeld:** Return legt eine Aufgabe an, der Cursor bleibt für die nächste im Feld.
  - **Liste einfügen:** Eine kopierte Liste wird in einzelne Aufgaben zerlegt. Aufzählungszeichen wie `-`, `•` und `1.` fallen weg.
  - **Projekt abschließen** hakt alle restlichen Aufgaben ab.
  - **Projekt teilen** schickt eine Checkliste samt Teilaufgaben.
  - **Projekt löschen** löscht seine Aufgaben mit. Ausnahme sind Aufgaben aus Terminen; sie bleiben beim Kunden.
- **Aufgaben**:
  - Ein Tipp öffnet die Aufgabe mit ihren **Teilaufgaben**.
  - Über „Bearbeiten“ änderst du:
    - Kunde und Projekt (auch zum Verschieben)
    - **Wer** (leer = du selbst)
    - **Fällig am** (mit Schnellknöpfen)
    - **★ Wichtig**
    - **Ergebnis**
    - **Rückmeldung an Kunden nötig**: Dann gibt es zwei Haken, erst „geklärt“, dann „Kunde informiert“.
  - Aufgaben in einem Projekt erben dessen Kunden. Aufgaben aus einem Termin erben Kunde und Projekt des Termins.
- **Teilaufgaben**: eine schlichte Checkliste in der Aufgabe.
  - Return legt die nächste Zeile an, die Rücktaste in einer leeren Zeile löscht sie.
  - Eine eingefügte Liste wird zerlegt.
  - Der Fortschritt steht überall als `☑ 3/8` an der Aufgabe. Sind alle Teilaufgaben erledigt, schlägt die App vor, die Aufgabe abzuhaken.
- **Heute**: alle offenen Aufgaben über alle Kunden hinweg, jeweils mit „Kunde › Projekt“.
  - **Ich:** deine Aufgaben und Termine, für die noch ein Bericht fehlt. Gruppiert nach Fälligkeit, Kunde oder Projekt.
  - **Klären:** nach Person oder Abteilung gruppiert, mit „Liste teilen“.
    - Mit **„Angefragt“** merkst du dir, wann du gefragt hast. Nach 7 Tagen ohne Antwort wird der Punkt markiert. Mit „Nachgehakt“ beginnt die Frist neu.
    - „Liste teilen“ markiert die geteilten Punkte automatisch als angefragt.
  - **Rückmeldung:** geklärte Punkte je Kunde, mit „Antwort-Entwurf“.
  - **Suche** nach Text, Kunde, Kundennr., Projekt, Wer, Ergebnis und Teilaufgaben.
- **Schnellfeld (1-Zeiler)**: Es gibt eins unter Heute, beim Kunden und im Projekt. Kurzbefehle werden erkannt und vor dem Return unter dem Feld angezeigt:
  - Fälligkeit: `heute`, `morgen`, `übermorgen`, `nächste Woche`, `Freitag`, `bis Fr` / `am Mo`, `12.12.`
    - Kurzformen wie „Fr“ gelten nur nach „bis“ oder „am“, damit „Fr. Müller“ Text bleibt.
  - `@Einkauf` → Wer. Die Aufgabe landet dann unter „Klären“.
  - `#Heide Sommer` oder `#K-10471` → Kunde. Ein unbekannter Kunde erscheint in der Vorschau als „neuer Kunde“ und wird beim Speichern angelegt.
  - `!` → wichtig
  - Beispiel: `Angebot schicken bis Fr #K-10471 @Einkauf !`
- **Termine**:
  - Titel/Betreff, Kunde, Projekt (optional), Beginn/Ende, Ort und Teilnehmer.
  - Der Tab „Termine“ listet alle Termine in „anstehend“ und „vergangen“ und ist durchsuchbar.
  - Außerdem stehen Termine beim Kunden und im Projekt.
  - **Aus Outlook-Einladung übernehmen:** Einladungstext einfügen oder eine `.ics`-Datei wählen. Betreff, Datum, Uhrzeit, Ort und Teilnehmer werden erkannt.
  - **Stichpunkte:**
    - Return erzeugt einen neuen Stichpunkt, die Rücktaste in einer leeren Zeile löscht ihn.
    - `#` am Anfang macht die Zeile zum Thema, also zur Überschrift im Bericht.
    - **→ Aufgabe** macht aus einem Stichpunkt eine Aufgabe.
  - **Themen-Vorlage:** deine Standard-Gliederung, festgelegt unter Mehr.
  - **Bericht-Entwurf:** Kunde, Anlass, Projekt, Themen, Stichpunkte und die vereinbarten Maßnahmen samt Teilaufgaben. Der Bericht steht unter „Heute“, bis du ihn abhakst.
  - **Kalender:** Termin als `.ics` exportieren.
- **Teilen:** ein Termin, ein Projekt, die offenen Aufgaben eines Kunden oder alle offenen Aufgaben (unter Mehr) als Text an Mail, Notizen, Teams usw.
- **Backup:** Export und Import als JSON-Datei. Die App erinnert dich, wenn das letzte Backup länger als 14 Tage zurückliegt. Ältere Backups lassen sich weiter laden; sie werden automatisch auf den neuen Aufbau umgestellt.

Die Abstimmung mit anderen läuft bewusst außerhalb der App. Die App ist nur dein persönlicher Überblick.

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
