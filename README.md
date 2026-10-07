<h1 align="center">TouchKio Card</h1>

<p align="center">
  Custom-Card für <a href="https://github.com/leukipp/touchkio">TouchKio</a> – Steuerung und Status eines Raspberry-Pi-Kiosks im Stil der NAS Card.
</p>

## Screenshot

<p align="center">
  <img src="https://raw.githubusercontent.com/BeGiBue/TouchKio-Card/main/images/Screenshot.png" alt="TouchKio Card Screenshot" width="400">
</p>

<p align="center">
  <sub>Darstellung mit Beispieldaten und Beispiel-Theme; Farben und Hintergrund kommen von deinem Home-Assistant-Theme.</sub>
</p>

<p align="center">
  <strong>Version 1.0.0</strong><br>
  <a href="https://github.com/BeGiBue/TouchKio-Card/actions/workflows/validate.yml"><img src="https://github.com/BeGiBue/TouchKio-Card/actions/workflows/validate.yml/badge.svg" alt="HACS validation"></a>
</p>

## Funktionen

- Theme-sensitive Darstellung für Light Mode, Dark Mode und benutzerdefinierte Home-Assistant-Themes (Glas-Look)
- Freigestelltes TouchKio-Gerätebild direkt in der JavaScript-Komponente eingebettet – groß im Hintergrund; optional eigene Bild-URL oder ausblendbar
- Display-Helligkeit per Slider; Tippen auf das Symbol schaltet das Display ein oder aus
- Seiten-Zoom per Slider
- Bildschirmtastatur als Schalter-Kachel
- Kiosk-Modus und Theme als Auswahl-Kacheln (nativer Picker)
- Seitenauswahl: Picker mit allen vorhandenen Home-Assistant-Dashboards und deren Ansichten; die Auswahl wird in die Seiten-URL-Entität geschrieben. Der Stift öffnet die Detailansicht zum manuellen Bearbeiten der URL
- Prozessor-Temperatur, CPU, RAM und Paket-Updates; Warnfarben (CPU orange ab 75 %, RAM ab 80 %, Temperatur ab 70 °C, rot ab 90 % / 90 % / 80 °C)
- Netzwerkadresse und Laufzeit
- App-Update-Zeile mit installierter und ggf. neuer Version; bei verfügbarem Update und unterstützter Installation erscheint der Button **Installieren** (mit zweitem Tippen zur Bestätigung), während der Installation der Fortschritt in Prozent
- Tippen auf die Kachel **Pakete** klappt die Liste der verfügbaren System-Updates (Paketname und neue Version) auf und wieder zu
- Aktualisieren, Neustart und Herunterfahren; Neustart und Herunterfahren verlangen ein zweites Tippen
- Alle Entitäten über native Home-Assistant-Entity-Picker wählbar; nicht gesetzte Bereiche werden ausgeblendet
- Breite im Sections-Dashboard frei von 4 bis 12 Spalten, Höhe automatisch
- Optimiert für Hochformat und Touch – iPhone, iPad und Raspberry-Pi-Kiosk: Schrift wächst mit der Kartenbreite

## Standard-Entitäten

```text
light.touchkio_touchkio_display
number.touchkio_touchkio_page_zoom
switch.touchkio_touchkio_keyboard
select.touchkio_touchkio_kiosk
select.touchkio_touchkio_theme
text.touchkio_touchkio_page_url
sensor.touchkio_touchkio_processor_temperature
sensor.touchkio_touchkio_processor_usage
sensor.touchkio_touchkio_memory_usage
sensor.touchkio_touchkio_package_upgrades
sensor.touchkio_touchkio_network_address
sensor.touchkio_touchkio_up_time
update.touchkio_touchkio_app
button.touchkio_touchkio_refresh
button.touchkio_touchkio_reboot
button.touchkio_touchkio_shutdown
```

Alle Entitäten können im grafischen Karteneditor geändert oder geleert werden. Ein leeres Feld blendet den zugehörigen Bereich aus.

## Installation über HACS

1. In HACS **Benutzerdefinierte Repositories** öffnen.
2. `https://github.com/BeGiBue/TouchKio-Card` hinzufügen.
3. Als Typ **Dashboard** auswählen.
4. **TouchKio Card** installieren.
5. Home Assistant bzw. den Browser vollständig neu laden.

## Card hinzufügen

Minimal:

```yaml
type: custom:touchkio-card
```

Vollständiges Beispiel:

```yaml
type: custom:touchkio-card
title: TouchKio
subtitle: Kiosk-Steuerung
display_entity: light.touchkio_touchkio_display
zoom_entity: number.touchkio_touchkio_page_zoom
keyboard_entity: switch.touchkio_touchkio_keyboard
kiosk_entity: select.touchkio_touchkio_kiosk
theme_entity: select.touchkio_touchkio_theme
url_entity: text.touchkio_touchkio_page_url
temperature_entity: sensor.touchkio_touchkio_processor_temperature
cpu_entity: sensor.touchkio_touchkio_processor_usage
memory_entity: sensor.touchkio_touchkio_memory_usage
packages_entity: sensor.touchkio_touchkio_package_upgrades
network_entity: sensor.touchkio_touchkio_network_address
uptime_entity: sensor.touchkio_touchkio_up_time
update_title: App-Update
update_entity: update.touchkio_touchkio_app
refresh_entity: button.touchkio_touchkio_refresh
reboot_entity: button.touchkio_touchkio_reboot
shutdown_entity: button.touchkio_touchkio_shutdown
```

## Optionen

| Option | Werte | Standard | Beschreibung |
|---|---|---|---|
| `show_image` | `true` \| `false` | `true` | Gerätebild im Hintergrund anzeigen. |
| `image_url` | URL | leer | Eigenes Gerätebild, z. B. `/local/images/touchkio.png`. Leer = eingebettetes Standardbild. |
| `scale` | `0.8` – `1.8` | `1` | Skaliert die gesamte Card, z. B. für Kiosk-Displays. |
| `confirm_actions` | `true` \| `false` | `true` | Neustart und Herunterfahren erst nach einem zweiten Tippen auslösen. |

## Updates

**App-Update (TouchKio selbst):** Die Update-Entität zeigt installierte und neue Version. Unterstützt TouchKio auf dem Gerät die Installation (Installation per `.deb` mit Dienst), erscheint in der Zeile der Button **Installieren**. Er ruft `update.install` auf; TouchKio führt dann sein Update-Skript aus und meldet den Fortschritt zurück. Unterstützt die Entität keine Installation, zeigt die Zeile nur den Status – das Update muss dann auf dem Gerät erfolgen.

**System-Updates (apt):** TouchKio prüft stündlich per `apt list --upgradable` und meldet Anzahl und Liste (Attribut `packages` des Sensors „Package Upgrades"). Die Card zeigt die Liste an. Installieren lässt sich das aus Home Assistant nicht, weil TouchKio dafür keinen Dienst bereitstellt; auf dem Gerät: `sudo apt update && sudo apt upgrade`.

## Seitenauswahl

Der Picker liest über die Home-Assistant-Schnittstelle die Dashboards (`lovelace/dashboards/list`) und deren Ansichten (`lovelace/config`) und bietet sie gruppiert nach Dashboard an. Bei der Auswahl wird die komplette URL per `text.set_value` in `url_entity` geschrieben.

- Der Adressanfang (z. B. `http://homeassistant.local:8123`) wird aus der aktuell gesetzten Seiten-URL übernommen, weil TouchKio die Adresse so erreicht, wie sie dort steht. Ist noch keine URL gesetzt, wird die Adresse der Home-Assistant-Oberfläche verwendet.
- Eine URL, die in keiner Ansicht vorkommt, wird als „Eigene URL" angezeigt und bleibt unverändert, bis eine andere Seite gewählt wird.
- Dashboards im automatisch generierten Modus liefern keine Konfiguration und erscheinen mit einer einzelnen Startseite.
- Die Auswahl wird einmal beim Laden der Card gelesen; nach neuen Dashboards oder Ansichten die Seite neu laden.

## Bild

Das freigestellte TouchKio-Gerätebild ist direkt in der JavaScript-Komponente eingebettet und wird nicht aus einem Ordner geladen. Mit `show_image: false` wird es ausgeblendet, mit `image_url` durch ein eigenes Bild ersetzt.

## Hinweise zu Marken

Dieses Projekt ist ein unabhängiges Community-Projekt und steht in keiner Verbindung zu TouchKio oder Home Assistant.

## Lizenz

GNU Affero General Public License v3.0 only (**AGPL-3.0-only**). Details stehen in [`LICENSE`](LICENSE).
