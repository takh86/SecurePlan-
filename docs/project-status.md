# SecurePlan – Project Status

**Stand:** 21.09.2026  
**Zweck:** Ein eindeutiger Einstiegspunkt für Menschen und Coding Agents.

## 1. Aktueller Gate-Stand

| Phase | Zustand | Bemerkung |
|---|---|---|
| Phase 2 – Requirements Engineering | FINAL / APPROVED / BASELINE FROZEN | Produktanforderungen |
| Phase 3 – Scope & MVP | FINAL / APPROVED / SCOPE FROZEN | verbindlicher Praktikumsumfang |
| Phase 3.5 – Product Research & Validation | FINAL / APPROVED | Research ändert Frozen Baselines nur über CR |
| CR-01 / Baseline Amendment v1.2 | FINAL / APPROVED | 3er-Ersatzlimit entfernt |
| Phase 4 – Systemanalyse | DOCUMENTED | v1.1 Professional trägt Dokumentstatus REVIEWED DRAFT; 17 Use Cases wurden als Phase-5-Input verwendet |
| Phase 5.1–5.8 | DOCUMENTED / PASS gemäß Teil-Gates | UX Requirements bis Critical Prototype |
| Phase 5.9 | CONDITIONAL PASS | interner Review abgeschlossen; reale Zielgruppen-Sessions offen |
| Phase 5.10 | PASS FOR PHASE 6 | UX/UI-Baseline eingefroren; kontrollierte Follow-ups bleiben |
| Phase 6 | **CURRENT / IN ARBEIT** | Software Architecture & System Design |
| Feature-Implementierung | **NOT IMPLEMENTED / NOT EVIDENCED** | startet erst nach Architektur-Gate |

## 2. Offene Follow-ups, die Phase 6 nicht blockieren

- reale formative Usability-Sessions mit Mitarbeiter- und Büro/Admin-Zielgruppen
- technische Keyboard-/Focus-/Accessibility-Verifikation in der späteren UI-Implementierung
- Monatsplan-Usability/Performance mit realistischem Full-Month-Datensatz
- High-Fidelity-Ausarbeitung gegen Phase-5-Baseline prüfen
- keine Wettbewerbsvorteilsbehauptung ohne empirische Evidenz

## 3. Was Phase 6 jetzt liefern soll

Phase 6 beantwortet technische Fragen, ohne bereits Features zu implementieren:

- Architekturziele und Qualitätsattribute
- Systemkontext und technische Bausteine
- Domain-/Modulgrenzen
- Company / Project / Month Modellierung
- Mitarbeiterzuordnung vs. Monatsplan
- Draft/Published, Versionierung und atomare Planänderungen
- Optimistic Locking / Concurrency
- Cancellation / ReplacementNeed / Offer als Domain-Verantwortlichkeiten
- serverseitiges RBAC und kontextuelle Berechtigungen
- Work-Queue-/Read-Model-Strategie
- API-Fehlercodes und UI-kompatible Error Contracts
- ADR-Kandidaten mit Alternativen und Trade-offs

**Guardrail:** Screens sind keine Datenbanktabellen. UI-Routen sind keine Domain-Grenzen.

## 4. Keine falschen Implementierungsclaims

Phase-5-HTML-Prototypen sind **PROTOTYPED**, nicht **IMPLEMENTED**.

Solange im Repository kein Produktionscode mit Tests/Build/CI-Nachweis vorliegt, darf ein Feature nicht als implementiert geführt werden.

## 5. Wirksamer Scope

Der Praktikums-MVP folgt Phase 3 plus CR-01. Details: [requirements/effective-mvp-baseline.md](requirements/effective-mvp-baseline.md).
