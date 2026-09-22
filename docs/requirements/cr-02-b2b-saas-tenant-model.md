# CR-02 – B2B-SaaS-Tenant-Modell

**Version:** v1.1  
**Stand:** 22.09.2026  
**Status:** FINAL / APPROVED  
**Repo-Hinweis:** Repo-Kurzfassung des genehmigten Change Requests; das ausführliche Originalartefakt bleibt Detailreferenz.

## Entscheidung

SecurePlan wird als B2B-SaaS-Dienst für mehrere voneinander isolierte Sicherheitsunternehmen geplant.

- Ein Kundenunternehmen entspricht genau einer **Company / einem Tenant**.
- Tenant-Nutzer besitzen persönliche Accounts.
- Ein Tenant-Benutzerkonto gehört genau **einer** Company.
- Es gibt kein Membership-Modell über mehrere Companies und keinen Company Switcher.
- Der SecurePlan-Betreiber verwaltet Companies im Provider-/Platform-Scope.
- Company Admins verwalten ausschließlich die eigene Company.

## 6-Monats-Roadmap

### Monate 1–3
Der eingefrorene Praktikums-MVP bleibt unverändert und operativ auf eine Company fokussiert. Die Architektur ist tenant-aware.

### Monate 4–6
Freigegeben:
- Multi-Company-Aktivierung
- providerseitiges Company/Tenant-Onboarding
- minimaler Platform Admin
- Company-Statusverwaltung
- initiales Company-Admin-Provisioning

Nicht freigegeben:
- Billing/Subscriptions
- vollständiges Self-Service-Onboarding
- Cross-Company-Memberships

## Korrektur zu Phase 3

Die frühere Sammelaussage „Subscription/Billing/Platform-Admin für SaaS = WON'T NOW“ wird differenziert:

- **Minimaler providerseitiger Platform-/Tenant-Admin:** für Monate 4–6 freigegeben.
- **Subscription/Billing:** bleibt WON'T NOW.
- **Vollständiges Self-Service-Onboarding:** bleibt WON'T NOW.
- **3-Monats-Praktikums-MVP:** unverändert.

## Sicherheits- und Isolationregeln

- TenantContext wird serverseitig aus der authentifizierten Identität abgeleitet.
- Clientseitige Company-Parameter sind keine Trust Source.
- Cross-Company Reads/Writes sind verboten.
- Cross-Tenant-Zugriffe müssen negativ getestet werden.
- Platform Admin besitzt kein implizites Recht zum Lesen operativer Tenant-Daten.

## Auswirkungen

CR-02 präzisiert:
- Phase 3 – Scope nach Monat 3
- Phase 5.2 – kein Company Switcher
- Phase 6 – Tenant- und Modularchitektur

CR-01 bleibt unverändert wirksam.
