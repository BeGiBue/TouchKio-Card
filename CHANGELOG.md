# Changelog

## 1.0.0 - 2026-10-07

- Erste Version der TouchKio Card im Stil der NAS Card.
- Display-Helligkeit als Slider; Tippen auf das Symbol schaltet das Display ein oder aus.
- Seiten-Zoom als Slider (Number-Entität, Min/Max/Schritt aus der Entität).
- Kacheln für Bildschirmtastatur (Schalter) sowie Kiosk-Modus und Theme (Auswahl).
- Seitenauswahl: Picker mit allen vorhandenen Home-Assistant-Dashboards und Ansichten; schreibt die gewählte URL in die Text-Entität. Der Stift öffnet die Detailansicht zum manuellen Bearbeiten.
- Freigestelltes TouchKio-Gerätebild eingebettet und groß im Hintergrund; Optionen `show_image` und `image_url`.
- Prozessor-Temperatur, CPU, RAM und Paket-Updates mit Warnfarben (CPU orange ab 75 %, RAM ab 80 %, Temperatur ab 70 °C; rot ab 90 %, 90 % bzw. 80 °C).
- Netzwerkadresse und Laufzeit als Textkacheln.
- App-Update-Zeile mit installierter und ggf. neuer Version.
- Aktionen Aktualisieren, Neustart und Herunterfahren; Neustart und Herunterfahren verlangen ein zweites Tippen.
- Alle Entitäten sind im grafischen Editor wählbar; nicht gesetzte Bereiche werden ausgeblendet.
- Glas-Look: Hintergrund, Rand und Blur kommen vom Theme. Schrift wächst mit der Kartenbreite, Option `scale` für Kiosk-Displays.
- HACS-Metadaten und Validierung über GitHub Actions.
