# 12-Wochen-Fahrplan – Implementation Baseline + aktueller Overlay

**Originalbasis:** Phase 3 Scope & MVP v1.1  
**Synchronisiert:** 21.09.2026

## Wichtige Einordnung

Die ursprüngliche Repository-Fassung vom 05.09.2026 behandelte Woche 1 als aktuellen Projektstand. Das ist nicht mehr korrekt.

Seitdem wurden Phase 2/3, Phase 3.5, Systemanalyse und Phase 5 bis zum Gate **PASS FOR PHASE 6** bearbeitet. Der aktuelle formale Schritt ist Phase 6 Architektur.

Der folgende 12-Wochen-Plan bleibt die **Implementierungsbaseline des Praktikums-MVP**. Er ist keine Behauptung, dass der Kalender heute noch bei „Woche 1“ steht.

## Aktueller Overlay

**Jetzt:** Phase 6 – Software Architecture & System Design  
**Danach:** Implementierung entlang der untenstehenden Phase-3-Sequenz  
**Noch nicht erlaubt:** ein UX-Prototyp als implementiertes Feature zählen

## Implementierungsbaseline

| Implementierungswoche | Fokus | Exit-Kriterium |
|---|---|---|
| 1 | Foundation: Repo-Struktur, DB, Migrationen, Docker lokal, CI-Basis | Clean Build + DB-Migration + Testpipeline |
| 2 | Auth/RBAC + User-Grundmodell | serverseitige AuthN/AuthZ funktioniert inkl. Negativtests |
| 3 | Mitarbeiter, Projekte, monatsbezogene Zuordnung | Stammdaten + zentrale Constraints |
| 4 | Monatsplan-Datenmodell + manuelle Erfassung/Pflege | Plan ohne Excel anlegbar/validierbar/bearbeitbar |
| 5 | Publish, Mitarbeiteransicht, Statistik, erste Staging-Iteration | Planning Flow End-to-End |
| 6 | Planänderungen/Revalidation; optional Excel-Import Stretch | Plan-Core stabil |
| 7 | Absage + automatischer Ersatzbedarf + Eligibility | Absage erzeugt gültigen Ersatzbedarf |
| 8 | Ersatzangebote + Büroentscheidung + atomare Übernahme | Hauptworkflow End-to-End |
| 9 | Edge Cases, Idempotenz, Admin Work Queue | Business Rules/Statusübergänge stabil |
| 10 | Regression, Security Review, Audit-Minimum, Error Handling, OpenAPI | Feature Freeze / Hardening |
| 11 | Release Candidate, Deployment-Härtung, README, Demo-Daten | reproduzierbarer Release Candidate |
| 12 | Bugfix, UX-Polish, Regression, Demo, Praktikumsdokumentation | MVP-Abnahme möglich |

## CR-01-Auswirkung

Die historische Week-9-/M5-Regel „3er-Limit“ ist entfernt. Sie darf weder implementiert noch getestet werden.

## Scope Guardrails

- MUST vor SHOULD
- Excel-Import darf den manuellen Monatsplan nicht blockieren
- Tagesplan und Lohnabrechnung bleiben Post-Praktikum
- neue Ideen standardmäßig ins Backlog
- Tests, Authorization und Datenintegrität werden bei Zeitdruck nicht gestrichen
- ab Feature Freeze keine neue MUST-Funktionalität ohne Scope-Entscheidung

## Architektur-Gate vor der Implementierung

Vor Start der Implementierungswoche 1 müssen die Phase-6-Ergebnisse freigegeben sein:
- Module/Boundaries
- Auth-/Security-Ansatz
- Daten-/Transaktionsstrategie
- Concurrency/Idempotenz
- API-/Error-Contracts
- ADR-Basis

Damit wird verhindert, dass „UI zuerst“ oder „DB aus Screens ableiten“ die Architektur bestimmt.
