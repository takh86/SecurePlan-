# SecurePlan

Praxisphasenprojekt an der THM: fokussierte, rollenbasierte Personaleinsatzplanung für Sicherheitsunternehmen.

> **Stand 22.09.2026**  
> **Aktueller formaler Schritt: Phase 6.5 – Transactions, Concurrency & Idempotency.**  
> Phase 6.1–6.4 sind dokumentiert und freigegeben. Es existiert weiterhin **kein nachgewiesener Produktions-Anwendungscode**. Klickbare Phase-5-Prototypen sind Design-/UX-Artefakte, keine implementierte Produktfunktion.

## Projektstatus

| Bereich | Status |
|---|---|
| Phase 2 – Requirements Baseline v1.1 | **FINAL / APPROVED / FROZEN** |
| Phase 3 – Scope & MVP v1.1 | **FINAL / APPROVED / FROZEN** |
| Phase 3.5 – Product Research & Validation | **FINAL / APPROVED** |
| CR-01 / Baseline Amendment v1.2 | **FINAL / APPROVED** – feste 3er-Ersatzgrenze entfernt |
| CR-02 – B2B-SaaS-Tenant-Modell v1.1 | **FINAL / APPROVED** |
| Phase 4 – Systemanalyse v1.2 | **FINAL / APPROVED** |
| Phase 5 – UX/UI | **PASS FOR PHASE 6**; Phase-5.2-Amendment wirksam |
| Phase 5.9 – reale Usability-Tests | **PENDING FOLLOW-UP**, blockiert Phase 6 nicht |
| Phase 6.1–6.4 – Architektur | **FINAL / APPROVED bzw. RE-APPROVED** |
| Phase 6.5 | **NÄCHSTER SCHRITT** |
| Feature-Implementierung | **NOCH NICHT BEGONNEN / NICHT NACHGEWIESEN** |

Details: [docs/project-status.md](docs/project-status.md)

## Produkt- und SaaS-Modell

- SecurePlan ist B2B-SaaS.
- Company = Tenant.
- Ein Tenant-Benutzerkonto gehört genau einer Company.
- Kein Company Switcher / keine Cross-Company-Membership.
- Platform Admin ist separater Provider-Scope.
- Monate 1–3: Praktikums-MVP, operativ eine Company, technisch tenant-aware.
- Monate 4–6: Multi-Company/Productization mit minimalem providerseitigem Tenant Management.
- Billing/Subscriptions und vollständiges Self-Service-Onboarding bleiben WON'T NOW.

## Verbindlicher Praktikums-MVP

Der wirksame Umfang folgt Phase 3 plus genehmigten Change Requests:

1. Foundation
2. Authentifizierung / RBAC / TenantContext
3. Mitarbeiter & Projekte
4. manueller Monatsplan + Publish + Mitarbeiteransicht
5. Absage & Ersatz
6. planbasierte Statistik
7. Admin Work Queue
8. Qualitätsminimum: Validation, Error Handling, Audit-Minimum, Tests, OpenAPI, CI
9. reproduzierbare Demo-/Staging-Auslieferung

Excel-Import ist SHOULD/Stretch. Tagesplan, Lohnabrechnung und vollständige Notifications sind nicht Teil des verbindlichen 3-Monats-Praktikums-MVP.

Siehe [docs/requirements/effective-mvp-baseline.md](docs/requirements/effective-mvp-baseline.md).

## Dokumentation

| Dokument | Zweck |
|---|---|
| [docs/README.md](docs/README.md) | Dokumentationsindex und Source-of-Truth-Regeln |
| [docs/project-status.md](docs/project-status.md) | Aktueller Gate- und Phasenstand |
| [docs/requirements/effective-mvp-baseline.md](docs/requirements/effective-mvp-baseline.md) | Wirksame MVP-/Produktbaseline |
| [docs/requirements/cr-02-b2b-saas-tenant-model.md](docs/requirements/cr-02-b2b-saas-tenant-model.md) | B2B-SaaS-/Tenant-Change |
| [docs/systemanalyse/phase-4-final-v1.2.md](docs/systemanalyse/phase-4-final-v1.2.md) | Phase-4-Systemanalyse, repo-lokale Kurzfassung |
| [docs/ux-ui/phase-5-baseline.md](docs/ux-ui/phase-5-baseline.md) | Konsolidierter Phase-5-Handoff |
| [docs/architektur/ueberblick.md](docs/architektur/ueberblick.md) | Phase-6-Architekturstand |
| [docs/planung/aktuelle-woche.md](docs/planung/aktuelle-woche.md) | Aktueller Arbeitsabschnitt |
| [docs/planung/fahrplan-12-wochen.md](docs/planung/fahrplan-12-wochen.md) | Implementierungsbaseline + CR-Overlay |
| [docs/planung/arbeitsvorrat.md](docs/planung/arbeitsvorrat.md) | Priorisierter Arbeitsvorrat |
| [docs/planung/fortschrittsprotokoll.md](docs/planung/fortschrittsprotokoll.md) | Tatsächlich nachweisbarer Fortschritt |

## Statusdisziplin

Für Umsetzungsaufgaben gilt: **GEPLANT · IN ARBEIT · FERTIG · BLOCKIERT · ZURÜCKGESTELLT**.

Bei Artefakten: **DOCUMENTED · PROTOTYPED · IMPLEMENTED**.

Ein dokumentierter oder klickbarer UX-Prototyp ist **nicht** automatisch implementierte Software.

## Nächster Gate

Phase 6.5 klärt Transaktionsgrenzen, Concurrency, Optimistic Locking, Idempotency und Duplicate Protection. Danach folgen Security/API/Data-Model-Details und das finale Architecture Review.

**Keine Feature-Implementierung vor dem vollständigen Architektur-Gate.**
