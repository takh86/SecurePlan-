# Arbeitsvorrat

**Stand:** 22.09.2026  
**Aktueller Fokus:** Phase 6 Architektur / nächster fachlicher Schritt 6.5.

> Hinweis: Die dokumentierten Teilphasen 6.1–6.4 und die bestehenden Backlog-IDs SP-A06-* sind zwei Sichten auf denselben Architekturarbeitsraum und werden nicht 1:1 umnummeriert.

## P0 — Phase 6 Architektur

### SP-A06-01 — Architekturziele und Qualitätsattribute
**Status:** FERTIG / APPROVED  
**Nachweis:** Phase 6.1 v1.2.

### SP-A06-02 — Systemkontext und Bausteine
**Status:** FERTIG / APPROVED  
**Nachweis:** Phase 6.2 v1.1.

### SP-A06-03 — Domain-/Modulgrenzen
**Status:** FERTIG / APPROVED  
**Nachweis:** Phase 6.3 v1.2.1 – Review Patch.

### SP-A06-03B — Module Dependencies & Public Contracts
**Status:** FERTIG / APPROVED  
**Nachweis:** Phase 6.4 v1.0.1 – Review Patch.

### SP-A06-04 — Datenmodell-Invarianten
**Status:** GEPLANT  
**Ergebnis:** Company/Project/Month, Assignment, Plan, Published/Draft, Case/Offer, Audit-Grundlagen, Tenant-Ownership-Constraints.

### SP-A06-05 — Security / RBAC / API Contracts
**Status:** GEPLANT  
**Ergebnis:** serverseitige Authorization, Tenant Isolation, Ressourcensichtbarkeit, Error-/Permission-Contract.

### SP-A06-06 — Transactions / Concurrency / Idempotency
**Status:** NÄCHSTER SCHRITT  
**Ergebnis:** atomare Ersatzübernahme, Optimistic Locking, Duplicate Protection, Race-Condition-Handling.

### SP-A06-07 — ADR Pack + Architecture Review
**Status:** GEPLANT  
**Ergebnis:** ADR-Entwürfe mit Alternativen/Trade-offs; Human Gate vor Umsetzung.

## P1 — Implementierung nach Architektur-Gate

1. Foundation
2. Auth/RBAC
3. Mitarbeiter & Projekte
4. manueller Monatsplan + Publish
5. Mitarbeiteransicht + Statistik
6. Absage/Ersatz
7. Admin Work Queue
8. Quality/Hardening
9. Demo Delivery

## P2 — SHOULD / Stretch

- Excel-Import
- Wunschfrei
- Schichttausch
- ausgewählte Notifications
- MFA falls Kern stabil
- erweiterte Filter/Suche

## P3 — Monate 4–6 / Product Expansion

- Multi-Company-Aktivierung
- minimaler Platform/Tenant Admin
- providerseitiges Company/Tenant-Onboarding
- weitere priorisierte Product Verticals nach stabilem Core

## Weitere Post-MVP-Bereiche

- Tagesplan / Arbeitspositionen
- Lohnabrechnungen
- vollständige Notification-Matrix
- Production Observability / Backup / RPO/RTO

## Verbindliche Regeln

- CR-01: kein 3er-Ersatzlimit
- CR-02: Company = Tenant; Account genau eine Company
- kein Feature wird aus UX-Screens in den Scope „hineindesignt“
- kein Implementierungsstatus ohne Code-/Testnachweis
- Security, Authorization, Tenant Isolation und Datenintegrität werden nicht als Zeitpuffer verwendet
