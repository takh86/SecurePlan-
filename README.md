# SecurePlan

Praxisphasenprojekt an der THM: fokussierte, rollenbasierte Personaleinsatzplanung für Sicherheitsunternehmen.

> **Stand 21.09.2026**
> Die Repository-Planung vom 05.09.2026 war veraltet und wurde mit den später freigegebenen Projektartefakten synchronisiert.
> **Aktueller formaler Schritt: Phase 6 – Software Architecture & System Design.**
> Es existiert weiterhin **kein nachgewiesener Produktions-Anwendungscode** in diesem Repository. Klickbare Phase-5-Prototypen sind Design-/UX-Artefakte, keine implementierte Produktfunktion.

## Projektstatus

| Bereich | Status |
|---|---|
| Phase 2 – Requirements Baseline v1.1 | **FINAL / APPROVED / FROZEN** |
| Phase 3 – Scope & MVP v1.1 | **FINAL / APPROVED / FROZEN** |
| Phase 3.5 – Product Research & Validation | **FINAL / APPROVED** |
| CR-01 / Baseline Amendment v1.2 | **FINAL / APPROVED** – feste 3er-Ersatzgrenze entfernt |
| Phase 4 – Systemanalyse v1.1 Professional | fachlicher Stand vorhanden; Dokumentstatus bleibt **REVIEWED DRAFT** |
| Phase 5 – UX/UI | **PASS FOR PHASE 6** |
| Phase 5.9 – reale Usability-Tests | **PENDING FOLLOW-UP**, blockiert Phase 6 nicht |
| Phase 6 – Architektur | **AKTUELL / IN ARBEIT** |
| Feature-Implementierung | **NOCH NICHT BEGONNEN / NICHT NACHGEWIESEN** |

Details: [docs/project-status.md](docs/project-status.md)

## Verbindlicher Praktikums-MVP

Der wirksame Umfang folgt Phase 3 plus genehmigten Change Requests:

1. Foundation
2. Authentifizierung / RBAC
3. Mitarbeiter & Projekte
4. manueller Monatsplan + Publish + Mitarbeiteransicht
5. Absage & Ersatz
6. planbasierte Statistik
7. Admin Work Queue
8. Qualitätsminimum: Validation, Error Handling, Audit-Minimum, Tests, OpenAPI, CI
9. reproduzierbare Demo-/Staging-Auslieferung

Excel-Import ist SHOULD/Stretch. Tagesplan, Lohnabrechnung und vollständige Notifications sind nicht Teil des verbindlichen Praktikums-MVP.

Siehe [docs/requirements/effective-mvp-baseline.md](docs/requirements/effective-mvp-baseline.md).

## Dokumentation

| Dokument | Zweck |
|---|---|
| [docs/project-status.md](docs/project-status.md) | Aktueller Phasenstand und Source-of-Truth-Regeln |
| [docs/requirements/](docs/requirements/) | Wirksame Requirements-/Scope-Baseline und Traceability |
| [docs/ux-ui/phase-5-baseline.md](docs/ux-ui/phase-5-baseline.md) | Konsolidierter Phase-5-Handoff |
| [docs/architektur/ueberblick.md](docs/architektur/ueberblick.md) | Phase-6-Architekturarbeitsstand |
| [docs/planung/aktuelle-woche.md](docs/planung/aktuelle-woche.md) | Aktueller Arbeitsabschnitt |
| [docs/planung/fahrplan-12-wochen.md](docs/planung/fahrplan-12-wochen.md) | Implementierungsbaseline + aktueller Overlay |
| [docs/planung/arbeitsvorrat.md](docs/planung/arbeitsvorrat.md) | Priorisierter Arbeitsvorrat |
| [docs/planung/fortschrittsprotokoll.md](docs/planung/fortschrittsprotokoll.md) | Tatsächlich nachweisbarer Fortschritt |

## Statusdisziplin

Für Umsetzungsaufgaben gilt weiter:
**GEPLANT · IN ARBEIT · FERTIG · BLOCKIERT · ZURÜCKGESTELLT**

Zusätzlich wird bei Projektartefakten klar unterschieden:
**DOCUMENTED · PROTOTYPED · IMPLEMENTED**

Ein dokumentierter oder klickbarer UX-Prototyp ist **nicht** automatisch implementierte Software.

## Nächster Gate

Phase 6 definiert und begründet Architekturziele, Qualitätsattribute, Bausteine, Domain-/Modulgrenzen, Datenverantwortung, Frontend-/Backend-Schnitt, Security-/RBAC-Ansatz, Transaktions-/Concurrency-Strategie und ADR-Kandidaten.

**Keine Feature-Implementierung vor dem Architektur-Gate.**
