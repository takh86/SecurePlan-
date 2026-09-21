# Arbeitsvorrat

**Stand:** 21.09.2026  
**Aktueller Fokus:** Phase 6 Architektur.  
Die alte Blockade „Phase 2/3 fehlen“ ist aufgehoben.

## P0 — jetzt: Phase 6 Architektur

### SP-A06-01 — Architekturziele und Qualitätsattribute
**Status:** IN ARBEIT  
**Ergebnis:** priorisierte Architekturtreiber und klare Praktikum-vs-Production-Abgrenzung.

### SP-A06-02 — Systemkontext und Bausteine
**Status:** GEPLANT  
**Ergebnis:** Kontext-/Container-/Bausteinsicht mit Verantwortlichkeiten.

### SP-A06-03 — Domain-/Modulgrenzen
**Status:** GEPLANT  
**Ergebnis:** begründeter modularer Schnitt; keine 1:1-Abbildung der UI.

### SP-A06-04 — Datenmodell-Invarianten
**Status:** GEPLANT  
**Ergebnis:** Company/Project/Month, Assignment, Plan, Published/Draft, Case/Offer, Audit-Grundlagen.

### SP-A06-05 — Security / RBAC / API Contracts
**Status:** GEPLANT  
**Ergebnis:** serverseitige Authorization, Ressourcensichtbarkeit, Error-/Permission-Contract.

### SP-A06-06 — Transactions / Concurrency / Idempotency
**Status:** GEPLANT  
**Ergebnis:** atomare Ersatzübernahme, Optimistic Locking, Duplicate Protection.

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

## P3 — Post-Praktikum

- Tagesplan / Arbeitspositionen
- Lohnabrechnungen
- vollständige Notification-Matrix
- Production Observability / Backup / RPO/RTO
- Multi-Company UI
- weitere Product Verticals

## Verbindliche Regeln

- CR-01: kein 3er-Ersatzlimit
- kein Feature wird aus UX-Screens in den Scope „hineindesignt“
- kein Implementierungsstatus ohne Code-/Testnachweis
- Security, Authorization und Datenintegrität werden nicht als Zeitpuffer verwendet
