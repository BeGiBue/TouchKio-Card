# TouchKio Card 1.0.0

Erste Version der TouchKio Card für Home Assistant: Steuerung und Status eines TouchKio-Kiosks (Raspberry Pi) im Glas-Look der NAS Card.

## Highlights

- Display-Helligkeit und Seiten-Zoom als Slider; Tippen auf das Display-Symbol schaltet das Display ein oder aus
- Bildschirmtastatur, Kiosk-Modus und Theme direkt steuerbar
- Seitenauswahl mit allen vorhandenen Home-Assistant-Dashboards und Ansichten; manuelle URL über den Stift
- Temperatur, CPU, RAM und Paket-Updates mit Warnfarben; Liste der verfügbaren System-Updates per Tippen auf **Pakete**
- Netzwerkadresse und Laufzeit
- App-Update mit Button **Installieren** (zweites Tippen zur Bestätigung) und Fortschrittsanzeige, sofern TouchKio die Installation unterstützt
- Aktualisieren, Neustart und Ausschalten; Neustart und Ausschalten verlangen ein zweites Tippen
- Freigestelltes Gerätebild groß im Hintergrund (abschaltbar oder durch eigenes Bild ersetzbar)
- Alle Entitäten im grafischen Editor wählbar; leere Felder blenden den Bereich aus
- Theme-sensitiv (Light, Dark, eigene Themes), optimiert für iPhone, iPad und Hochformat-Kiosk

## Hinweise

- Systempakete (apt) lassen sich aus Home Assistant nicht installieren, weil TouchKio dafür keinen Dienst bereitstellt. TouchKio selbst wird nicht über apt-Quellen aktualisiert, sondern über die Update-Entität bzw. das TouchKio-Install-Skript.
- Der Seitenpicker liest Dashboards einmal beim Laden der Card; nach neuen Dashboards die Seite neu laden.

## Installation

Das Repository ist für die Installation als HACS-Dashboard-Plugin vorbereitet. `hacs.json` verweist auf `touchkio-card.js`.

Card hinzufügen:

```yaml
type: custom:touchkio-card
```

## Lizenz

GNU Affero General Public License v3.0 only (AGPL-3.0-only)
