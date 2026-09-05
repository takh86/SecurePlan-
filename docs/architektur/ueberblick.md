# Architekturüberblick

**Status: `BLOCKIERT`**
**Ursache:** Phase 2 und Phase 3 liegen nicht vor. Ohne die NFR- und
SEC-Anforderungen lässt sich keine begründete Architektur beschreiben.

Wird am **Dienstag der Woche 1** (`SP-W01-02`) erstellt, gemeinsam mit
ADR-0001 und ADR-0002, und in **Woche 11** auf den Endstand gebracht.

---

## 1. Kontextsicht

_Wer nutzt SecurePlan, und mit welchen externen Systemen spricht es?_

⛔ offen — abzuleiten aus Phase 2.

## 2. Komponentensicht

_Welche Bausteine gibt es, und wie hängen sie zusammen?_

⛔ offen — abzuleiten aus ADR-0001.

## 3. Datenmodell

_Kernentitäten und ihre Beziehungen; welche Bedingungen die Datenbank durchsetzt._

⛔ offen — abzuleiten aus den Geschäftsregeln der Phase 2.

**Grundsatz:** Datenintegrität wird in der **Datenbank** durchgesetzt
(`NOT NULL`, `UNIQUE`, Fremdschlüssel, `CHECK`). Validierung im Code ist die
erste Verteidigungslinie, nicht die Absicherung.

## 4. Sicherheitsarchitektur

_Authentifizierung, Autorisierung, Datenzugriff, Geheimnisverwaltung._

⛔ offen — abzuleiten aus den SEC-Anforderungen der Phase 2, entschieden in ADR-0002.

**Grundsatz:** Autorisierung wird in der **Dienstschicht** erzwungen, nicht nur
in der Oberfläche. Eine ausgeblendete Schaltfläche ist keine Autorisierung.
Jeder Schnitt bringt Negativtests für unberechtigten Zugriff mit.

## 5. Betrieb und Deployment

_Lokale Umgebung, CI, Staging._

⛔ offen — abzuleiten aus ADR-0001.

---

## Architekturentscheidungen

Alle Entscheidungen werden als ADR unter `adr/` festgehalten.
Vorlage: `adr/0000-vorlage.md`.

| Nr. | Titel | Status |
|---|---|---|
| 0001 | Technologiestack | ⛔ offen (Woche 1, Dienstag) |
| 0002 | Authentifizierung und Autorisierung | ⛔ offen (Woche 1, Dienstag) |
