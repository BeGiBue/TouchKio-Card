# Release-Checkliste

Für `X.Y.Z` die Version einsetzen.

## Repository vorbereiten

- [ ] `VERSION` steht auf `X.Y.Z`.
- [ ] Versionskennung in `touchkio-card.js` steht auf `X.Y.Z`.
- [ ] `README.md` zeigt Version `X.Y.Z`.
- [ ] `CHANGELOG.md` hat einen Eintrag für `X.Y.Z`; frühere Einträge bleiben unverändert.
- [ ] `RELEASE_NOTES_X.Y.Z.md` ist vorbereitet.
- [ ] HACS-Validierung auf dem finalen `main`-Commit ist grün.

## Vor Veröffentlichung prüfen

- [ ] Änderungen im echten Dashboard prüfen (Editor, Seitenauswahl, Display-Slider, Paketliste, App-Update, Laufzeit).
- [ ] Bestehende Karten mit älterer Konfiguration laden ohne Fehler.

## Veröffentlichung

- [ ] Tag `vX.Y.Z` auf dem finalen `main`-Commit erstellen.
- [ ] GitHub Release `vX.Y.Z` mit dem Inhalt aus `RELEASE_NOTES_X.Y.Z.md` veröffentlichen.
- [ ] In HACS auf das Update prüfen und installieren.
