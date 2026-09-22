# Phase 4 – Systemanalyse KOMPAKT

**Version:** v1.0  
**Stand:** 22.09.2026  
**Status:** Arbeits-/Architekturreferenz  
**Repo-Hinweis:** Bewusst verdichtete Kurzfassung. Für vollständige Vorbedingungen, Haupt-/Alternativabläufe und Nachbedingungen gilt das ausführliche Phase-4-Originalartefakt; [Phase 4 FINAL v1.2](phase-4-final-v1.2.md) dokumentiert den wirksamen Gate-/Clarification-Stand.

## Systemgrenze

### Im MVP
- Mitarbeiter- und Projektverwaltung
- Monatsplanung
- persönliche Mitarbeiteransicht
- Absage & Ersatz
- Admin Work Queue
- planbasierte Statistik

### Außerhalb
- Tagesplan
- Lohnabrechnungen
- vollständige Notifications
- Zeiterfassung
- GPS/WKS
- KI-Planung

## Akteure

**Büro/Admin:** verwaltet Mitarbeiter/Projekte, erstellt und veröffentlicht Monatspläne, bearbeitet Absage-/Ersatzfälle.

**Mitarbeiter:** sieht eigenen veröffentlichten Plan, erstellt/zieht Absage zurück, gibt Ersatzangebot ab, sieht Status und Statistik.

## Kernprozesse

- Planung: UC-15/16 → UC-03 → UC-04 → UC-05 → UC-06
- Absage & Ersatz: UC-06 → UC-07 → UC-10 → UC-11 → UC-12 → UC-13
- Admin Work Queue: UC-14 → UC-09 / UC-11 / UC-12
- Employee Statistics: UC-05/06 → UC-17

## Kritische Regeln

- Mitarbeiter sehen nur eigene/freigegebene Ressourcen.
- Published Plan ist verbindliche Source of Truth.
- Absage erzeugt Ersatzbedarf, entfernt aber nicht automatisch aus dem Plan.
- Pro Mitarbeiter und ReplacementNeed höchstens ein aktives ReplacementOffer.
- Genau ein Ersatz wird final ausgewählt.
- Ersatz-Planänderung muss atomar sein.
- Kein 3er-Ersatzlimit.
- Employee Statistics ist keine Arbeitszeiterfassung.
