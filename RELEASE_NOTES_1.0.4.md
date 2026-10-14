# TouchKio Card 1.0.4

## Behoben

- Scrollen im TouchKio-Kiosk: Die Card blockiert Wischgesten nicht mehr. Nur die aufgeklappte Paketliste scrollt selbst und reicht die Geste am Ende an die Seite weiter.
- Die Card wächst bei Überstand mit dem Inhalt; die Höhe wird auch nach Umbrüchen und dem Laden der Schrift neu gemessen.
- Display-Slider bleibt nach einem abgebrochenen Touch nicht mehr im Ziehen-Zustand hängen.

## Neu

- Kompakte Darstellung für kleine Hochformat-Displays (Raspberry Pi 7" hochkant). Option `compact: auto | on | off`; im TouchKio-Kiosk wird sie bei schmalem Hochformat automatisch aktiv.

## Update

Über HACS aktualisieren und den Browser bzw. die Home-Assistant-App vollständig neu laden. Die Konfiguration muss nicht geändert werden.
