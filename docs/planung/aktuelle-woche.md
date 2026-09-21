# Aktueller Arbeitsabschnitt — Phase 6: Software Architecture & System Design

**Stand:** 21.09.2026  
**Status:** IN ARBEIT / PRE-IMPLEMENTATION

Die alte Datei „Woche 1 – M0 Fundament“ war eine Implementierungsplanung aus dem Stand 05.09.2026. Seitdem wurden Requirements, Scope, Research, Systemanalyse und Phase-5-UX/UI-Artefakte außerhalb des damaligen Repository-Standes fertiggestellt bzw. weitergeführt.

**Aktuell wird noch keine Feature-Implementierung gestartet.**

## Ziel dieses Abschnitts

Eine Architekturbaseline erstellen, die den freigegebenen MVP technisch schneidet und anschließend einen sicheren Start der Implementierung ermöglicht.

## Arbeitspakete

### A6-01 — Architekturziele & Qualitätsattribute
- relevante NFR-/Security-Ziele für den Praktikums-MVP priorisieren
- Demo/Staging vs. spätere Production-Gates trennen
- Overengineering vermeiden

### A6-02 — Systemkontext & Bausteine
- Systemgrenze
- Client / Backend / PostgreSQL / externe E-Mail- oder Deployment-Abhängigkeiten nur soweit MVP-relevant
- Verantwortlichkeiten pro Baustein

### A6-03 — Domain- und Modulgrenzen
Mindestens prüfen:
- Identity / Access
- Employees
- Projects / Monthly Assignment
- Monthly Planning
- Cancellation / Replacement
- Work Queue
- Statistics
- Audit / Shared Infrastructure

### A6-04 — Daten- und Konsistenzmodell
- Company / Project / Month
- monatsbezogene Mitarbeiterzuordnung
- Draft / Published
- atomare Ersatz-Planänderung
- Optimistic Locking
- Idempotenz
- DB-Constraints

### A6-05 — API & Authorization
- serverseitiges RBAC
- Employee sieht nur eigene Ressourcen
- Admin-Rechte
- stabile Error Codes / Domain Errors
- Employee Mobile UX mit möglichst wenigen Roundtrips, ohne Datenüberfreigabe

### A6-06 — ADR-Kandidaten
ADR-Vorschläge vorbereiten, aber nicht ohne menschliche Entscheidung finalisieren:
- Technologiestack / Repository-Struktur
- AuthN/AuthZ
- Modulgrenzen / Modularer Monolith
- Persistenz / ORM / Migrationen
- Concurrency / Optimistic Locking
- Transaktionsgrenzen im Absage-/Ersatzflow
- API-/Error-Contract
- Deployment-/CI-Baseline

## Definition of Done Phase 6

- Architekturziele priorisiert
- Kontext- und Bausteinsicht vorhanden
- Domain-/Modulgrenzen begründet
- Datenverantwortung und zentrale Invarianten beschrieben
- Security-/Authorization-Strategie beschrieben
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
