# Architekturüberblick – Phase 6

**Stand:** 22.09.2026  
**Status:** Phase 6.1–6.4 FINAL / APPROVED; Phase 6.5 NEXT

## System
SecurePlan = B2B-SaaS. Company = Tenant. Account genau eine Company. Platform Admin = Provider-Scope.

## Horizont
Monate 1–3 Praktikums-MVP. Monate 4–6 Multi-Company/Productization. Billing/Subscriptions und Full Self-Service-Onboarding bleiben WON'T NOW.

## Container
Responsive Web Client → REST Backend (tenant-aware Modular Monolith) → PostgreSQL. Start: Shared DB + Shared Schema.

## Building Blocks
Platform & Tenant Management · Identity & Access · Workforce & Projects · Planning · Absage & Ersatz · Audit.

Read: Statistics, Admin Work Queue.  
Cross-cutting: TenantContext, Logging, Configuration, Persistence.

## Modulregeln
No cross-module repository access · No cross-module table mutation · keine Zyklen · explizite Public Contracts.

## Next
Phase 6.5: Transaction Boundaries · Commit/Rollback · Optimistic Locking · Idempotency · Duplicate Protection · Audit-Transaktionsverhalten.

Keine Feature-Implementierung vor vollständigem Architekturreview und Human Approval.
