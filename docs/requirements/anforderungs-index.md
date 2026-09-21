# Anforderungsindex – wirksamer Praktikums-MVP

**Stand:** 21.09.2026  
**Status:** für Phase 6 ausreichend konsolidiert; Code-/Testverweise entstehen mit der Implementierung.

Traceability-Ziel:

Anforderung / Scope → Architekturentscheidung → Vertical Slice → Code → Test → Nachweis

## MVP-Index

| Scope | Anforderungen / Regeln | Priorität | Aktueller Zustand |
|---|---|---|---|
| M1 Foundation | PostgreSQL, Migrationen, Docker lokal, strukturierte Basis, CI | MUST | GEPLANT nach Phase-6-Gate |
| M2 Auth/RBAC | BR-AUTH-01; SEC-AUTHZ-01/02; SEC-EMAIL-01; SEC-SESSION-01; FR-ACT-01 | MUST | Architektur in Phase 6 |
| M3 Mitarbeiter | FR-EMP-01..03; BR-EMP-01..07; BR-AUD-EMP-01 | MUST | Architektur in Phase 6 |
| M3 Projekte | FR-PROJ-01; BR-PROJ-01..05 | MUST | Architektur in Phase 6 |
| M4 Monatsplan | FR-MP-05..09; BR-MP-04..08; manuelle Erfassung als Core | MUST | Architektur in Phase 6 |
| Excel-Import | FR-MP-01..04 | SHOULD / Stretch | ZURÜCKGESTELLT bis Core stabil |
| M5 Absage | FR-AB-01..03; BR-AB-01..05 | MUST | Architektur in Phase 6 |
| M5 Ersatz | BR-ER-00..07; BR-ER-10..11; FR-ER-00..04; FR-NOT-06 | MUST | Architektur in Phase 6 |
| CR-01 | BR-ER-08 entfällt; quota-bezogener BR-ER-09 entfällt; AC-ER-04 entfällt | APPROVED CHANGE | FERTIG dokumentiert |
| M6 Statistik | planbasierte Arbeitstage + TAG/NACHT | MUST | GEPLANT |
| M7 Work Queue | offene Fälle + Deep Link / direkte Navigation | MUST | GEPLANT |
| M8 Quality | Validation, Error Contract, Audit-Minimum, Tests, OpenAPI, CI | MUST | Architektur/Planung |
| M9 Delivery | Docker Build, Setup, Secrets, Demo/Staging, extern HTTPS | MUST | GEPLANT |

## Bewusste Scope Cuts

| Bereich | Praktikumsstatus |
|---|---|
| Tagesplan / Schichtleiter-Tagesplanung | Post-Praktikum |
| Lohnabrechnungen | Post-Praktikum |
| vollständige Notifications | Post-Praktikum |
| Wunschfrei | SHOULD/Stretch |
| Schichttausch | SHOULD/Stretch |
| Full Multi-Tenant SaaS / Billing | Out of Scope |
| Native Mobile App | Won't now |

## Konflikte / Amendments

### CR-01 – Ersatzlimit
Die historische Phase-2/3-Regel „maximal drei Ersatzübernahmen pro Mitarbeiter/Monatsplan“ ist **nicht mehr wirksam**.

Wirksamer Stand:
- keine feste 3er-Obergrenze
- Eligibility bleibt bestehen
- genau ein Ersatz wird final ausgewählt
- atomare Planänderung bleibt Pflicht
- Idempotenz, Authorization, Audit-Minimum und Datenintegrität bleiben Pflicht

## Implementierungsfortschreibung

Mit jedem späteren Vertical Slice werden Spalten für ADR, Slice, Codepfad, Test und Nachweis ergänzt. Bis dahin darf kein Eintrag allein wegen vorhandener UX-Dokumentation als implementiert markiert werden.
