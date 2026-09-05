# Aktuelle Woche — Woche 1 (M0 Fundament)

**Meilenstein:** M0 – Fundament
**Wochenziel:** Ein „laufendes Skelett" existiert — ein trivialer Pfad
HTTP → Dienstschicht → Datenbank → Test → CI → Staging mit einer
Platzhalter-Ressource.
**Bewusst keine Fachfunktion.** Die beginnt in Woche 2, wenn Phase 2/3
ausgewertet sind.

**Verplant:** Mo–Mi (3 Tage) · **Puffer:** Do

## Abschlusskriterien der Woche

- [ ] Phase 2 und Phase 3 liegen unter `docs/requirements/` im Repository
- [ ] Anforderungsindex existiert (alle Kennungen aus Phase 2/3 erfasst)
- [ ] ADR-0001 (Technologiestack) und ADR-0002 (AuthN/AuthZ-Ansatz) geschrieben
- [ ] `docker compose up` startet Anwendung + Datenbank lokal
- [ ] Mindestens eine Migration angewandt
- [ ] CI läuft bei jedem Push: Formatprüfung, statische Analyse, Tests, Build
- [ ] Mindestens ein Einheiten- und ein Integrationstest, beide grün
- [ ] Staging-Umgebung erreichbar, Gesundheitsendpunkt antwortet
- [ ] Arbeitsvorrat für Woche 2 aus Phase 3 abgeleitet

---

## Montag — Grundlagen und Rückverfolgbarkeit

**Arbeitsvorrat:** `SP-W01-01`

**Ziel**
Beide Grundlagendokumente liegen versioniert im Repository und jede
Anforderungskennung ist in einem durchsuchbaren Index erfasst.

**Aufgaben**
1. Phase 2 und Phase 3 nach `docs/requirements/` legen, committen, pushen.
2. Beide Dokumente vollständig lesen — selbst, nicht nur der Agent.
3. `docs/requirements/anforderungs-index.md` befüllen:
   Kennung | Titel | Priorität | Quelle | Schnitt | Test | Status.
   Status initial durchgehend `GEPLANT`.
4. Konflikte zwischen Phase 2 und Phase 3 auflisten und entscheiden —
   **beim Umfang gewinnt Phase 3.** Ergebnis im Index dokumentieren.
5. Ersten Eindruck des MUSS-Umfangs gegen die Kennzahl ≈ 24 Entwicklertage halten.

**Anforderungen**
Alle (der Index erfasst den Gesamtbestand).

**Lernziel**
Warum Rückverfolgbarkeit (Anforderung → Code → Test → Nachweis) in einer
Praxisphase den Unterschied macht zwischen „läuft" und „nachweisbar erfüllt".

**Agentenrolle (B)**
Dokumente lesen, Kennungen extrahieren, Indextabelle erzeugen, Widersprüche
zwischen Phase 2 und Phase 3 auflisten.

**Studentenverantwortung (A)**
Beide Dokumente selbst lesen. Jeden Konflikt selbst entscheiden.
**Der Agent setzt keine Priorität.**

**Verifikation**
Stichprobe von 10 Kennungen im Index gegen das Originaldokument prüfen —
sind Wortlaut und Priorität korrekt übernommen?

**Tests**
Heute keine (keine Anwendungslogik).

**Ergebnis**
Commit mit beiden Dokumenten und befülltem Anforderungsindex.

**Fertigstellungskriterien**
Jede in Phase 2/3 vergebene Kennung steht genau einmal im Index;
die Stichprobe ist fehlerfrei.

**Risiken / Rückfallebene**
Dokumente sehr umfangreich → Index heute nur für den MUSS-Umfang vollständig,
SOLL/KANN am Dienstag nachziehen.

---

## Dienstag — Architekturentscheidungen

**Arbeitsvorrat:** `SP-W01-02`

**Ziel**
Technologiestack und Sicherheitsansatz sind entschieden und **begründet
schriftlich** festgehalten.

**Aufgaben**
1. NFR- und SEC-Anforderungen aus Phase 2 herausziehen und den Stack **danach** bewerten.
2. **ADR-0001 Technologiestack**: Kontext, Optionen, Entscheidung, Konsequenzen.
   Bewertet gegen Vorkenntnisse, NFR-Anforderungen, Ökosystemreife,
   Deployment-Aufwand und die verbleibenden ≈ 24 Entwicklertage.
3. **ADR-0002 Authentifizierung und Autorisierung**: Sitzungs- vs. Token-Verfahren,
   Rollenmodell, **wo** Autorisierung geprüft wird.
   Grundsatz: erzwungen in der Dienstschicht, nicht nur in der Oberfläche.
4. `docs/architektur/ueberblick.md`: Kontextsicht + Komponentenübersicht.
5. Woche-2-Schnitte aus dem Phase-3-MUSS-Umfang schneiden und in
   `arbeitsvorrat.md` eintragen.

**Anforderungen**
NFR-*, SEC-* (Kennungen aus Phase 2).

**Lernziel**
Was ein Architekturentscheidungsprotokoll leistet — und warum
„ich kenne die Sprache" allein keine tragfähige Begründung ist.

**Agentenrolle (B)**
Optionen gegenüberstellen, Konsequenzen ausformulieren, ADR-Entwurf schreiben,
Risiken je Option benennen.

**Studentenverantwortung (A)**
**Die Entscheidung selbst.** Das ist die wichtigste nicht delegierbare
Entscheidung der gesamten Praxisphase und muss im Kolloquium ohne Hilfsmittel
verteidigt werden können.

**Verifikation**
ADR-0001 und ADR-0002 laut erklären, aus dem Gedächtnis, ohne das Dokument.
Was nicht erklärbar ist, ist nicht entschieden — sondern übernommen.

**Tests**
Heute keine.

**Ergebnis**
ADR-0001, ADR-0002, Architekturüberblick, Woche-2-Einträge im Arbeitsvorrat.

**Fertigstellungskriterien**
Beide ADRs enthalten mindestens zwei verworfene Alternativen mit Begründung.
Jede SEC-Anforderung aus Phase 2 ist in ADR-0002 adressiert oder ausdrücklich
auf einen späteren Schnitt verwiesen.

**Risiken / Rückfallebene**
Entscheidung fällt schwer → den Stack wählen, in dem am schnellsten produktiv
gearbeitet werden kann. Bei ≈ 24 Entwicklertagen schlägt Vertrautheit
theoretische Eignung. Diese Begründung gehört so ins ADR.

---

## Mittwoch — Projektgerüst, Datenbank, CI

**Arbeitsvorrat:** `SP-W01-03`

**Ziel**
`docker compose up` startet Anwendung und Datenbank lokal;
CI läuft bei jedem Push grün durch.

**Aufgaben**
1. Projektskelett gemäß ADR-0001 anlegen: Abhängigkeiten, Konfiguration,
   Ordnerstruktur, Umgebungsvariablen über `.env.example`.
   **Keine Geheimnisse im Repository.**
2. `docker-compose.yml`: Anwendung + Datenbank mit Datenpersistenz.
3. Migrationswerkzeug einrichten; Migration `0001_init` mit einer
   Platzhaltertabelle inkl. Primärschlüssel, `NOT NULL` und Eindeutigkeitsbedingung.
4. Testgerüst einrichten; ein Einheitentest und ein Integrationstest
   (Integrationstest spricht die **echte** Datenbank an, keine Attrappe).
5. GitHub-Actions-Arbeitsablauf: Formatprüfung → statische Analyse → Tests → Build.
   Fehlschlag bricht den Lauf ab.
6. `.gitignore`, `README.md` (Einrichtung in unter 5 Minuten), PR-Vorlage.

**Anforderungen**
NFR-* (Betreibbarkeit, Testbarkeit).

**Lernziel**
Warum die Datenbankbedingung (`NOT NULL`, `UNIQUE`, Fremdschlüssel) die
eigentliche Absicherung der Datenintegrität ist — und die Validierung im Code
nur die erste Verteidigungslinie.

**Agentenrolle (B)**
Skelett, Compose-Datei, CI-Arbeitsablauf, Testgerüst, Migration.

**Studentenverantwortung (A)**
Entscheidung, welche Bedingungen die Datenbank durchsetzt.
Der CI-Arbeitsablauf muss Zeile für Zeile erklärbar sein.

**Verifikation**
- Frischer Klon in ein leeres Verzeichnis → `docker compose up` → läuft?
- Einen Test absichtlich brechen → wird CI **rot**?
  (Ein CI-Lauf, der nie rot wird, prüft nichts.)
- Migration rückwärts und erneut vorwärts anwenden → funktioniert?

**Tests**
1 Einheitentest, 1 Integrationstest, beide grün in CI.

**Ergebnis**
Pull Request „Fundament" mit grünem CI-Lauf.

**Fertigstellungskriterien**
CI grün auf dem Zweig; absichtlich gebrochener Test erzeugt nachweislich einen
roten Lauf; `.env.example` enthält keine echten Werte.

**Risiken / Rückfallebene**
Docker/CI frisst den Tag → CI-Deployment auf Donnerstag verschieben,
aber lokales `docker compose` **muss** heute stehen.

---

## Donnerstag — Laufendes Skelett, Staging, Wochenabschluss

**Arbeitsvorrat:** `SP-W01-04` (+ Puffer)

**Ziel**
Ein Aufruf gegen die Staging-Umgebung durchläuft alle Schichten und liest
aus der Datenbank.

**Aufgaben**
1. Trivialen vertikalen Pfad bauen: HTTP-Endpunkt → Dienstschicht → Datenzugriff
   → Platzhaltertabelle → Antwort. Plus Gesundheitsendpunkt, der die
   Datenbankverbindung prüft.
2. Integrationstest über den vollständigen Pfad.
3. Staging-Umgebung aufsetzen (kleinster tragfähiger Weg gemäß ADR-0001) und deployen.
4. Pull Request „Fundament" nach `main` zusammenführen (CI grün).
5. `fortschrittsprotokoll.md` für Woche 1 füllen — mit dem **tatsächlichen**
   Status je Aufgabe (`FERTIG` / `IN ARBEIT` / `BLOCKIERT` / `ZURÜCKGESTELLT`).
6. Diese Datei für Woche 2 aus dem Arbeitsvorrat neu aufsetzen.
7. Wochenbericht schreiben (Vorlage: `../betreuung/vorlagen.md`).

**Anforderungen**
NFR-* (Verfügbarkeit, Betreibbarkeit).

**Lernziel**
Warum ein laufendes Skelett in Woche 1 den Integrationsschmerz aus Woche 9
herausnimmt — Deployment ist ein Risiko, das man früh und billig oder spät und
teuer bezahlt.

**Agentenrolle (B)**
Endpunkt, Dienstschicht, Datenzugriff, Test, Deployment-Konfiguration;
Entwurf des Wochenberichts aus dem Git-Verlauf.

**Studentenverantwortung (A)**
Den Wochenbericht **vor dem Versand** gegen den Repository-Stand auf Wahrheit
prüfen. Kein Punkt darin, der nicht im Repository nachweisbar ist.

**Verifikation**
- `curl` gegen die Staging-URL — antwortet der Gesundheitsendpunkt?
- Datenbank in Staging anhalten → meldet der Gesundheitsendpunkt korrekt Fehler?
- Vollständige Diff-Durchsicht des Pull Requests, Zeile für Zeile.

**Tests**
Integrationstest über den vollständigen Pfad, grün in CI.

**Ergebnis**
Erreichbare Staging-URL, `main` grün, Fortschrittsprotokoll Woche 1,
verschickter Wochenbericht.

**Fertigstellungskriterien**
Alle Abschlusskriterien der Woche 1 sind abgehakt **oder** ausdrücklich als
`ZURÜCKGESTELLT` mit Begründung im Fortschrittsprotokoll vermerkt.

**Risiken / Rückfallebene**
Staging scheitert an Zugängen oder Kosten → Rückfall auf ein deploybares
Container-Abbild plus dokumentierten Deployment-Weg; Staging wird zur ersten
Aufgabe der Woche 2 und als `BLOCKIERT` mit Ursache geführt.

---

## Nachplanung

- **Täglich abends:** Diese Datei für den Folgetag anpassen — auf Basis des
  tatsächlichen Fortschritts, nicht des ursprünglichen Plans.
- **Donnerstags:** Woche 2 aus dem Arbeitsvorrat neu aufsetzen.
- Es wird **kein** starrer 48-Tage-Plan festgeschrieben.
