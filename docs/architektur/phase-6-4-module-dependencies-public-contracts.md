# Phase 6.4 – Module Dependencies & Public Contracts

**Version:** v1.0.1  
**Stand:** 22.09.2026  
**Status:** FINAL / APPROVED – Review Patch – PASS FOR PHASE 6.5  
**Repo-Hinweis:** Kurzfassung des freigegebenen Projektartefakts; ersetzt nicht das ausführliche Originalartefakt.

> **Review-Patch v1.0.1:** Präzisiert nur bereits geltende No-Cycle-Guardrails für Company Suspension und GEGENSTANDSLOS. Keine neue Dependency und keine neue Modulgrenze wurde eingeführt. Human Approval wird mit dem Merge von PR #3 dokumentiert.

## Leitprinzip

Ein Modul darf ein anderes Modul benutzen, aber nur über dessen öffentlichen Application Contract – niemals über interne Repositories, Entities oder Tabellen.

## Verbindliche Architecture Rules

1. **No cross-module repository access.**
2. **No cross-module table mutation.**
3. **Dependencies are unidirectional where possible; circular dependencies are prohibited.**
4. **Cross-module collaboration happens through explicit public application contracts.**

## Dependency Matrix

| From | To | Zweck | Zugriff |
|---|---|---|---|
| Platform & Tenant Management | Identity & Access | initialer Company Admin / Account Lifecycle | Public Contract |
| Workforce & Projects | Identity & Access | Employee Account / Offboarding | Public Contract |
| Planning | Workforce & Projects | Assignment / eligibility-relevante Stammdaten | Public Contract |
| Absage & Ersatz | Planning | Published Plan + Planmutation | Public Contract |
| Absage & Ersatz | Workforce & Projects | Replacement Eligibility Inputs | Public Contract |
| alle auditpflichtigen Module inkl. Platform & Tenant Management | Audit | fachliches / administratives Audit | Audit Contract |
| Employee Statistics | Planning | planbasierte Reads | Read-only Contract |
| Admin Work Queue | Absage & Ersatz | offene Vorgänge | Read-only Contract |

## Konzeptionelle Public Contracts

Beispiele, noch keine finalen Methodensignaturen:
- Identity & Access: provisionAccount, deactivateAccount, invalidateSessions
- Workforce & Projects: validateAssignment, getEligibilityData
- Planning: getPublishedDuty, replaceEmployeeInDuty, publishPlan
- Absage & Ersatz: getOpenCases, getCaseDetails
- Audit: recordBusinessAction

## Tenant Context

TenantContext ist kein Business-Modul.

- companyId wird serverseitig aus dem authentifizierten Account abgeleitet
- Client-Company-ID ist keine Trust Source
- Cross-Company Reads/Writes sind verboten
- Tenant Queries/Mutationen laufen immer im Tenant Context

## Kritische Lifecycle-Checks

### Employee Offboarding
Workforce & Projects → Identity & Access: Zugriff deaktivieren / Sessions invalidieren. Keine Rückabhängigkeit von Identity auf Workforce-Repositories.

### Company Suspension
Platform & Tenant Management besitzt Tenant-Status. Die Sperrmechanik darf **keine Identity & Access → Platform & Tenant Management-Abhängigkeit** erzeugen. Der konkrete Mechanismus wird in **Phase 6.5 bzw. SP-A06-05 (Security / RBAC / API Contracts)** festgelegt.

## Explizit auf die nächsten Architekturentscheidungen verschoben

- konkrete Transaction Boundaries
- Commit/Rollback über Modulgrenzen
- Optimistic Locking
- Idempotency / Duplicate Protection
- Audit innerhalb/außerhalb kritischer Transaktionen
- Mechanismus für GEGENSTANDSLOS nach relevanter Planänderung **ohne Planning → Absage & Ersatz-Zyklus**, z. B. Revalidation gegen Planversion oder internes Domain Event
