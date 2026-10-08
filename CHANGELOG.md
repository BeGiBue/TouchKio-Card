# Changelog

## 1.0.2 - 2026-10-08

### Geändert

- Die Höhe der Card ist fest: Im Layout-Editor lässt sie sich nicht mehr verändern (`rows`, `min_rows` und `max_rows` sind gleich), die Breite bleibt frei einstellbar.
- Die aufgeklappte Paketliste ändert die Höhe nicht mehr, sondern scrollt innerhalb der Card.

## 1.0.1 - 2026-10-07

### Geändert

- Laufzeit: Die Einheit wird automatisch gewählt (Min, Std, Tage, ab 7 Tagen Wochen), z. B. „5 Std 12 Min“, „2 Tage 4 Std“, „3 Wochen 2 Tage“. TouchKio meldet die Laufzeit in Minuten.
- Lizenzhinweis: SPDX-Kennung und Copyright im Code-Kopf, ausführlicherer Lizenzabschnitt in der README.
- README: Button zum automatischen Hinzufügen in HACS; aktualisierter Screenshot.

### Entfernt

- Box **Seiten-Zoom** und die Option `zoom_entity`. Steht `zoom_entity` noch in einer bestehenden Konfiguration, wird der Eintrag ignoriert.

## 1.0.0 - 2026-10-07

- Erste Version der TouchKio Card im Stil der NAS Card.
- Display-Helligkeit als Slider; Tippen auf das Symbol schaltet das Display ein oder aus.
- Seiten-Zoom als Slider (Number-Entität, Min/Max/Schritt aus der Entität).
- Kacheln für Bildschirmtastatur (Schalter) sowie Kiosk-Modus und Theme (Auswahl).
- Seitenauswahl: Picker mit allen vorhandenen Home-Assistant-Dashboards und Ansichten; schreibt die gewählte URL in die Text-Entität. Der Stift öffnet die Detailansicht zum manuellen Bearbeiten.
- Freigestelltes TouchKio-Gerätebild eingebettet und groß im Hintergrund; Optionen `show_image` und `image_url`.
- Prozessor-Temperatur, CPU, RAM und Paket-Updates mit Warnfarben (CPU orange ab 75 %, RAM ab 80 %, Temperatur ab 70 °C; rot ab 90 %, 90 % bzw. 80 °C).
- Netzwerkadresse und Laufzeit als Textkacheln.
- App-Update-Zeile mit installierter und ggf. neuer Version. Unterstützt die Entität die Installation, erscheint der Button **Installieren** (zweites Tippen zur Bestätigung, danach Fortschrittsanzeige).
- Die Kachel **Pakete** klappt die Liste der verfügbaren System-Updates (Attribut `packages`) auf.
- Aktionen Aktualisieren, Neustart und Herunterfahren; Neustart und Herunterfahren verlangen ein zweites Tippen.
- Alle Entitäten sind im grafischen Editor wählbar; nicht gesetzte Bereiche werden ausgeblendet.
- Glas-Look: Hintergrund, Rand und Blur kommen vom Theme. Schrift wächst mit der Kartenbreite, Option `scale` für Kiosk-Displays.
- HACS-Metadaten und Validierung über GitHub Actions.
