# Arbeitsvorrat (Backlog)

**Status: `BLOCKIERT`**
**Ursache:** Phase 2 und Phase 3 liegen nicht im Repository vor
(siehe `../requirements/README.md`).

Ohne die Grundlagendokumente können keine Einträge mit echten Anforderungs-
kennungen erzeugt werden. Kennungen werden **wörtlich aus Phase 2/3 übernommen**
— sie werden nicht abgeleitet und nicht erfunden.

---

## Erstellungsregeln (gelten, sobald die Dokumente vorliegen)

1. **Alle MUSS-Einträge zuerst**, sortiert nach technischer Abhängigkeit.
   Authentifizierung/Autorisierung und das Kern-Datenmodell stehen vor allem,
   was darauf aufbaut.
2. **SOLL-Einträge** danach, jeweils mit ihren Eintrittsbedingungen aus Phase 3
   als **explizite Abhängigkeit** im Feld „Abhängigkeiten".
3. **KANN-Einträge** ausschließlich als klar markierter Anhang außerhalb des
   Praxisphasenumfangs — Umsetzung nur nach ausdrücklicher Freigabe.
4. Jeder Eintrag ist ein **vertikaler Schnitt** von 1–3 verplanten Tagen.
   Größeres wird zerlegt.
5. Kennungsschema: `SP-W<Woche>-<laufende Nummer>`, z. B. `SP-W03-02`.
   Die Wochenziffer ist die **geplante** Woche und wird bei Verschiebung
   **nicht** geändert (die Kennung bleibt stabil, der Fahrplan zieht nach).

---

## Eintragsschema

```markdown
### SP-W02-01 — <Titel>

| Feld | Inhalt |
|---|---|
| Kennung | SP-W02-01 |
| Ziel | eine messbare Aussage |
| Epic | <aus Phase 3> |
| Anforderungen | FR-…, BR-…, SEC-…, NFR-… (wörtlich aus Phase 2/3) |
| Abhängigkeiten | SP-W01-03 |
| Komplexität | S / M / L |
| Risiko | niedrig / mittel / hoch + Begründung |
| Status | GEPLANT |

**Umsetzungsaufgaben**
1. Datenmodell und Migration inkl. Datenbankbedingungen
2. Geschäftsregel in der Dienstschicht
3. Schnittstelle
4. benötigte Oberfläche
5. Tests
6. Dokumentation

**Testanforderungen**
- Einheitentests: <Geschäftsregel, inkl. Grenzfälle>
- Integrationstests: <vollständiger Pfad gegen die echte Datenbank>
- Autorisierungstests (Negativfälle): <unberechtigter Zugriff wird abgewiesen>

**Fertigstellungskriterien**
- [ ] Alle Umsetzungsaufgaben erledigt
- [ ] Tests grün in CI
- [ ] In Staging vorführbar
- [ ] Anforderungsindex aktualisiert (Kennung → Schnitt → Test)
- [ ] Diff vollständig durchgesehen und verstanden

**Erwarteter Nachweis**
- Commit-/PR-Verweis, Testausgabe, Migrationsdatei, ggf. Screenshot

**Agentenrolle (B):** <was der Agent beitragen darf>
**Studentenverantwortung (A):** <was nicht delegierbar ist>
**Menschliche Verifikation (C):** <was konkret geprüft wird>
```

---

## MUSS-Einträge

⛔ `BLOCKIERT` — wartet auf Phase 3.

## SOLL-Einträge

⛔ `BLOCKIERT` — wartet auf Phase 3. Jeweils mit Eintrittsbedingung.

## KANN-Einträge (außerhalb des Praxisphasenumfangs)

⛔ `BLOCKIERT` — wartet auf Phase 3. Umsetzung nur nach ausdrücklicher Freigabe.

---

## Festgelegte Einträge Woche 1 (baselineunabhängig)

Diese vier Einträge sind unabhängig von Phase 2/3 planbar, weil sie das
technische Fundament betreffen und keine Fachanforderung umsetzen.

### SP-W01-01 — Grundlagen und Rückverfolgbarkeit

| Feld | Inhalt |
|---|---|
| Kennung | SP-W01-01 |
| Ziel | Phase 2 und Phase 3 liegen versioniert im Repository; jede Anforderungskennung ist im Index erfasst |
| Epic | Projektfundament |
| Anforderungen | alle (Index über den Gesamtbestand) |
| Abhängigkeiten | — |
| Komplexität | M |
| Risiko | hoch — blockiert den gesamten übrigen Arbeitsvorrat (R1) |
| Status | GEPLANT |

**Fertigstellungskriterien**
- [ ] Beide Dokumente unter `docs/requirements/` eingecheckt
- [ ] Jede Kennung aus Phase 2/3 steht genau einmal im Anforderungsindex
- [ ] Stichprobe über 10 Kennungen fehlerfrei (Wortlaut, Priorität)
- [ ] Konflikte Phase 2 ↔ Phase 3 dokumentiert und entschieden

**Agentenrolle (B):** Dokumente lesen, Kennungen extrahieren, Indextabelle erzeugen, Widersprüche auflisten
**Studentenverantwortung (A):** Beide Dokumente selbst lesen; jeden Konflikt selbst entscheiden — der Agent setzt keine Priorität
**Menschliche Verifikation (C):** Stichprobe gegen das Originaldokument

---

### SP-W01-02 — Architekturentscheidungen (ADR-0001, ADR-0002)

| Feld | Inhalt |
|---|---|
| Kennung | SP-W01-02 |
| Ziel | Technologiestack und AuthN/AuthZ-Ansatz sind entschieden und schriftlich begründet |
| Epic | Projektfundament |
| Anforderungen | NFR-*, SEC-* (Kennungen aus Phase 2) |
| Abhängigkeiten | SP-W01-01 |
| Komplexität | M |
| Risiko | hoch — trägt das gesamte Projekt; nachträgliche Korrektur ist teuer |
| Status | GEPLANT |

**Fertigstellungskriterien**
- [ ] ADR-0001 und ADR-0002 geschrieben
- [ ] Jedes ADR enthält mindestens zwei verworfene Alternativen mit Begründung
- [ ] Jede SEC-Anforderung aus Phase 2 ist in ADR-0002 adressiert oder ausdrücklich auf einen späteren Schnitt verwiesen
- [ ] Architekturüberblick mit Kontext- und Komponentensicht

**Agentenrolle (B):** Optionen gegenüberstellen, Konsequenzen ausformulieren, ADR-Entwurf schreiben, Risiken je Option benennen
**Studentenverantwortung (A):** **Die Entscheidung selbst.** Wichtigste nicht delegierbare Entscheidung der Praxisphase
**Menschliche Verifikation (C):** Beide ADRs aus dem Gedächtnis laut erklären, ohne das Dokument. Was nicht erklärbar ist, ist nicht entschieden — sondern übernommen

---

### SP-W01-03 — Projektgerüst, Datenbank, CI

| Feld | Inhalt |
|---|---|
| Kennung | SP-W01-03 |
| Ziel | `docker compose up` startet Anwendung und Datenbank lokal; CI läuft bei jedem Push |
| Epic | Projektfundament |
| Anforderungen | NFR-* (Betreibbarkeit, Testbarkeit) |
| Abhängigkeiten | SP-W01-02 |
| Komplexität | L |
| Risiko | mittel — Werkzeugketten-Aufwand wird typischerweise unterschätzt (R6) |
| Status | GEPLANT |

**Testanforderungen**
- 1 Einheitentest
- 1 Integrationstest gegen die **echte** Datenbank (keine Attrappe)

**Fertigstellungskriterien**
- [ ] `docker compose up` läuft aus einem frischen Klon
- [ ] Migration `0001_init` mit Primärschlüssel, `NOT NULL` und Eindeutigkeitsbedingung
- [ ] Migration rückwärts und erneut vorwärts anwendbar
- [ ] CI: Formatprüfung → statische Analyse → Tests → Build; Fehlschlag bricht ab
- [ ] Absichtlich gebrochener Test erzeugt nachweislich einen **roten** CI-Lauf
- [ ] `.env.example` vorhanden, enthält **keine** echten Werte

**Agentenrolle (B):** Skelett, Compose-Datei, CI-Arbeitsablauf, Testgerüst, Migration
**Studentenverantwortung (A):** Welche Bedingungen die Datenbank durchsetzt; CI-Arbeitsablauf Zeile für Zeile erklären können
**Menschliche Verifikation (C):** Frischer Klon; CI absichtlich rot ziehen; Migration hin und zurück

---

### SP-W01-04 — Laufendes Skelett und Staging

| Feld | Inhalt |
|---|---|
| Kennung | SP-W01-04 |
| Ziel | Ein Aufruf gegen Staging durchläuft alle Schichten und liest aus der Datenbank |
| Epic | Projektfundament |
| Anforderungen | NFR-* (Verfügbarkeit, Betreibbarkeit) |
| Abhängigkeiten | SP-W01-03 |
| Komplexität | M |
| Risiko | mittel — Zugänge/Kosten der Staging-Umgebung (R7) |
| Status | GEPLANT |

**Hinweis:** Bewusst **keine** Fachfunktion. Es geht ausschließlich darum, den
Integrationsschmerz früh und billig zu bezahlen statt spät und teuer.

**Testanforderungen**
- Integrationstest über den vollständigen Pfad, grün in CI

**Fertigstellungskriterien**
- [ ] HTTP-Endpunkt → Dienstschicht → Datenzugriff → Platzhaltertabelle → Antwort
- [ ] Gesundheitsendpunkt prüft die Datenbankverbindung
- [ ] Staging erreichbar; `curl` gegen die Staging-URL antwortet
- [ ] Datenbank in Staging angehalten → Gesundheitsendpunkt meldet korrekt Fehler
- [ ] PR „Fundament" mit grünem CI nach `main` zusammengeführt

**Agentenrolle (B):** Endpunkt, Dienstschicht, Datenzugriff, Test, Deployment-Konfiguration
**Studentenverantwortung (A):** Deployment-Weg verstehen und erklären können
**Menschliche Verifikation (C):** Vollständige Diff-Durchsicht des PR, Zeile für Zeile

---

## Nicht eingeführt

Story Points, Velocity-Diagramme, Burndown-Charts und ein zum Repository
paralleles Ticketsystem. Bei einem Alleinentwickler kosten sie mehr, als sie
einbringen. Verbindlich sind: dieser Arbeitsvorrat, `aktuelle-woche.md` und
`fortschrittsprotokoll.md`.
