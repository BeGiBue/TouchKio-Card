# Release Checklist — v1.0.0

## Repository vorbereitet

- [x] `VERSION` steht auf `1.0.0`.
- [x] Versionskennung in `touchkio-card.js` steht auf `1.0.0`.
- [x] `README.md` zeigt Version `1.0.0`.
- [x] `CHANGELOG.md` für `1.0.0` geschrieben.
- [x] `RELEASE_NOTES_1.0.0.md` vorbereitet.
- [x] `hacs.json` verweist auf `touchkio-card.js`.
- [x] HACS-Validierung ist für `main`, Pull Requests und manuelle Ausführung vorbereitet.
- [x] README beschreibt Installation, Konfiguration, Updates und Seitenauswahl.
- [x] `.github/CODEOWNERS` enthält `@BeGiBue`.
- [x] Lizenz AGPL-3.0-only.

## Vor Veröffentlichung prüfen

- [ ] **GitHub-Topics setzen** (Repository → About → Zahnrad → Topics), z. B. `home-assistant`, `hacs`, `lovelace`, `custom-card`, `dashboard`, `touchkio`. Ohne Topics schlägt die HACS-Prüfung „Validation topics" fehl (alle anderen 7 Prüfungen bestehen).
- [ ] HACS-Validate-Lauf auf dem finalen `main`-Commit erfolgreich abschließen (Actions → Validate → Run workflow).
- [ ] Card in Home Assistant mit Light Mode prüfen.
- [ ] Card in Home Assistant mit Dark Mode prüfen.
- [ ] Visuellen Editor prüfen: Titel, Untertitel, Bild-Optionen und alle Entity-Picker.
- [ ] Breitenänderung im Sections-Dashboard prüfen; Höhe darf nicht manuell skalierbar sein.
- [ ] Mobile Ansicht prüfen (iPhone, iPad, Kiosk).
- [ ] Display-Slider mit der echten TouchKio-Instanz prüfen.
- [ ] Seitenauswahl prüfen: Dashboards und Ansichten werden geladen, Auswahl ändert die Seiten-URL.
- [ ] Kiosk-Modus und Theme (Auswahl) sowie Bildschirmtastatur (Schalter) prüfen.
- [ ] Paket-Liste prüfen (Tippen auf „Pakete").
- [ ] App-Update prüfen: Button „Installieren" erscheint nur, wenn die Entität es unterstützt; Fortschrittsanzeige.
- [ ] Aktualisieren, Neustart und Ausschalten mit den Button-Entitäten prüfen (zweites Tippen).
- [ ] Optional: `images/Screenshot.png` durch einen Screenshot aus dem eigenen Dashboard ersetzen (aktuell Darstellung mit Beispieldaten).

## Veröffentlichung

- [ ] Nach dem erfolgreichen HACS-Lauf Tag `v1.0.0` auf dem finalen `main`-Commit erstellen.
- [ ] Danach GitHub Release `v1.0.0` mit dem Inhalt aus `RELEASE_NOTES_1.0.0.md` veröffentlichen.
- [ ] Optional: Aufnahme in `hacs/default` per Pull Request beantragen.
