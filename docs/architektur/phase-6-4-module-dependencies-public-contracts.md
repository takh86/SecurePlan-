# Phase 6.4 – Module Dependencies & Public Contracts

**Version:** v1.0  
**Status:** FINAL / APPROVED – PASS FOR PHASE 6.5

## Rules
1. No cross-module repository access.
2. No cross-module table mutation.
3. Dependencies are unidirectional where possible; circular dependencies are prohibited.
4. Cross-module collaboration happens through explicit public application contracts.

## Dependencies
- Platform & Tenant Management → Identity & Access
- Workforce & Projects → Identity & Access
- Planning → Workforce & Projects
- Absage & Ersatz → Planning
- Absage & Ersatz → Workforce & Projects
- Business Modules → Audit
- Statistics → Planning (read-only)
- Work Queue → Absage & Ersatz (read-only)

TenantContext ist kein Business-Modul. companyId wird serverseitig aus dem authentifizierten Account abgeleitet. Client-Company-ID ist keine Trust Source.

Employee Offboarding: Workforce → Identity.  
Company Suspension: Tenant Management besitzt Status; konkrete Sperrmechanik folgt im Security/Auth-Design.

Auf 6.5 verschoben: Transaction Boundaries, Commit/Rollback, Optimistic Locking, Idempotency, Audit-Transaktionsverhalten.
