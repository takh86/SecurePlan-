# Phase 6.3 – Backend Building Blocks

**Version:** v1.2  
**Status:** FINAL / RE-APPROVED

1. Platform & Tenant Management – Company/Tenant Lifecycle, Onboarding, Status, initiales Admin-Provisioning.
2. Identity & Access – Accounts, Credentials, Sessions, Rollen.
3. Workforce & Projects – Employee, Project, MonthlyProjectAssignment, Shift Config, Eligibility.
4. Planning – MonthlyPlan, Draft/Published, Publish/Re-Publish, Version, Planmutationen.
5. Absage & Ersatz – Request, Need, Offer, Decision.
6. Audit – Audit Records, keine Business Decisions.

Read Capabilities: Employee Statistics aus Planning; Admin Work Queue aus Absage/Ersatz.

Cross-cutting: TenantContext, Logging, Configuration, Persistence.

Design: Business Capabilities statt Screens/Tabellen · High Cohesion · Low Coupling · keine direkten fremden Repositories/Entities · Tenant Isolation als Querschnittsregel.
