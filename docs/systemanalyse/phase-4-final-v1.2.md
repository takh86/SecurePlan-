# Phase 4 – Systemanalyse FINAL v1.2

**Version:** v1.2  
**Stand:** 22.09.2026  
**Status:** FINAL / APPROVED  
**Repo-Hinweis:** Repo-Kurzfassung des freigegebenen ausführlichen Phase-4-Originalartefakts; die vollständigen Use-Case-Spezifikationen bleiben Detailreferenz.

Die 17 Use Cases aus Phase 4 v1.1 bleiben fachlich gültig. v1.2 finalisiert den früheren REVIEWED-DRAFT-Status und schließt zwei Traceability-Lücken zu bereits freigegebenen Anforderungen.

## Use-Case-Scope

UC-01 Anmelden · UC-02 Abmelden · UC-03 Monatsplan erstellen · UC-04 Monatsplan bearbeiten · UC-05 Monatsplan veröffentlichen · UC-06 Eigenen Monatsplan anzeigen · UC-07 Absageantrag erstellen · UC-08 Absageantrag zurückziehen · UC-09 Absageanträge prüfen und entscheiden · UC-10 Ersatzangebot abgeben · UC-11 Ersatzangebote prüfen · UC-12 Ersatzmitarbeiter auswählen · UC-13 Antragsstatus anzeigen · UC-14 offene Vorgänge anzeigen · UC-15 Mitarbeiter verwalten · UC-16 Projekte/Zuordnungen verwalten · UC-17 eigene Statistik anzeigen.

## CL-04-01 – Administrative Verfügbarkeit für Ersatz-Eligibility

Bereits verbindlich: KRANK oder genehmigter URLAUB schließen einen Ersatzkandidaten für den betroffenen Zeitraum aus.

Präzisierung:
- minimale administrative Verfügbarkeits-/Abwesenheitspflege wird UC-15 zugeordnet
- KRANK speichert nur Datum/Zeitraum + Status
- keine Diagnose, Symptome oder medizinische Freitexte
- digitaler Urlaubsantrag und Urlaubskonto bleiben Post-MVP

## CL-04-02 – Projektbezogene Schichtkonfiguration

Projektbezogene Schichtarten und Start-/Endzeiten werden UC-16 zugeordnet.

Kein neuer Use Case und keine neue MVP-Vertikale.

## Querschnittliche Regeln

- serverseitige Autorisierung
- Published Plan = Source of Truth
- Planänderungen werden revalidiert
- Absage ist ein Antrag und entfernt nicht automatisch aus dem Plan
- genau ein Ersatz wird final gewählt
- Planänderung bei Ersatz erfolgt atomar
- CR-01: kein 3er-Ersatzlimit
- Statistik ist planbasiert, keine Zeiterfassung
