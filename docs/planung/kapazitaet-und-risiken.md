# Kapazität und Risiken

**Synchronisiert:** 21.09.2026

## 1. Ursprüngliches Kapazitätsmodell

Die Phase-3-Implementierungsbaseline bleibt:
- 12 Wochen
- 4 Arbeitstage/Woche
- 48 Bruttotage
- ca. 75 % geplante Auslastung
- 36 verplante Tage
- 12 Tage Puffer
- Feature Freeze/Hardening im letzten Drittel

Diese Zahlen beschreiben die **Implementierungsbaseline**, nicht den heutigen Kalenderfortschritt. Analyse/UX-Arbeit wurde vor der eigentlichen Code-Umsetzung weitergeführt.

## 2. Schutzregeln

1. MUST vor SHOULD.
2. Stretch erst nach stabilem MVP-Core.
3. Neue Features standardmäßig zurückstellen.
4. Tests kontinuierlich pro Slice.
5. Security, Authorization und Datenintegrität nicht für Zeitgewinn kürzen.
6. Tagesplan/Lohnabrechnung nicht heimlich in den Praktikums-MVP ziehen.
7. Excel-Import darf den manuellen Plan-Core nicht blockieren.
8. CR-01: keine feste 3er-Ersatzgrenze.

## 3. Agenten-/Human-Regel

KI darf analysieren, entwerfen, implementieren und reviewen. Nicht delegierbar bleiben:
- Architekturentscheidungen
- Scope-/Business-Rule-Entscheidungen
- Security-/Authorization-Entscheidungen
- Human Approval vor Merge zentraler Änderungen

Generierter Code ist ein Vorschlag, kein Nachweis.

## 4. Aktuelles Risikoregister

| Nr. | Risiko | Wirkung | Stand / Maßnahme |
|---|---|---|---|
| R1 | Repo-Dokumentation ist älter als Projektstand | hoch | **adressiert durch Repo-Sync** |
| R2 | UX-Prototyp wird fälschlich als Implementierung behandelt | hoch | klare DOCUMENTED/PROTOTYPED/IMPLEMENTED-Trennung |
| R3 | Architektur wird aus Screens/Routes abgeleitet | hoch | Phase-6-Guardrail: Domain Responsibilities zuerst |
| R4 | Overengineering vor dem ersten Vertical Slice | hoch | Modularer Monolith / einfachster tragfähiger Weg bewerten |
| R5 | Auth/RBAC wird zu spät oder nur im UI umgesetzt | kritisch | serverseitige Authorization; frühe Negativtests |
| R6 | Absage/Ersatz-Konsistenz und Edge Cases | hoch | Transactions, Idempotenz, Optimistic Locking in Phase 6 entscheiden |
| R7 | Scope Creep aus Research/Design | hoch | Phase 3 + CR als verbindlicher Scope |
| R8 | reale Usability-Validierung bleibt offen | mittel | als Follow-up sichtbar halten; keine erfundenen Nutzerergebnisse |
| R9 | Deployment/CI wird zu spät integriert | mittel | frühe minimale Iteration nach Architektur-Gate |
| R10 | Zeitdruck kürzt Tests/Security | kritisch | Stretch entfernen, nicht Quality Guardrails |

## 5. Aktuelles Machbarkeitsurteil

Der MVP ist durch Phase 3 bewusst reduziert: Foundation, Auth/RBAC, Mitarbeiter/Projekte, manueller Monatsplan, Absage/Ersatz, Statistik, Work Queue, Qualitätsminimum und Demo Delivery.

Die nächste relevante Machbarkeitsprüfung erfolgt **nach Phase 6**, wenn Architektur, Slice-Schnitt und technische Risiken besser geschätzt werden können.

Es werden keine fiktiven Fortschritts- oder Resttage erfunden.
