# Aktueller Arbeitsabschnitt — Phase 6: Software Architecture & System Design

**Stand:** 22.09.2026  
**Status:** IN ARBEIT / PRE-IMPLEMENTATION  
**Nächster fachlicher Schritt:** Phase 6.5 – Transactions, Concurrency & Idempotency

Die alte Datei „Woche 1 – M0 Fundament“ war eine Implementierungsplanung aus dem Stand 05.09.2026. Seitdem wurden Requirements, Scope, Research, Systemanalyse und UX/UI abgeschlossen bzw. weitergeführt.

**Aktuell wird noch keine Feature-Implementierung gestartet.**

## Ziel dieses Abschnitts

Eine Architekturbaseline erstellen, die den freigegebenen MVP technisch schneidet und anschließend einen sicheren Start der Implementierung ermöglicht.

## Abgeschlossene Architekturteilphasen

- Phase 6.1 – Architecture Goals & Quality Attributes: FINAL / RE-APPROVED
- Phase 6.2 – System Context & Container View: FINAL / RE-APPROVED
- Phase 6.3 v1.2.1 – Backend Building Blocks: FINAL / RE-APPROVED – Review Patch
- Phase 6.4 v1.0.1 – Module Dependencies & Public Contracts: FINAL / APPROVED – Review Patch

## Bestehende Architektur-Arbeitspakete

### A6-01 — Architekturziele & Qualitätsattribute
FERTIG.

### A6-02 — Systemkontext & Bausteine
FERTIG.

### A6-03 — Domain- und Modulgrenzen
FERTIG.

### A6-03B — Dependencies & Public Contracts
FERTIG.

### A6-04 — Daten- und Konsistenzmodell
Noch GEPLANT:
- Company / Project / Month
- Tenant Ownership
- monatsbezogene Mitarbeiterzuordnung
- Draft / Published
- DB-Constraints

### A6-05 — API & Authorization
Noch GEPLANT:
- serverseitiges RBAC
- Tenant Isolation
- Employee sieht nur eigene Ressourcen
- Admin-Rechte
- stabile Error Codes / Domain Errors

### A6-06 — Transactions / Concurrency / Idempotency
**NÄCHSTER SCHRITT**:
- atomare Ersatz-Planänderung
- Optimistic Locking
- Idempotenz
- Duplicate Protection
- Race Conditions
- Audit-Transaktionsverhalten

### A6-07 — ADR Pack + Architecture Review
Danach:
- Technologiestack / Repository-Struktur
- AuthN/AuthZ
- Modulgrenzen / Modularer Monolith
- Persistenz / ORM / Migrationen
- Concurrency / Optimistic Locking
- Transaktionsgrenzen
- API-/Error-Contract
- Deployment-/CI-Baseline
- Multi-Tenancy / Tenant Data Isolation

## Definition of Done Phase 6

- Architekturziele priorisiert
- Kontext- und Bausteinsicht vorhanden
- Domain-/Modulgrenzen begründet
- Dependencies/Public Contracts geklärt
- Datenverantwortung und zentrale Invarianten beschrieben
- Security-/Authorization-/Tenant-Isolation-Strategie beschrieben
- Transaktions-/Concurrency-Risiken geklärt
- ADR-Entwürfe mit Alternativen/Trade-offs vorhanden
- Architektur-Review durchgeführt
- **Human Approval vor Implementierungsstart**

## Explizit nicht Teil dieses Abschnitts

- Employee Mobile UI implementieren
- Backend-Features bauen
- DB-Schema final migrieren
- Auth programmieren
- CI/CD produktiv einrichten

Diese Punkte folgen nach dem Architektur-Gate in der Implementierungssequenz.
