# 12-Wochen-Fahrplan

**Stand:** 05.09.2026
**Rahmen:** festgelegt · **Inhalte ab Woche 2:** `BLOCKIERT` (Phase 3 fehlt)

Grundlage: der Fahrplan aus Phase 3, verfeinert um den tatsächlichen
Repository-Zustand (grüne Wiese, 1 Commit, kein Code).
Kapazitätsmodell und Schutzregeln: siehe `kapazitaet-und-risiken.md`.

---

## Übersicht

| Woche | Meilenstein | Hauptziel | Umfang | Puffer |
|---|---|---|---|---|
| 1 | **M0 – Fundament** | Lauffähiges Skelett vom Aufruf bis zur Datenbank, in CI und Staging | ✅ festgelegt | Do |
| 2 | M1 – Sicherheitskern | Authentifizierung/Autorisierung als erster vertikaler Fachschnitt | ⛔ aus Phase 3 | Do |
| 3 | M1 | Kern-Datenmodell + erster fachlicher MUSS-Schnitt | ⛔ aus Phase 3 | Do |
| 4 | M1 | MUSS-Schnitte | ⛔ aus Phase 3 | Do |
| 5 | **M2 – MVP-Kern** | MUSS-Schnitte, Zwischenvorführung | ⛔ aus Phase 3 | Do |
| 6 | M2 | MUSS-Schnitte | ⛔ aus Phase 3 | Do |
| 7 | M2 | MUSS-Schnitte | ⛔ aus Phase 3 | Do |
| 8 | **M3 – MUSS vollständig** | Letzte MUSS-Schnitte; Umfangsentscheidung SOLL | ⛔ aus Phase 3 | Do |
| 9 | M3 | SOLL nur bei erfüllten Eintrittsbedingungen; sonst Härtung | ⛔ aus Phase 3 | Do |
| 10 | **Funktionsstopp** | Keine neuen Funktionen. Fehlerbehebung, Sicherheitsdurchsicht, Testlücken | ✅ festgelegt | ganze Woche |
| 11 | M4 – Stabilisierung | Abschlussdokumentation, Architekturüberblick, ADR-Vollständigkeit | ✅ festgelegt | ganze Woche |
| 12 | **M4 – Abgabe** | Abschlussbericht, Vorführung, Übergabe | ✅ festgelegt | ganze Woche |

---

## In jeder Woche geltende Grundsätze

- **Wöchentliches Abschlusskriterium:** `main` ist grün, Staging läuft,
  die Woche ist im `fortschrittsprotokoll.md` dokumentiert, der Wochenbericht
  ist an die Betreuung verschickt.
- Ein Umfangsverzug wird durch Streichen von SOLL/KANN aufgefangen —
  **nie** durch Kürzen von Sicherheit, Autorisierung oder Datenintegrität.
- Ab **Woche 8** wird wöchentlich geprüft, ob der MUSS-Umfang bis Woche 9 hält.
  Wenn nicht: Umfangsgespräch mit der Betreuung **in Woche 8**, nicht später.
- Am Ende jeder Woche wird die Folgewoche neu geplant (`aktuelle-woche.md`).
  Es wird **nicht** im Voraus ein starrer 48-Tage-Plan festgeschrieben.

---

## Woche 1 — M0 Fundament (festgelegt)

**Hauptziel:** Ein „laufendes Skelett" existiert — ein trivialer Pfad
HTTP → Dienstschicht → Datenbank → Test → CI → Staging mit einer
Platzhalter-Ressource. **Bewusst keine Fachfunktion**; die beginnt in Woche 2,
wenn Phase 2/3 ausgewertet sind.

**Vorführbares Ergebnis:** `curl` gegen die Staging-URL liefert eine Antwort,
die nachweislich aus der Datenbank stammt; der Gesundheitsendpunkt meldet
den Datenbankzustand korrekt.

**Abschlusskriterien**
- [ ] Phase 2 und Phase 3 liegen unter `docs/requirements/` im Repository
- [ ] Anforderungsindex existiert (alle Kennungen aus Phase 2/3 erfasst)
- [ ] ADR-0001 (Technologiestack) und ADR-0002 (AuthN/AuthZ-Ansatz) geschrieben
- [ ] `docker compose up` startet Anwendung + Datenbank lokal
- [ ] Mindestens eine Migration angewandt
- [ ] CI läuft bei jedem Push: Formatprüfung, statische Analyse, Tests, Build
- [ ] Mindestens ein Einheiten- und ein Integrationstest, beide grün
- [ ] Staging-Umgebung erreichbar, Gesundheitsendpunkt antwortet
- [ ] Arbeitsvorrat für Woche 2 aus Phase 3 abgeleitet

**Risiken:** R1 (fehlende Grundlagen), R6 (Fundamentaufwand), R7 (Staging)
**Abhängigkeiten:** Phase 2 und Phase 3 müssen am Montag eingecheckt sein
**Puffer:** Donnerstag

Detailplan: `aktuelle-woche.md`

---

## Woche 2 — M1 Sicherheitskern

**Hauptziel:** Authentifizierung und Autorisierung als **erster vertikaler
Fachschnitt** — bewusst zuerst, nicht zuletzt (Risiko R4).

**Umfang:** ⛔ `BLOCKIERT` — wird aus den SEC-/FR-Anforderungen der Phase 2 und
dem MUSS-Umfang der Phase 3 abgeleitet.

**Vorführbares Ergebnis (Rahmen):** Ein Nutzer meldet sich an; ein Zugriff ohne
ausreichende Berechtigung wird nachweislich abgewiesen — belegt durch einen
Negativtest, nicht nur durch die Oberfläche.

**Abschlusskriterien (Rahmen)**
- [ ] Autorisierung wird in der Dienstschicht erzwungen, nicht nur in der Oberfläche
- [ ] Negativtests für unberechtigten Zugriff vorhanden und grün
- [ ] Geheimnisse ausschließlich über Umgebungsvariablen, nichts im Repository
- [ ] Schnitt in Staging vorführbar

**Abhängigkeiten:** Woche 1 vollständig; ADR-0002 entschieden
**Risiken:** R4 (Unterschätzung), R2 (Umfang)
**Puffer:** Donnerstag

---

## Wochen 3–9 — M1 bis M3

**Umfang:** ⛔ `BLOCKIERT` — wird nach Vorliegen von Phase 3 aus dem
priorisierten Arbeitsvorrat belegt (`arbeitsvorrat.md`).

**Belegungsregel:** Pro Woche 2–3 vertikale Schnitte à 1–3 verplante Tage,
strikt in Abhängigkeitsreihenfolge, MUSS vor SOLL. Donnerstag bleibt Puffer.

**Prüfpunkt Woche 5:** Zwischenvorführung des MVP-Kerns für die Betreuung.
**Prüfpunkt Woche 8:** Umfangsentscheidung — hält MUSS bis Woche 9?
Wenn nein, Umfangsgespräch **jetzt**.
**Woche 9:** SOLL-Einträge **nur**, wenn deren Eintrittsbedingungen aus Phase 3
nachweislich erfüllt sind. Andernfalls: Härtung, Testlücken, Fehlerbehebung.

---

## Woche 10 — Funktionsstopp (festgelegt)

**Hauptziel:** Stabilisierung. **Ab dieser Woche keine neuen Funktionen.**

**Umfang**
- Fehlerbehebung aus den Wochen 1–9
- Vollständige Sicherheitsdurchsicht (Autorisierung, Eingabevalidierung, Datenzugriff, Geheimnisverwaltung, Abhängigkeiten)
- Testlücken schließen, insbesondere Autorisierungs-Negativfälle und Grenzfälle der Geschäftsregeln
- Anforderungsindex vollständig auf tatsächlichen Stand bringen

**Abschlusskriterien**
- [ ] Kein Eintrag im Anforderungsindex trägt einen unbelegten Status
- [ ] Sicherheitsdurchsicht dokumentiert, Befunde behoben oder ausdrücklich als Restrisiko benannt
- [ ] `main` grün, Staging läuft

**Regel:** Jeder Wunsch nach einer Ausnahme geht als Umfangsentscheidung an die
Betreuung — er wird nicht still umgesetzt.

**Risiken:** R8 (Funktionsstopp wird unterlaufen)

---

## Woche 11 — M4 Stabilisierung (festgelegt)

**Hauptziel:** Das Projekt ist ohne mündliche Erklärung verständlich.

**Umfang**
- `docs/architektur/ueberblick.md` auf den Endstand bringen
- ADR-Bestand vollständig und widerspruchsfrei
- README: Einrichtung, Betrieb, Deployment, Tests
- Rückverfolgbarkeit final: Anforderung → Schnitt → Test → Nachweis
- Bekannte Einschränkungen und Restrisiken schriftlich benennen

**Abschlusskriterien**
- [ ] Ein fremder Entwickler kann das Projekt allein anhand der Dokumentation aufsetzen
- [ ] Jede getroffene Architekturentscheidung hat ein ADR
- [ ] Anforderungsindex spiegelt den tatsächlichen Repository-Stand

---

## Woche 12 — M4 Abgabe (festgelegt)

**Hauptziel:** Abgabefähiger Stand und Vorführung.

**Umfang**
- Abschlussbericht aus `fortschrittsprotokoll.md` und dem Git-Verlauf erstellen
- Vorführung vorbereiten und proben (Ablauf entlang der MUSS-Schnitte)
- Übergabe: Repository, Staging-Zugang, offene Punkte
- Abschließende Rückschau: was hat getragen, was nicht

**Abschlusskriterien**
- [ ] Abschlussbericht enthält ausschließlich nachweisbare Ergebnisse
- [ ] Vorführung läuft gegen Staging, nicht gegen die lokale Umgebung
- [ ] Nicht umgesetzter Umfang ist ausdrücklich als `ZURÜCKGESTELLT` benannt, mit Begründung
