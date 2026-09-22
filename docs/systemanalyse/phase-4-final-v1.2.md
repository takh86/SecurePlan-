# Phase 4 – Systemanalyse FINAL v1.2

**Status:** FINAL / APPROVED

Die 17 Use Cases aus v1.1 bleiben gültig. v1.2 finalisiert den früheren REVIEWED-DRAFT-Status und schließt Traceability-Lücken.

## Use Cases
UC-01 Anmelden · UC-02 Abmelden · UC-03 Monatsplan erstellen · UC-04 Monatsplan bearbeiten · UC-05 Monatsplan veröffentlichen · UC-06 Eigenen Monatsplan anzeigen · UC-07 Absage erstellen · UC-08 Absage zurückziehen · UC-09 Absage entscheiden · UC-10 Ersatzangebot abgeben · UC-11 Ersatzangebote prüfen · UC-12 Ersatz wählen · UC-13 Status anzeigen · UC-14 offene Vorgänge anzeigen · UC-15 Mitarbeiter verwalten · UC-16 Projekte/Zuordnungen verwalten · UC-17 Statistik anzeigen.

## CL-04-01 – Verfügbarkeit
KRANK oder genehmigter URLAUB schließen Ersatzkandidaten aus. Minimale administrative Abwesenheitspflege wird UC-15 zugeordnet. KRANK speichert nur Datum/Zeitraum + Status; keine Diagnose/Freitexte.

## CL-04-02 – Schichtkonfiguration
Projektbezogene Schichtarten und Start-/Endzeiten werden UC-16 zugeordnet.

## Kernregeln
serverseitige Autorisierung · Published Plan = Source of Truth · Revalidation · Absage entfernt nicht automatisch aus Plan · genau ein Ersatz final · atomare Planänderung · kein 3er-Limit · Statistik ist keine Zeiterfassung.
