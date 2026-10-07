# Release Checklist — v1.0.1

## Repository vorbereitet

- [x] `VERSION` steht auf `1.0.1`.
- [x] Versionskennung in `touchkio-card.js` steht auf `1.0.1`.
- [x] `README.md` zeigt Version `1.0.1`.
- [x] `CHANGELOG.md` für `1.0.1` geschrieben; der Eintrag für `1.0.0` entspricht dem veröffentlichten Stand.
- [x] `RELEASE_NOTES_1.0.1.md` vorbereitet.
- [x] `hacs.json` verweist auf `touchkio-card.js`.
- [x] HACS-Validierung läuft auf `main` und ist grün (GitHub-Topics gesetzt).
- [x] Lizenz AGPL-3.0-only, SPDX-Kennung im Code.

## Vor Veröffentlichung prüfen

- [ ] HACS-Validate-Lauf auf dem finalen `main`-Commit erfolgreich abschließen.
- [ ] Laufzeit mit dem echten Sensor prüfen (Minuten → Std/Tage/Wochen).
- [ ] Editor prüfen: kein Eintrag „Seiten-Zoom“ mehr; bestehende Karten mit `zoom_entity` laden ohne Fehler.
- [ ] Seitenauswahl, Display-Slider, Paketliste und App-Update im echten Dashboard prüfen.

## Veröffentlichung

- [ ] Tag `v1.0.1` auf dem finalen `main`-Commit erstellen.
- [ ] GitHub Release `v1.0.1` mit dem Inhalt aus `RELEASE_NOTES_1.0.1.md` veröffentlichen.
- [ ] In HACS auf das Update prüfen und installieren.
