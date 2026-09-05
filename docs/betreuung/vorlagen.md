# Vorlagen für die Betreuungskommunikation

Gültig für die **aktuelle Woche**. Es werden bewusst **keine** Berichte für
Wochen vorformuliert, die noch nicht stattgefunden haben.

**Grundregel für alle drei Formate:**
Es wird nur gemeldet, was im Repository nachweisbar ist — Commit, Pull Request,
Testlauf oder erreichbare URL. Kein geplanter Stand, keine Aufrundung,
kein erfundener Fortschritt.

---

## 1. Morgendliches Check-in (Element / THMConnect)

```
SecurePlan – Check-in [Wochentag], [TT.MM.]

Heutiges Ziel: <ein messbares Ergebnis>
Geplant:
 - <Aufgabe 1>
 - <Aufgabe 2>
 - <Aufgabe 3>
Offen/Blockiert: <konkret oder "keine">
Bezug: <Anforderungskennungen>
```

### Beispiel — Montag Woche 1

```
SecurePlan – Check-in Montag, TT.MM.

Heutiges Ziel: Phase 2 und Phase 3 liegen versioniert im Repository,
Anforderungsindex ist für den MUSS-Umfang vollständig.
Geplant:
 - Beide Grundlagendokumente einchecken (SP-W01-01)
 - Anforderungsindex befüllen (Kennung, Priorität, Quelle)
 - Konflikte Phase 2 ↔ Phase 3 auflisten und entscheiden
Offen/Blockiert: keine
Bezug: SP-W01-01, Gesamtbestand Phase 2/3
```

---

## 2. Abendliches Check-out

```
SecurePlan – Check-out [Wochentag], [TT.MM.]

Erledigt (FERTIG):
 - <Aufgabe> → Nachweis: <Commit/PR/Testlauf>
In Arbeit:
 - <Aufgabe> → Stand: <konkret>
Blockiert:
 - <Aufgabe> → Ursache: <konkret>
Nicht geschafft:
 - <Aufgabe> → verschoben auf: <Tag>
Erkenntnis heute: <ein bis zwei Sätze>
Plan morgen: <ein Satz>
```

**Regel:** Unter „Erledigt" steht ausschließlich, was im Repository nachweisbar
ist. Ein Fehlschlag wird als Fehlschlag gemeldet — das ist keine schlechte
Nachricht, sondern die Grundlage einer belastbaren Nachplanung.

---

## 3. Wöchentlicher Fortschrittsbericht (E-Mail, formlos)

```
Betreff: SecurePlan – Fortschritt KW <XX> (Woche <n>/12)

Hallo Herr/Frau <Name>,

kurzer Stand zur Woche <n>:

Wochenziel: <Ziel aus dem Fahrplan>
Erreicht:   <erreicht / teilweise erreicht / nicht erreicht>

Abgeschlossen:
 - <Ergebnis> (<Anforderungskennungen>) – <Commit/PR-Verweis>

In Arbeit:
 - <Punkt> – Stand <konkret>

Blockiert / offene Punkte:
 - <Punkt> – Ursache <konkret>

Technische Entscheidung dieser Woche:
 - <ADR-Nummer und Kern der Entscheidung in einem Satz>

Nächste Woche geplant:
 - <2–4 Punkte>

Umfangsstand: MUSS <x>/<y> Schnitte fertig; Zeitplan <im Plan / n Tage Verzug>

Viele Grüße
Taha Hussein
```

### Erstellung

Der Wochenbericht wird aus `../planung/fortschrittsprotokoll.md` und dem
Git-Verlauf erzeugt — **nicht** aus dem Fahrplan.

Nützlich dafür:

```bash
git log --since="7 days ago" --oneline --no-merges
```

Der Agent darf den Bericht entwerfen. **Vor dem Versand prüft der Student jeden
Punkt gegen den Repository-Stand.** Was sich nicht belegen lässt, wird gestrichen
oder als `IN ARBEIT` bzw. `BLOCKIERT` umformuliert.

### Ablage

Verschickte Berichte werden unter `wochenberichte/kw-<XX>.md` abgelegt,
damit der Abschlussbericht in Woche 12 daraus erstellt werden kann.

---

## 4. Eskalation: Umfangsgespräch

Zu verwenden, sobald absehbar ist, dass der MUSS-Umfang bis Woche 9 nicht hält —
**frühestmöglich**, nicht erst in Woche 8.

```
Betreff: SecurePlan – Umfangsabstimmung erforderlich (Woche <n>/12)

Hallo Herr/Frau <Name>,

nach aktuellem Stand ist der MUSS-Umfang bis Woche 9 nicht vollständig
umsetzbar. Grundlage der Einschätzung:

Verbleibende verplante Entwicklertage: <x>
Offener MUSS-Umfang:                   <y> Schnitte, geschätzt <z> Tage
Ursache des Verzugs:                   <konkret>

Vorschlag (Reihenfolge nach Schutzregeln aus Phase 3):
 1. Streichen bzw. Zurückstellen von: <SOLL/KANN-Einträge>
 2. Vereinfachen von: <MUSS-Eintrag> auf <reduzierten Umfang>

Nicht zur Disposition stehen Sicherheit, Autorisierung und Datenintegrität.
Ein Zeitverzug wird nicht darüber aufgeholt.

Bitte um Rückmeldung, ob dieses Vorgehen so mitgetragen wird.

Viele Grüße
Taha Hussein
```
