# Kapazität und Risiken

## 1. Kapazitätsmodell (verbindlich)

| Größe | Wert |
|---|---|
| Kalenderwochen | 12 |
| Arbeitstage pro Woche | 4 (Mo–Do) |
| Bruttotage gesamt | **48** |
| Planauslastung | 75 % |
| **Verplante Tage gesamt** | **36** |
| **Puffer gesamt** | **12** |

### Wochenrhythmus (Standard)

- **Mo–Mi** — Umsetzung verplanter Aufgaben (3 Tage = 75 %)
- **Do** — Integration, Tests grün ziehen, Dokumentation, Nachziehen, Wochenbericht

Der Puffer ist **keine** Reserve für zusätzlichen Funktionsumfang.
Er deckt: Einarbeitung, Fehlersuche, Integrationsprobleme, Rückmeldungen der
Betreuung, Refaktorierung.

### Die harte Zahl, die den Umfang bestimmt

Der Funktionsstopp gilt **ab Woche 10**. Das echte Entwicklungsfenster ist damit:

| | Tage |
|---|---|
| Woche 1–9 brutto | 36 |
| abzüglich Woche 1 (Fundament, keine Fachfunktion) | −4 |
| Bruttotage für Fachfunktionalität | 32 |
| **davon verplant bei 75 %** | **≈ 24 Tage** |

> **Der gesamte MUSS-Umfang aus Phase 3 muss in rund 24 verplante Entwicklertage passen.**

Das ist der Maßstab für die Machbarkeitsprüfung, sobald Phase 3 vorliegt.
Passt der Umfang nicht, wird das **sofort** gemeldet — nicht in Woche 8.

---

## 2. Schutzregeln (aus Phase 3, einzuhalten)

1. MUSS vor SOLL.
2. SOLL erst, wenn dessen Eintrittsbedingungen erfüllt sind.
3. KANN liegt außerhalb des Praxisphasenumfangs, außer bei ausdrücklicher Freigabe.
4. Durchgehendes Testen — nicht am Ende.
5. Frühe Staging-Umgebung / frühes Deployment.
6. Funktionsstopp ab Woche 10.
7. **Sicherheit, Autorisierung und Datenintegrität werden niemals gekürzt, um
   Zeitverzug aufzuholen.** Bei Verzug wird Funktionsumfang gestrichen, nicht Sicherheit.

---

## 3. Arbeitsweise: Vertikale Schnitte

Kein „erst Backend, dann Frontend, Tests zum Schluss". Jeder Schnitt läuft
vollständig durch:

```
Anforderung → Geschäftsregel → Datenmodell → Migration/Bedingung →
Backend → Schnittstelle → benötigte Oberfläche → Tests →
Dokumentation → Integration → Vorführung
```

**Fertigkeitsregel:** Ein Schnitt gilt erst als fertig, wenn er vorführbar ist —
über die Oberfläche oder mindestens über einen reproduzierbaren
Schnittstellenaufruf gegen die Staging-Umgebung.

**Schnittgröße:** 1–3 verplante Tage. Größere Themen werden zerlegt.

---

## 4. Rollenmodell: Student, Agent, Verifikation

### A — Studentenverantwortung (nicht delegierbar)

Architekturentscheidungen, Datenmodell, Geschäftsregeln, Sicherheits- und
Autorisierungsentscheidungen, Umfangsentscheidungen, Betreuungskommunikation.

> Jede wichtige Entscheidung muss ohne Blick in den Code erklärbar sein.

### B — Agentenunterstützung (erlaubt)

Repository-Analyse, Umsetzungsvorschläge, Codeerstellung, Testerstellung,
Fehlersuche, Refaktorierung, Code-Durchsicht, Sicherheitsdurchsicht,
Dokumentation, Diff-Durchsicht.

### C — Menschliche Verifikation (Pflicht bei jeder KI-Änderung)

1. **Diff-Durchsicht** — jede Zeile gelesen und verstanden.
2. **Testnachweis** — Tests laufen, und sie prüfen die richtige Sache.
3. **Anforderungsabgleich** — welche Kennung aus Phase 2/3 wird erfüllt?
4. **Sicherheitsprüfung** — Autorisierung, Eingabevalidierung, Datenzugriff.
5. **Geschäftsregelprüfung** — hält die Regel auch am Rand (Grenzfälle)?

**Grundsatz:** Generierter Code ist ein Vorschlag, kein Ergebnis.
Nicht verstandener Code wird nicht zusammengeführt.

**Tagesgrenze:** Höchstens ein größerer KI-generierter Änderungssatz pro Tag.
Alles darüber wird aufgeteilt — sonst kippt die Durchsichtsqualität.

---

## 5. Risikoregister

Wird wöchentlich am Donnerstag geprüft und fortgeschrieben.

| Nr. | Risiko | Wirkung | Wahrsch. | Gegenmaßnahme | Stand |
|---|---|---|---|---|---|
| R1 | **Phase 2/3 fehlen im Repository** — Arbeitsvorrat und Fahrplaninhalte blockiert | hoch | **eingetreten** | Aufgabe 1 am Montag der Woche 1 | **offen** |
| R2 | MUSS-Umfang passt nicht in ≈24 verplante Entwicklertage | hoch | mittel | Prüfung sofort nach Vorliegen von Phase 3; bei Nichtpassen Umfangsgespräch in Woche 1, nicht in Woche 8 | offen |
| R3 | Alleinentwickler ohne menschliche Code-Durchsicht | mittel | hoch | Verpflichtende Selbstdurchsicht (Abschnitt 4 C); Pull Request auch bei Alleinarbeit; Betreuung erhält wöchentlich PR-Verweise | offen |
| R4 | Sicherheits-/Autorisierungsanforderungen werden unterschätzt | **hoch** | mittel | AuthN/AuthZ ist der **erste** Fachschnitt (Woche 2), nicht der letzte; Autorisierungs-Negativtests in jedem Schnitt Pflicht | offen |
| R5 | KI-generierter Code wird übernommen, ohne verstanden zu werden | hoch | mittel | Tagesgrenze; Erklärprobe bei ADRs; nicht Erklärbares wird nicht zusammengeführt | offen |
| R6 | Fundamentaufwand (grüne Wiese) frisst mehr als Woche 1 | mittel | mittel | Feste Abschlusskriterien Woche 1; bei Verzug fällt Staging (nicht CI, nicht Tests) auf Woche 2 | offen |
| R7 | Staging/Deployment scheitert an Zugängen oder Kosten | mittel | mittel | In Woche 1 aufdecken, nicht in Woche 9; Rückfallebene: deploybares Container-Abbild + dokumentierter Weg | offen |
| R8 | Funktionsstopp ab Woche 10 wird unterlaufen | mittel | mittel | Ab Woche 10 werden nur Fehlerbehebungen zusammengeführt; Ausnahmen gehen als Umfangsentscheidung an die Betreuung | offen |
| R9 | Zeitverzug wird durch Weglassen von Sicherheit/Autorisierung aufgeholt | **kritisch** | niedrig | Ausdrückliches Verbot (Schutzregel 7). Verzug wird ausschließlich über Streichen von SOLL/KANN aufgefangen | offen |

---

## 6. Machbarkeitsurteil (Stand 05.09.2026, vorläufig)

Das **Prozessgerüst** ist tragfähig: 36 verplante Tage, 12 Tage Puffer,
wöchentliche Abschlusskriterien, früher Staging-Pfad, Funktionsstopp ab Woche 10.

Die **inhaltliche Machbarkeit** ist noch **nicht** beurteilbar — dafür wird Phase 3
benötigt. Die entscheidende Kennzahl liegt jedoch vor:
**≈ 24 verplante Entwicklertage für den gesamten MUSS-Umfang.** Das ist knapp.
Es ist damit zu rechnen, dass nach Sichtung von Phase 3 über den Umfang
gesprochen werden muss.
