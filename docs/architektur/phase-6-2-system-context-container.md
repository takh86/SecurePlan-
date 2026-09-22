# Phase 6.2 – System Context & Container View

**Version:** v1.1  
**Status:** FINAL / RE-APPROVED

Akteure: Platform Admin · Company Admin/Büro · Mitarbeiter.

**Control Plane:** Tenant anlegen, Status verwalten, initialen Company Admin provisionieren.  
**Application Plane:** Mitarbeiter, Projekte, Monatsplan, Absage/Ersatz, Work Queue, Statistik.

Container: Responsive Web Client → REST/HTTPS → tenant-aware Modular Monolith → PostgreSQL.

Tenant Rules: Company = Tenant · Account genau eine Company · kein Company Switcher · TenantContext serverseitig · Company Admin nur eigene Company · Platform Admin kein implizites Recht auf operative Tenant-Daten.

Isolation: Shared Database + Shared Schema + explizite Company Ownership. DB-per-Tenant bleibt spätere Option bei echten Treibern.
