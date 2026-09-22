# Phase 6.2 – System Context & Container View

**Version:** v1.1  
**Stand:** 22.09.2026  
**Status:** FINAL / RE-APPROVED  
**Repo-Hinweis:** Kurzfassung des freigegebenen Projektartefakts; ersetzt nicht das ausführliche Originalartefakt.

## System Context

SecurePlan ist B2B-SaaS. Akteure:
- Platform Admin / SecurePlan Betreiber
- Company Admin / Büro
- Mitarbeiter

## Control Plane vs. Application Plane

**Control Plane:** Company/Tenant anlegen, Status verwalten, initialen Company Admin provisionieren.

**Application Plane:** Mitarbeiter, Projekte, Monatsplan, Absage/Ersatz, Admin Work Queue, Employee Statistics.

Die Trennung ist logisch/modular; kein separates Microservice-Deployment im 6-Monats-Projekt.

## Container View

Responsive Web Client → REST/HTTPS → Backend API (tenant-aware Modular Monolith) → PostgreSQL.

## Tenant Rules

- Company = Tenant
- Account gehört genau einer Company
- kein Company Switcher
- TenantContext serverseitig aus Auth Identity
- Company Admin sieht nur eigene Company
- Platform Admin besitzt kein implizites Recht auf operative Tenant-Daten

## Datenisolation

Startstrategie: Shared Database + Shared Schema + explizite Company Ownership.

Database-per-Tenant bleibt spätere Option bei realen Compliance-/Enterprise-Treibern.
