# Anforderungsgrundlagen

**Stand:** 21.09.2026  
**Status:** Architekturarbeit ist **nicht mehr durch fehlende Phase-2/3-Dokumente blockiert**.

Die ursprüngliche Repository-Aussage „Phase 2 und Phase 3 fehlen“ war nur für den Stand vom 05.09.2026 korrekt. Die später freigegebenen Projektartefakte wurden inzwischen ausgewertet und in eine repo-lokale wirksame Baseline übertragen.

## Wirksame Quellen

| Quelle | Status | Rolle |
|---|---|---|
| Phase 2 – FINAL Requirements Baseline v1.1, 02.09.2026 | FINAL / APPROVED / FROZEN | Produktanforderungen |
| Phase 3 – FINAL Scope & MVP v1.1, 02.09.2026 | FINAL / APPROVED / FROZEN | verbindlicher Praktikumsumfang |
| Phase 3.5.3 – Requirements & Scope Impact Review v1.0 | FINAL / APPROVED | Research-Impact und Change-Control |
| Baseline Amendment v1.2 / CR-01, 08.09.2026 | FINAL / APPROVED | normative Korrektur |
| Phase 5.10 – FINAL UX/UI Baseline Gate v1.0, 16.09.2026 | PASS FOR PHASE 6 | Handoff in Architektur |

Repo-lokale konsolidierte Fassung:
[effective-mvp-baseline.md](effective-mvp-baseline.md)

## Konfliktregel

- Phase 2 definiert das Gesamtprodukt.
- Phase 3 definiert, was im Praktikum umgesetzt wird.
- Ein genehmigtes Amendment/CR überschreibt widersprechende ältere Stellen.
- Research allein ändert keine Frozen Baseline.
- CR-01 entfernt die feste 3er-Ersatzgrenze.

## CR-01 – verbindlich

Entfallen:
- BR-ER-08
- BR-ER-09, soweit es das 3er-Ersatzkontingent definiert
- AC-ER-04
- die entsprechende 3er-Limit-Formulierung in Phase 3 M5 und Woche 9

Alle übrigen Eligibility-, Genehmigungs-, Transaktions-, Idempotenz- und Planregeln bleiben bestehen.

## Traceability

Der MVP-orientierte Index steht in [anforderungs-index.md](anforderungs-index.md).

Er wird ab Implementierungsbeginn pro Slice um Code-, Test- und Nachweisverweise erweitert. Fehlende Zeilen-Transkription aus dem vollständigen Phase-2-Gesamtprodukt blockiert **nicht** Phase 6; implementiert wird ausschließlich gegen die hier konsolidierte wirksame MVP-Baseline und genehmigte spätere ADRs/Changes.
