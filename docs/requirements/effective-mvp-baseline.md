# Effective MVP Baseline

**Stand:** 22.09.2026  
**Basis:** Phase 2 v1.1 + Phase 3 v1.1 + Phase 3.5 + CR-01 + CR-02.

## Monate 1–3 MUST
Foundation · Auth/RBAC · Mitarbeiter/Projekte · manueller Monatsplan + Publish · Mitarbeiteransicht · Absage/Ersatz · Statistik · Work Queue · Quality Minimum · Demo Delivery.

Zusätzlich tenant-aware Basis:
- TenantContext serverseitig
- Account genau eine Company
- Cross-Tenant-Negativtests
- minimale KRANK/URLAUB-Verfügbarkeit für Eligibility
- projektbezogene Schichtkonfiguration

CR-01: kein 3er-Ersatzlimit.

## SHOULD
Excel-Import · Wunschfrei · Schichttausch · ausgewählte Notifications · MFA wenn Core stabil · Suche/Filter · Basis-Health/Error Tracking.

## Monate 4–6 gemäß CR-02
mehrere isolierte Companies · minimaler providerseitiger Platform/Tenant Admin · Company-Onboarding/Status · initiales Company-Admin-Provisioning.

## WON'T NOW
Native Mobile · Microservices · Redis/Queues ohne Bedarf · KI-Autoplanung · GPS/Ist-Zeiterfassung · Payroll/Steuer · Billing/Subscriptions · Full Self-Service-Tenant-Onboarding · Advanced BI · WhatsApp.
