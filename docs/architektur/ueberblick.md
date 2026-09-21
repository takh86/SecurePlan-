# Architekturüberblick – Phase 6

**Stand:** 21.09.2026  
**Status:** **IN ARBEIT – Phase 6 Software Architecture & System Design**

Die Architektur ist nicht mehr durch „fehlende Phase 2/3“ blockiert. Requirements, Scope, CR-01, Systemanalyse und Phase-5-Handoff liefern ausreichend fachliche Grundlage für den Architekturstart.

**Wichtig:** Dieses Dokument beschreibt den Architekturarbeitsraum. Offene ADRs sind noch keine finalen technischen Entscheidungen.

## 1. Systemkontext

SecurePlan ist eine rollenbasierte Webanwendung für den Praktikums-MVP eines Sicherheitsunternehmens.

Primäre Nutzer:
- Büro/Admin
- Mitarbeiter

Spätere bzw. außerhalb des Praktikums-MVP liegende Bereiche:
- Tagesplan/Schichtleiter-Vertical
- Lohnabrechnungen
- vollständige Notification-Infrastruktur
- Multi-Company-Self-Service/Billing

## 2. Verbindliche fachliche Grenzen

Der Praktikums-MVP umfasst:
- Identity / Access
- Mitarbeiter
- Projekte + monatsbezogene Zuordnung
- Monatsplan + Draft/Published
- Employee Plan View
- Absage/Ersatz
- Work Queue
- planbasierte Statistik
- Audit-/Quality-Minimum

Nicht aus UI-Screens ableiten: Modulgrenzen müssen aus Verantwortlichkeiten, Invarianten und Transaktionen begründet werden.

## 3. Architekturtreiber

- serverseitige Authorization
- persönliche Daten nur im zulässigen Kontext
- Datenintegrität durch DB-Constraints und Transaktionen
- Optimistic Locking gegen Lost Updates
- atomare Ersatz-Planänderung
- Idempotenz für wiederholte Kernaktionen
- reproduzierbare Migrationen
- automatisierte Tests
- einfache lokale und Demo-/Staging-Betreibbarkeit
- spätere Company-Trennung ermöglichen, ohne Full-SaaS im MVP zu bauen

## 4. Phase-6-Fragen

### Company / Project / Month
Wie wird Company-Readiness modelliert, ohne Multi-Tenant-Overengineering?

### Assignment
Welche Entity/Relation bildet Employee + Project + Calendar Month und historische Zuordnung?

### Monthly Plan
Wie werden Draft, Published, Versionierung, Revalidation und Planänderungen modelliert?

### Cancellation / Replacement
Welche Aggregate/Services und Transaktionsgrenzen bilden Cancellation, ReplacementNeed und Offer?

### Authorization
Wie werden Admin und Employee serverseitig autorisiert und Datenzugriffe eingeschränkt?

### Work Queue
Welche Query-/Read-Model-Strategie liefert offene Vorgänge und Deep Links?

### Error Contract
Wie werden Domain Errors in stabile API-Fehlercodes und verständliche UI-Zustände übersetzt?

## 5. Technische Planungsannahmen aus Phase 3

Phase 3 nennt als konservative Planungsrichtung:
- Modularer Monolith
- PostgreSQL
- REST
- responsive Web-UI
- Docker-basierte lokale Umgebung

Diese Punkte werden in Phase 6 gegen Anforderungen und Alternativen geprüft und über ADRs begründet. Sie werden hier **nicht** als ungeprüfte Finalentscheidung deklariert.

## 6. ADR-Kandidaten

| ADR | Thema | Status |
|---|---|---|
| 0001 | Technologiestack / Repo-Struktur | VORSCHLAG – Entscheidung offen |
| 0002 | Authentifizierung & Autorisierung | VORSCHLAG – Entscheidung offen |
| 0003 | Modularer Monolith / Modulgrenzen | VORSCHLAG – Entscheidung offen |
| 0004 | Persistenz / Migrationen / DB-Constraints | VORSCHLAG – Entscheidung offen |
| 0005 | Concurrency / Optimistic Locking | VORSCHLAG – Entscheidung offen |
| 0006 | Absage-/Ersatz-Transaktionen & Idempotenz | VORSCHLAG – Entscheidung offen |
| 0007 | API-/Error-Contract | VORSCHLAG – Entscheidung offen |
| 0008 | CI/CD / Demo Deployment Baseline | VORSCHLAG – Entscheidung offen |

Vorlage: [adr/0000-vorlage.md](adr/0000-vorlage.md)

## 7. Stop Condition

Phase 6 endet mit einem Architekturreview und menschlicher Freigabe. Erst danach startet die Feature-Implementierung.
