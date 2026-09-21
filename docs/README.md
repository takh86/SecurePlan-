# SecurePlan – Projektdokumentation

Dieses Verzeichnis ist die **aktuelle Projektquelle der Wahrheit**. Die alte Repository-Planung vom 05.09.2026 wurde am 21.09.2026 mit den späteren Projektartefakten synchronisiert.

## Aktueller Stand

- Phase 2: FINAL / FROZEN
- Phase 3: FINAL / FROZEN
- Phase 3.5: FINAL / APPROVED
- CR-01: APPROVED; feste Obergrenze von drei Ersatzübernahmen entfernt
- Phase 4: fachlicher Systemanalyse-Stand vorhanden; v1.1-Dokument bleibt als REVIEWED DRAFT bezeichnet
- Phase 5: PASS FOR PHASE 6
- Phase 5.9 reale Nutzertests: offen als kontrolliertes Follow-up
- Phase 6: aktueller Arbeitsabschnitt
- Production Feature Code: nicht nachgewiesen

Siehe [project-status.md](project-status.md).

## Struktur

| Pfad | Zweck |
|---|---|
| requirements/ | wirksame Requirements-/Scope-Baseline, CR-01 und Traceability |
| ux-ui/ | konsolidierter Phase-5-Handoff und UX/UI-Frozen Decisions |
| planung/ | aktueller Arbeitsabschnitt, Backlog, Roadmap, Fortschritt, Risiken |
| architektur/ | Phase-6-Architekturüberblick und ADRs |
| betreuung/ | Vorlagen für Check-in, Check-out und Wochenberichte |

## Source-of-Truth-Reihenfolge

Bei Konflikten gilt:

1. Phase 2 Requirements Baseline v1.1 **plus genehmigte Amendments / CR-01**
2. Phase 3 Scope & MVP v1.1 für den Praktikumsumfang
3. Phase 3.5 Research & Impact Review als Validierung; keine stille Scope-Änderung
4. Phase 4 Systemanalyse für Akteure, Use Cases und Systemgrenzen
5. Phase 5.1–5.10 für UX/UI und den Handoff zu Phase 6
6. ADRs für später ausdrücklich genehmigte technische Entscheidungen

Wichtig: Phase 3 verschiebt gültige Phase-2-Produktanforderungen aus dem Praktikums-MVP, ohne sie als Produktanforderung zu löschen.

## Nachweisregel

**FERTIG** wird nur für tatsächlich nachweisbare Ergebnisse verwendet. Dokumente und Prototypen dürfen als abgeschlossen dokumentiert werden, ohne daraus Implementierungsfortschritt abzuleiten.

Aktuelle Statussemantik:
- **DOCUMENTED**: Analyse-/Designartefakt vorhanden
- **PROTOTYPED**: klickbarer/visueller Prototyp vorhanden
- **IMPLEMENTED**: Produktionscode + Test-/Repository-Nachweis vorhanden
