# Phase 6.3 – Backend Building Blocks

**Version:** v1.2  
**Stand:** 22.09.2026  
**Status:** FINAL / RE-APPROVED  
**Repo-Hinweis:** Kurzfassung des freigegebenen Projektartefakts; ersetzt nicht das ausführliche Originalartefakt.

## Designprinzipien

- Business Capabilities statt Screens/Tabellen
- High Cohesion, Low Coupling
- keine direkten fremden Repositories/Entities
- Tenant Isolation als Querschnittsregel
- Control Plane und Tenant Application Plane logisch getrennt

## Finale Building Blocks

### 1. Platform & Tenant Management
Besitzt:
- Company/Tenant Lifecycle
- providerseitiges Onboarding
- Company/Tenant Status
- initiales Company-Admin-Provisioning als orchestrierter Flow

### 2. Identity & Access
Besitzt:
- Account
- Credentials
- Sessions
- Rollen / Security Identity

### 3. Workforce & Projects
Besitzt:
- Employee
- Project
- MonthlyProjectAssignment
- Project Shift Configuration
- eligibility-relevante Stammdaten: aktive Beschäftigung, Projektzuordnung, Schicht-Eignung und minimale KRANK/URLAUB-Verfügbarkeit

### 4. Planning
Besitzt:
- MonthlyPlan
- Plan Entries
- Draft / Published
- Publish / Re-Publish
- Plan Version / Optimistic Lock Boundary
- Planmutationen

### 5. Absage & Ersatz
Besitzt:
- CancellationRequest
- ReplacementNeed
- ReplacementOffer
- ReplacementDecision

**Verantwortung:** Absage & Ersatz bewertet die Replacement Eligibility serverseitig über öffentliche Contracts zu Workforce & Projects und Planning. Workforce besitzt die dafür benötigten Stammdaten, nicht die fachliche Ersatzentscheidung.

### 6. Audit
Besitzt:
- Audit Records
- keine Business Decisions

## Read Capabilities

Keine eigenen Domain-Module:
- Employee Statistics → aus Planning
- Admin Work Queue → aus Absage & Ersatz

## Cross-cutting

- TenantContext
- Logging
- Configuration
- Persistence

## Bewusst kein eigenes Modul

- vollständige Notifications
- Billing / Subscription
- Employee Statistics als Domain
- Admin Work Queue als Domain
- TenantContext als Domain
