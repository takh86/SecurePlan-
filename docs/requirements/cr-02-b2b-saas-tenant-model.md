# CR-02 – B2B-SaaS-Tenant-Modell

**Version:** v1.1  
**Status:** FINAL / APPROVED

## Entscheidung
SecurePlan wird als B2B-SaaS für isolierte Sicherheitsunternehmen geplant.

- Kundenunternehmen = Company = Tenant.
- Tenant-Nutzerkonto gehört genau einer Company.
- Kein Cross-Company-Membership-Modell, kein Company Switcher.
- Platform Admin verwaltet Companies im Provider-Scope.
- Company Admin verwaltet nur die eigene Company.

## Roadmap
**Monate 1–3:** Praktikums-MVP, operativ eine Company, technisch tenant-aware.  
**Monate 4–6:** Multi-Company-Aktivierung, providerseitiges Tenant-Onboarding, minimaler Platform Admin, Company-Status, initiales Company-Admin-Provisioning.

Nicht freigegeben: Billing/Subscriptions, vollständiges Self-Service-Onboarding, Cross-Company-Memberships.

## Phase-3-Korrektur
Die Sammelaussage „Subscription/Billing/Platform-Admin = WON'T NOW“ wird differenziert:
- minimaler Platform-/Tenant-Admin: Monate 4–6 freigegeben
- Billing/Subscription: weiterhin WON'T NOW
- Full Self-Service-Onboarding: weiterhin WON'T NOW
- 3-Monats-MVP unverändert

## Security
TenantContext serverseitig · Client-Company-ID keine Trust Source · Cross-Company Reads/Writes verboten · Negativtests verpflichtend · Platform Admin kein implizites Recht auf operative Tenant-Daten.
