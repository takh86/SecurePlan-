# Anforderungsgrundlagen

**Stand:** 22.09.2026  
**Status:** konsolidierte Grundlage für Phase 6; Architekturarbeit ist nicht durch fehlende Phase-2/3-Dokumente blockiert.

Die ursprüngliche Repository-Aussage „Phase 2 und Phase 3 fehlen“ war nur für den Stand vom 05.09.2026 korrekt. Die später freigegebenen Projektartefakte wurden inzwischen in eine repo-lokale wirksame Baseline übertragen.

## Wirksame Quellen

| Quelle | Status | Rolle |
|---|---|---|
| Phase 2 – FINAL Requirements Baseline v1.1 | FINAL / APPROVED / FROZEN | Produktanforderungen |
| Phase 3 – FINAL Scope & MVP v1.1 | FINAL / APPROVED / FROZEN | verbindlicher 3-Monats-Praktikumsumfang |
| Phase 3.5.3 – Requirements & Scope Impact Review v1.0 | FINAL / APPROVED | Research-Impact und Change-Control |
| CR-01 / Baseline Amendment v1.2 | FINAL / APPROVED | 3er-Ersatzlimit entfernt |
| CR-02 – B2B-SaaS-Tenant-Modell v1.1 | FINAL / APPROVED | Tenant-/Roadmap-Präzisierung |
| Phase 4 – Systemanalyse v1.2 | FINAL / APPROVED | Use Cases + Traceability-Clarifications |
| Phase 5.10 + Phase-5.2-Amendment | PASS FOR PHASE 6 | UX-Handoff / Company-Kontext |

Repo-lokale konsolidierte Fassung: [effective-mvp-baseline.md](effective-mvp-baseline.md)

## Konfliktregel

- Phase 2 definiert das Gesamtprodukt.
- Phase 3 definiert, was im 3-Monats-Praktikum umgesetzt wird.
- Ein genehmigtes Amendment/CR überschreibt widersprechende ältere Stellen.
- Research allein ändert keine Frozen Baseline.
- CR-01 entfernt die feste 3er-Ersatzgrenze.
- CR-02 präzisiert das B2B-SaaS-/Tenant-Modell und die Monate 4–6, ohne den 3-Monats-MVP aufzuweiten.

## CR-01 – verbindlich

Entfallen:
- BR-ER-08
- BR-ER-09, soweit es das 3er-Ersatzkontingent definiert
- AC-ER-04
- die entsprechende 3er-Limit-Formulierung in Phase 3 M5 und Woche 9

Alle übrigen Eligibility-, Genehmigungs-, Transaktions-, Idempotenz- und Planregeln bleiben bestehen.

## CR-02 – verbindlich

- Company = Tenant.
- Tenant-Nutzerkonto gehört genau einer Company.
- Kein Company Switcher / keine Cross-Company-Membership.
- Monate 1–3 bleiben der eingefrorene Praktikums-MVP.
- Monate 4–6 erlauben Multi-Company-Aktivierung und minimalen providerseitigen Platform/Tenant Admin.
- Billing/Subscription und vollständiges Self-Service-Onboarding bleiben WON'T NOW.
- Cross-Company Reads/Writes sind verboten.

Details: [cr-02-b2b-saas-tenant-model.md](cr-02-b2b-saas-tenant-model.md)

## Traceability

Der MVP-orientierte Index steht in [anforderungs-index.md](anforderungs-index.md).

Er wird ab Implementierungsbeginn pro Slice um Code-, Test- und Nachweisverweise erweitert. Dokumentation oder Prototypen allein gelten nicht als Implementierungsnachweis.
