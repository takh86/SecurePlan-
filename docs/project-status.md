# SecurePlan – Project Status

**Stand:** 22.09.2026  
**Zweck:** Ein eindeutiger Einstiegspunkt für Menschen und Coding Agents.

## 1. Aktueller Gate-Stand

| Phase | Zustand | Bemerkung |
|---|---|---|
| Phase 2 – Requirements Engineering | FINAL / APPROVED / BASELINE FROZEN | Produktanforderungen |
| Phase 3 – Scope & MVP | FINAL / APPROVED / SCOPE FROZEN | verbindlicher 3-Monats-Praktikumsumfang |
| Phase 3.5 – Product Research & Validation | FINAL / APPROVED | Research ändert Frozen Baselines nur über CR |
| CR-01 / Baseline Amendment v1.2 | FINAL / APPROVED | 3er-Ersatzlimit entfernt |
| CR-02 – B2B-SaaS-Tenant-Modell v1.1 | FINAL / APPROVED | Company = Tenant; Monate 4–6 Multi-Company/Productization |
| Phase 4 – Systemanalyse v1.2 | FINAL / APPROVED | 17 Use Cases + CL-04-01/02 |
| Phase 5.1–5.8 | DOCUMENTED / PASS gemäß Teil-Gates | UX Requirements bis Critical Prototype |
| Phase 5.9 | CONDITIONAL PASS | interner Review abgeschlossen; reale Zielgruppen-Sessions offen |
| Phase 5.10 | PASS FOR PHASE 6 | UX/UI-Baseline eingefroren; kontrollierte Follow-ups bleiben |
| Phase 6.1 | FINAL / RE-APPROVED | Architecture Goals & Quality Attributes |
| Phase 6.2 | FINAL / RE-APPROVED | System Context & Container View |
| Phase 6.3 v1.2.1 | FINAL / RE-APPROVED – Review Patch | Backend Building Blocks; Ownership-Präzisierung ohne Boundary-Änderung |
| Phase 6.4 v1.0.1 | FINAL / APPROVED – Review Patch | Module Dependencies & Public Contracts; No-Cycle-Präzisierung |
| Phase 6.5 | NEXT / GEPLANT | Transactions, Concurrency & Idempotency |
| Feature-Implementierung | NOT IMPLEMENTED / NOT EVIDENCED | startet erst nach vollständigem Architektur-Gate |

## 2. Verbindliches SaaS-/Tenant-Modell

- SecurePlan ist B2B-SaaS.
- Company = Tenant.
- Tenant-Nutzer besitzen persönliche Accounts und gehören genau einer Company.
- Kein Company Switcher / keine Cross-Company-Membership.
- Platform Admin ist Provider-Scope, nicht Company Admin.
- Platform Admin besitzt kein implizites Recht zum Lesen operativer Tenant-Daten.
- TenantContext wird serverseitig aus der Auth Identity abgeleitet; Client-Company-ID ist keine Trust Source.
- Cross-Company Reads/Writes sind verboten und müssen negativ getestet werden.
- Shared Database + Shared Schema ist die bevorzugte Startstrategie.
- Billing/Subscription-Automation und vollständiges Self-Service-Onboarding bleiben WON'T NOW.

## 3. Offene Follow-ups, die Phase 6 nicht blockieren

- reale formative Usability-Sessions mit Mitarbeiter- und Büro/Admin-Zielgruppen
- technische Keyboard-/Focus-/Accessibility-Verifikation in der späteren UI-Implementierung
- Monatsplan-Usability/Performance mit realistischem Full-Month-Datensatz
- High-Fidelity-Ausarbeitung gegen Phase-5-Baseline prüfen
- keine Wettbewerbsvorteilsbehauptung ohne empirische Evidenz

## 4. Was Phase 6 liefert

- Architekturziele und Qualitätsattribute
- Systemkontext und Container
- Domain-/Modulgrenzen und Ownership
- Module Dependencies / Public Contracts
- Daten- und Konsistenzmodell
- Transactions / Concurrency / Idempotency
- serverseitige Security / RBAC / Tenant Isolation
- API-/Error-Contracts
- ADR-Kandidaten und finales Architecture Review

**Guardrail:** Screens sind keine Datenbanktabellen. UI-Routen sind keine Domain-Grenzen.

## 5. Freigegebene Building Blocks

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

## 6. Keine falschen Implementierungsclaims

Phase-5-HTML-Prototypen sind **PROTOTYPED**, nicht **IMPLEMENTED**.

Solange im Repository kein Produktionscode mit Tests/Build/CI-Nachweis vorliegt, darf ein Feature nicht als implementiert geführt werden.

## 7. Wirksamer Scope und Dokumente

- [Effective MVP Baseline](requirements/effective-mvp-baseline.md)
- [Anforderungsindex](requirements/anforderungs-index.md)
- [CR-02](requirements/cr-02-b2b-saas-tenant-model.md)
- [Phase 4 FINAL v1.2](systemanalyse/phase-4-final-v1.2.md)
- [Phase 5 Baseline](ux-ui/phase-5-baseline.md)
- [Phase 5.2 Amendment](ux-ui/phase-5-2-amendment-cr-02.md)
- [Phase 6.1](architektur/phase-6-1-architecture-goals.md)
- [Phase 6.2](architektur/phase-6-2-system-context-container.md)
- [Phase 6.3](architektur/phase-6-3-backend-building-blocks.md)
- [Phase 6.4](architektur/phase-6-4-module-dependencies-public-contracts.md)
