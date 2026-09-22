# Effective MVP Baseline

**Stand:** 22.09.2026  
**Basis:** Phase 2 v1.1 + Phase 3 v1.1 + Phase 3.5 Impact Review + CR-01 / Baseline Amendment v1.2 + CR-02 v1.1 + Phase 4 FINAL v1.2 (CL-04-01/02).

Dieses Dokument ist die repo-lokale, umsetzungsorientierte Konsolidierung. Es ersetzt nicht die historischen Originalartefakte. Genehmigte CRs überschreiben widersprechende ältere Stellen; Phase-4-Clarifications schließen Traceability-Lücken, ohne neue Verticals einzuführen.

## MUST – Praktikums-MVP Monate 1–3

### M1 – Foundation
- reproduzierbare Projektbasis
- PostgreSQL + Migrationen
- lokale Docker-basierte Umgebung
- strukturierte Backend-/Frontend-Basis
- Build/Lint/Test in CI
- tenant-aware technische Basis, operativ zunächst eine Company

### M2 – Auth & RBAC
- Login/Logout und initiale Aktivierung/Passwortsetzung in pragmatischer Form
- sichere Passwortspeicherung
- Mitarbeiter vs. Büro/Admin
- serverseitige Authorization
- persönliche Accounts, keine Shared Accounts
- Tenant-Nutzerkonto gehört genau einer Company
- TenantContext wird serverseitig aus der authentifizierten Identität abgeleitet
- clientseitig gelieferte Company-IDs sind keine Trust Source

Relevante Phase-2-IDs: BR-AUTH-01, SEC-AUTHZ-01, SEC-AUTHZ-02, SEC-EMAIL-01, SEC-SESSION-01, FR-ACT-01.  
Ergänzende normative Präzisierung: CR-02 v1.1.

### M3 – Mitarbeiter & Projekte
- Mitarbeiter anlegen/bearbeiten/deaktivieren
- Mitarbeiter-ID, E-Mail, Schicht-Eignung
- Projekt-Grunddaten
- monatsbezogene Projektzuordnung
- Mitarbeiter grundsätzlich genau ein Projekt je Kalendermonat
- Projektwechsel zum Monatswechsel; Historie bleibt nachvollziehbar
- minimale administrative KRANK/URLAUB-Verfügbarkeit, soweit für Ersatz-Eligibility erforderlich
- KRANK speichert nur Datum/Zeitraum + Status; keine Diagnose/Symptome/medizinischen Freitexte
- projektbezogene Schichtarten und Start-/Endzeiten

Relevante IDs: FR-EMP-01..03, BR-EMP-01..07, BR-AUD-EMP-01, FR-PROJ-01, BR-PROJ-01..05.  
Traceability-Clarifications: Phase 4 v1.2, CL-04-01 und CL-04-02.

### M4 – Monatsplan
- Projekt + Kalendermonat
- einfache manuelle Erfassung/Pflege zuerst
- Draft/Published
- Publish + Revalidation
- Mitarbeiter sieht ausschließlich den eigenen aktuellen veröffentlichten Stand
- notwendige Planänderungen innerhalb SecurePlan

Relevante IDs: FR-MP-05..09, BR-MP-04..08.  
FR-MP-01..04 (Excel-Import) bleiben Produktanforderungen, sind im Praktikum jedoch SHOULD/Stretch.

### M5 – Absage & Ersatz
- Mitarbeiter beantragt Absage für eigenen geplanten Dienst
- gültige Absage erzeugt offenen Ersatzbedarf
- geeignete Mitarbeiter sehen Ersatzmöglichkeit und können Angebot abgeben
- Büro/Admin prüft Absage, Dienst und Angebote zusammen
- genau ein geeigneter Ersatz kann gewählt werden
- Planänderung bei Genehmigung atomar
- Genehmigung ohne Ersatzangebot bleibt möglich
- GEGENSTANDSLOS bei relevanter veröffentlichter Planänderung
- Idempotenz und serverseitige Eligibility
- Eligibility berücksichtigt u. a. Projektzuordnung, Schicht-Eignung sowie KRANK/genehmigten URLAUB im relevanten Zeitraum

Relevante IDs: FR-AB-01..03, BR-AB-01..05, BR-ER-00..07, BR-ER-10..11, FR-ER-00..04, FR-NOT-06.

**CR-01:** BR-ER-08 entfällt; quota-bezogener Teil von BR-ER-09 entfällt; AC-ER-04 entfällt. Es gibt **keine feste Obergrenze von drei Ersatzübernahmen**.

### M6 – Planbasierte Statistik
- eigene geplante Arbeitstage
- TAG/NACHT-Zählung für den Monat
- Grundlage ist der aktuelle veröffentlichte Plan

### M7 – Admin Work Queue
- einfache Übersicht offener Absage-/Ersatzentscheidungen
- direkte Navigation zum konkreten Fall
- kein umfangreiches KPI-Dashboard als MVP-Pflicht

### M8 – Qualitätsminimum
- DTO-/Input-Validation
- konsistentes Error Handling
- Audit-Minimum für kritische MVP-Aktionen
- Unit-, Integration- und API-Tests für Kernregeln
- Autorisierungs-Negativtests
- Cross-Tenant-Negativtests
- OpenAPI
- CI für Build/Lint/Test
- Datenintegrität über DB-Constraints und Transaktionen

### M9 – Demo Delivery
- Docker-basierter Build
- dokumentiertes Setup
- Environment-/Secrets-Trennung
- erreichbares Demo-/Staging-Deployment
- HTTPS bei externer Bereitstellung

## SHOULD / Stretch

Nur nach stabilem MUST-Core:
- standardisierter Excel-Import mit Preview/Validation
- Wunschfrei
- Schichttausch
- In-App-Notifications
- ausgewählte E-Mail-Notifications
- MFA für Büro/Admin, falls zeitlich tragfähig; spätestens Production-Must
- erweiterte Suche/Filter
- Basis-Health/Error Tracking

## Monate 4–6 – freigegebene Product Expansion gemäß CR-02

- mehrere voneinander isolierte Companies/Tenants
- minimaler providerseitiger Platform-/Tenant-Admin
- providerseitiges Company/Tenant-Onboarding
- Company-Statusverwaltung
- initiales Company-Admin-Provisioning
- tenant-scoped Accounts, Mitarbeiter, Projekte und Business-Daten

Diese Aktivierung erweitert **nicht** den eingefrorenen 3-Monats-Praktikums-MVP.

## Post-Praktikum / COULD

- Tagesplan inkl. Arbeitspositionen und Druckansicht
- Lohnabrechnungen
- vollständige Notification-Matrix
- vollständiger Audit-Viewer
- erweitertes Dashboard
- automatisiertes Offboarding
- Retention-Automation
- Production-Observability/Backup/RPO/RTO
- weitere Product Verticals

## WON'T NOW

- Native Mobile Apps
- Microservices
- Redis/Queues ohne konkreten Bedarf
- KI-basierte automatische Dienstplanung
- GPS/Check-in/Ist-Zeiterfassung
- Payroll-/Steuerberechnung
- SaaS Billing / Subscription Automation
- vollständiges Self-Service-Tenant-Onboarding
- Advanced BI
- WhatsApp-Integration

## MVP Demo Flow

Admin → Mitarbeiter/Projekt → Monatsplan → Publish → Mitarbeiteransicht → Absage → Ersatzangebot → Büroentscheidung → atomar aktualisierter Plan → Statistik.

Security, Authorization, Tenant Isolation, Datenintegrität und Tests werden bei Zeitdruck **nicht** gestrichen.
