# SecurePlan – Projektdokumentation

**Stand:** 22.09.2026

Dieses Verzeichnis ist die **aktuelle repo-lokale Projektquelle der Wahrheit**. Historische Originalartefakte bleiben erhalten; die Markdown-Dateien konsolidieren den freigegebenen Stand für Menschen und Coding Agents.

## Aktueller Stand

- Phase 2: FINAL / FROZEN
- Phase 3: FINAL / FROZEN
- Phase 3.5: FINAL / APPROVED
- CR-01: FINAL / APPROVED; feste Obergrenze von drei Ersatzübernahmen entfernt
- CR-02 v1.1: FINAL / APPROVED; B2B-SaaS-/Tenant-Modell und Monate 4–6 präzisiert
- Phase 4: FINAL / APPROVED v1.2
- Phase 5: PASS FOR PHASE 6; Phase-5.2-Amendment v1.2 zu CR-02 wirksam
- Phase 5.9 reale Nutzertests: offen als kontrolliertes Follow-up
- Phase 6.1–6.4: FINAL / APPROVED bzw. RE-APPROVED
- Phase 6.5: nächster Architekturabschnitt
- Production Feature Code: nicht nachgewiesen

Siehe [project-status.md](project-status.md).

## Struktur

| Pfad | Zweck |
|---|---|
| [requirements/](requirements/) | Requirements-/Scope-Baseline, CR-01, CR-02 und Traceability |
| [systemanalyse/](systemanalyse/) | Phase-4-Systemanalyse FINAL v1.2 und Kompaktreferenz |
| [ux-ui/](ux-ui/) | Phase-5-Handoff und IA-Amendment zu CR-02 |
| [architektur/](architektur/) | Phase-6-Architekturteilphasen, Gate Review und ADRs |
| [planung/](planung/) | aktueller Arbeitsabschnitt, Backlog, Roadmap, Fortschritt, Risiken |
| [betreuung/](betreuung/) | Vorlagen für Check-in, Check-out und Wochenberichte |

## Wichtige Dokumente

### Requirements / Scope
- [Effective MVP Baseline](requirements/effective-mvp-baseline.md)
- [Anforderungsindex](requirements/anforderungs-index.md)
- [CR-02 – B2B-SaaS-Tenant-Modell](requirements/cr-02-b2b-saas-tenant-model.md)

### Systemanalyse / UX
- [Phase 4 FINAL v1.2](systemanalyse/phase-4-final-v1.2.md)
- [Phase 4 Kompakt](systemanalyse/phase-4-kompakt.md)
- [Phase 5 Baseline](ux-ui/phase-5-baseline.md)
- [Phase 5.2 Amendment v1.2](ux-ui/phase-5-2-amendment-cr-02.md)

### Architektur
- [Architekturüberblick](architektur/ueberblick.md)
- [Phase 6.1 – Architecture Goals](architektur/phase-6-1-architecture-goals.md)
- [Phase 6.2 – System Context & Container View](architektur/phase-6-2-system-context-container.md)
- [Phase 6.3 – Backend Building Blocks](architektur/phase-6-3-backend-building-blocks.md)
- [Phase 6.4 – Dependencies & Public Contracts](architektur/phase-6-4-module-dependencies-public-contracts.md)
- [Backward Consistency Gate](architektur/backward-consistency-gate-2026-09-22.md)
- [ADR-Vorlage](architektur/adr/0000-vorlage.md)

### Planung
- [Aktueller Arbeitsabschnitt](planung/aktuelle-woche.md)
- [12-Wochen-Fahrplan](planung/fahrplan-12-wochen.md)
- [Arbeitsvorrat](planung/arbeitsvorrat.md)
- [Kapazität & Risiken](planung/kapazitaet-und-risiken.md)
- [Fortschrittsprotokoll](planung/fortschrittsprotokoll.md)

## Source-of-Truth-Reihenfolge

Bei Konflikten gilt:

1. Phase 2 Requirements Baseline v1.1 plus genehmigte Change Requests / Amendments (**CR-01, CR-02 v1.1**)
2. Phase 3 Scope & MVP v1.1 für den 3-Monats-Praktikumsumfang
3. Phase 3.5 Research & Impact Review als Validierung; keine stille Scope-Änderung
4. Phase 4 Systemanalyse **FINAL v1.2**
5. Phase 5.1–5.10 plus **Phase-5.2-Amendment v1.2**
6. freigegebene Phase-6-Architekturdokumente (6.1–6.4)
7. ADRs für später ausdrücklich genehmigte technische Detailentscheidungen

Wichtig: Phase 3 verschiebt gültige Phase-2-Produktanforderungen aus dem Praktikums-MVP, ohne sie als Produktanforderung zu löschen. CR-02 erweitert nicht den 3-Monats-MVP, sondern präzisiert den 6-Monats-Produkthorizont.

## Nachweisregel

**FERTIG** wird nur für tatsächlich nachweisbare Ergebnisse verwendet.

- **DOCUMENTED:** Analyse-/Designartefakt vorhanden
- **PROTOTYPED:** klickbarer/visueller Prototyp vorhanden
- **IMPLEMENTED:** Produktionscode + Test-/Build-/Repository-Nachweis vorhanden
