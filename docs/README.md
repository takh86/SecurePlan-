# SecurePlan – Projektdokumentation

Dieses Verzeichnis ist die **Quelle der Wahrheit** für die Praxisphase.
Alles, was gegenüber der Betreuung als Fortschritt gemeldet wird, muss hier
oder im Git-Verlauf nachweisbar sein.

## Struktur

| Pfad | Zweck |
|---|---|
| `requirements/` | Verbindliche Grundlagendokumente (Phase 2, Phase 3) + Anforderungsindex |
| `planung/` | Fahrplan, Arbeitsvorrat, aktuelle Woche, Fortschrittsprotokoll, Kapazität/Risiken |
| `architektur/` | Architekturüberblick und Architekturentscheidungsprotokolle (ADR) |
| `betreuung/` | Vorlagen für Check-in/Check-out und die Wochenberichte |

## Statusvokabular (verbindlich, nur diese fünf)

| Status | Bedeutung |
|---|---|
| `GEPLANT` | Aufgabe existiert im Arbeitsvorrat, nicht begonnen |
| `IN ARBEIT` | begonnen, noch nicht abgeschlossen |
| `FERTIG` | alle Fertigstellungskriterien erfüllt, Nachweis im Repository vorhanden |
| `BLOCKIERT` | wartet auf eine externe Voraussetzung (mit benannter Ursache) |
| `ZURÜCKGESTELLT` | bewusst verschoben (mit benannter Begründung) |

**Absolute Regel:** `FERTIG` nur, wenn der Nachweis im Repository liegt.
Kein geplanter Stand wird als erledigt gemeldet. Keine erfundenen Fortschritte
gegenüber der Betreuung.

## Rangfolge der Dokumente

1. **Phase 3 – Scope & MVP v1.1 FINAL** — maßgeblich für den Umfang der Praxisphase.
2. **Phase 2 – Requirements Baseline v1.1 FINAL** — maßgeblich für die Produktanforderungen.

Bei einem Konflikt darüber, **was in der Praxisphase umgesetzt wird, gewinnt Phase 3.**
Jeder festgestellte Konflikt wird in `requirements/anforderungs-index.md` dokumentiert.
