# Phase 6.1 – Architecture Goals & Quality Attributes

**Version:** v1.2  
**Status:** FINAL / RE-APPROVED

## P1
serverseitige Authorization · Cross-Tenant Isolation · DB-Constraints + Domain Validation · Published Plan Source of Truth · atomare Ersatz-Planänderung · Optimistic Concurrency · Idempotenz · explizite State Transitions · negative Authorization-/Business-Rule-Tests.

## P2
stabile Error Contracts · Auditability · klare Modulgrenzen · reproduzierbare Migrationen/Builds/CI/Deployment.

## P3
tenant-aware von Beginn an · effiziente Read Paths · Performance ohne premature scaling.

## Constraints
Modular Monolith · PostgreSQL · REST · Responsive Web · Docker lokal · Account genau eine Company · Platform Admin separater Scope · Shared DB + Shared Schema · keine Microservices/Queues/Redis ohne konkreten Treiber.
