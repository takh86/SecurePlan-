# Phase 5.2 – Information Architecture Amendment v1.2

**Version:** v1.2  
**Stand:** 22.09.2026  
**Basis:** CR-02  
**Status:** FINAL / APPROVED  
**Repo-Hinweis:** Kurzfassung des genehmigten Amendments; Phase 5.2 FINAL bleibt gültig, soweit dieses Amendment nichts ersetzt.

## Ersetzte Annahme

Entfällt:
- Future Company Switcher
- Membership-Modell über mehrere Companies pro Benutzerkonto

## Neuer globaler Kontext

Für Company Admin und Mitarbeiter gilt:

SecurePlan → Company-Kontext des authentifizierten Accounts → rollenbezogene Navigation → Seiten-/Bereichskontext → Konto/Abmelden.

Ein Tenant-Nutzerkonto gehört genau einer Company.

## Provider-Administration

Platform-/Tenant-Onboarding gehört zum providerseitigen Control Plane und nicht zur normalen Company-Admin-/Mitarbeiter-IA des 3-Monats-MVP.

Die bestehenden Tenant-UX-Flows bleiben deshalb unverändert.
