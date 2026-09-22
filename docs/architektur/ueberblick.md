# Architekturüberblick – Phase 6

**Stand:** 22.09.2026  
**Status:** Phase 6.1–6.4 FINAL / APPROVED; Phase 6.5 NEXT

## Freigegebene Dokumente

- [Phase 6.1 – Architecture Goals](phase-6-1-architecture-goals.md)
- [Phase 6.2 – System Context & Container View](phase-6-2-system-context-container.md)
- [Phase 6.3 – Backend Building Blocks](phase-6-3-backend-building-blocks.md)
- [Phase 6.4 – Module Dependencies & Public Contracts](phase-6-4-module-dependencies-public-contracts.md)
- [Backward Consistency Gate](backward-consistency-gate-2026-09-22.md)
- [ADR-Vorlage](adr/0000-vorlage.md)

## 1. Systemkontext

SecurePlan ist B2B-SaaS. Company = Tenant. Tenant-Benutzerkonto gehört genau einer Company. Platform Admin ist separater Provider-Scope.

## 2. 6-Monats-Horizont

- Monate 1–3: fokussierter Praktikums-MVP mit operativ einer Company
- Monate 4–6: Multi-Company-Aktivierung mit minimalem providerseitigem Tenant Management
- Billing/Subscriptions und vollständiges Self-Service-Onboarding bleiben WON'T NOW

## 3. Container View

Responsive Web Client → REST Backend (tenant-aware Modular Monolith) → PostgreSQL.

Shared Database + Shared Schema ist die bevorzugte Startstrategie. Database-per-Tenant bleibt spätere Option bei konkreten Compliance-/Enterprise-Treibern.

## 4. Backend Building Blocks

1. Platform & Tenant Management
2. Identity & Access
3. Workforce & Projects
4. Planning
5. Absage & Ersatz
6. Audit

Read Capabilities:
- Employee Statistics
- Admin Work Queue

Cross-cutting:
- TenantContext
- Logging
- Configuration
- Persistence

## 5. Verbindliche Ownership

- Platform & Tenant Management besitzt Company/Tenant-Lifecycle.
- Identity & Access besitzt Accounts, Credentials, Sessions und Rollen.
- Workforce & Projects besitzt Employee, Project, MonthlyProjectAssignment, Shift Config und eligibility-relevante Stammdaten inkl. minimaler KRANK/URLAUB-Verfügbarkeit.
- Planning besitzt MonthlyPlan, Draft/Published und Planmutationen.
- Absage & Ersatz besitzt CancellationRequest, ReplacementNeed, ReplacementOffer und ReplacementDecision und bewertet Replacement Eligibility über Public Contracts.
- Audit besitzt Audit Records, nicht Business Decisions.

## 6. Modulregeln

1. No cross-module repository access.
2. No cross-module table mutation.
3. Dependencies are unidirectional where possible; circular dependencies are prohibited.
4. Cross-module collaboration happens through explicit public application contracts.

## 7. Wichtige Abhängigkeiten

- Platform & Tenant Management → Identity & Access
- Workforce & Projects → Identity & Access
- Planning → Workforce & Projects
- Absage & Ersatz → Planning
- Absage & Ersatz → Workforce & Projects
- alle auditpflichtigen Module inkl. Platform & Tenant Management → Audit
- Employee Statistics → Planning (read only)
- Admin Work Queue → Absage & Ersatz (read only)

## 8. Nächster Abschnitt – Phase 6.5

Zu entscheiden:
- Transaction Boundaries
- Commit/Rollback über Modulgrenzen
- Optimistic Locking
- Idempotency / Duplicate Protection
- Mechanismus für GEGENSTANDSLOS ohne Dependency-Zyklus
- Company-Suspension-Sperrmechanik ohne Identity → Platform-Zyklus
- Audit innerhalb/außerhalb kritischer Transaktionen

## 9. Stop Condition

Feature-Implementierung startet erst nach vollständigem Architekturreview und Human Approval.
