# Anforderungsgrundlagen

## Erwartete Dokumente

Diese beiden Dokumente sind die verbindliche Grundlage des Projekts und
**müssen hier versioniert abgelegt werden**:

| Datei | Rolle | Status |
|---|---|---|
| `phase-2-requirements-baseline-v1.1-FINAL.<md\|pdf\|docx>` | Produktanforderungsbasis | ⛔ **fehlt** |
| `phase-3-scope-mvp-v1.1-FINAL.<md\|pdf\|docx>` | Maßgebliche Umfangsbasis der Praxisphase | ⛔ **fehlt** |

**Stand 05.09.2026:** Beide Dokumente liegen nicht im Repository vor.
Geprüft wurden: Arbeitsverzeichnis, alle lokalen und entfernten Zweige,
vollständiger Git-Verlauf, GitHub-Issues, GitHub-Pull-Requests.

Solange sie fehlen, sind blockiert:
- `../planung/arbeitsvorrat.md` (keine echten Anforderungskennungen verfügbar)
- die Inhaltsspalten von `../planung/fahrplan-12-wochen.md` ab Woche 2
- die abschließende Machbarkeitsprüfung des MUSS-Umfangs

## Warum das nicht umgangen wird

Ein Arbeitsvorrat mit erfundenen Anforderungskennungen wäre für die Praxisphase
wertlos: Es gäbe keine Rückverfolgbarkeit von der Anforderung über den Code und
den Test bis zum Nachweis. Die Kennungen werden **wörtlich** aus Phase 2/3
übernommen, nicht abgeleitet und nicht erfunden.

## Nach dem Einchecken der Dokumente

1. Beide Dokumente vollständig lesen (Student selbst, nicht nur der Agent).
2. `anforderungs-index.md` befüllen — jede Kennung genau einmal.
3. Stichprobe: 10 Kennungen gegen das Originaldokument prüfen (Wortlaut, Priorität).
4. Konflikte zwischen Phase 2 und Phase 3 im Index dokumentieren; **Phase 3 gewinnt beim Umfang.**
