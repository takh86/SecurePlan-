# SecurePlan

Praxisphasenprojekt an der THM: fokussierte, rollenbasierte Personaleinsatzplanung für Sicherheitsunternehmen.

> **Stand 22.09.2026**  
> **Aktueller formaler Schritt: Phase 6.5 – Transactions, Concurrency & Idempotency.**  
> Phase 6.1–6.4 sind dokumentiert und freigegeben. Es existiert weiterhin **kein nachgewiesener Produktions-Anwendungscode**.

## Status

| Bereich | Status |
|---|---|
| Phase 2 | FINAL / APPROVED / FROZEN |
| Phase 3 | FINAL / APPROVED / FROZEN |
| Phase 3.5 | FINAL / APPROVED |
| CR-01 | FINAL / APPROVED |
| CR-02 v1.1 | FINAL / APPROVED |
| Phase 4 v1.2 | FINAL / APPROVED |
| Phase 5 | PASS FOR PHASE 6 |
| Phase 6.1 | FINAL / RE-APPROVED |
| Phase 6.2 | FINAL / RE-APPROVED |
| Phase 6.3 | FINAL / RE-APPROVED |
| Phase 6.4 | FINAL / APPROVED |
| Implementierung | NOCH NICHT BEGONNEN / NICHT NACHGEWIESEN |

Details: [docs/project-status.md](docs/project-status.md)

## SaaS-Modell
- SecurePlan = B2B-SaaS.
- Company = Tenant.
- Ein Tenant-Account gehört genau einer Company.
- Kein Company Switcher / keine Cross-Company-Membership.
- Platform Admin ist separater Provider-Scope.
- Monate 1–3: Praktikums-MVP.
- Monate 4–6: Multi-Company/Productization.
- Billing/Subscriptions und vollständiges Self-Service-Onboarding bleiben out.

## Dokumentation
- [Requirements](docs/requirements/)
- [Systemanalyse](docs/systemanalyse/)
- [UX/UI](docs/ux-ui/)
- [Architektur](docs/architektur/)
- [Planung](docs/planung/)

**Keine Feature-Implementierung vor vollständigem Architektur-Gate.**
