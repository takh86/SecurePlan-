# Phase 5 – UX/UI Baseline Handoff

**Stand:** 16.09.2026 / Repo-Sync aktualisiert am 22.09.2026  
**Gate:** **PASS FOR PHASE 6 / CONTROLLED FOLLOW-UPS**

> **Amendment:** Phase 5.2 wurde durch [Phase-5.2-Amendment v1.2 (CR-02)](phase-5-2-amendment-cr-02.md) präzisiert. Company ist für Tenant-Nutzer fester Account-Kontext, nicht wählbar; die frühere Future-Company-Switcher-/Membership-Annahme ist aufgehoben.

## Teilphasen

- 5.1 UX Requirements – PASS
- 5.2 Information Architecture – PASS / FINAL, amended by v1.2 CR-02
- 5.3 User Flows – PASS
- 5.4 Screen Inventory – PASS
- 5.5 Screen & Interaction States – PASS
- 5.6 Low-Fidelity Wireframes – PASS
- 5.7 Responsive & Accessibility Rules – PASS
- 5.8 Critical-Flow Prototype & Design Handoff – PASS
- 5.9 Expert Review + testbereiter Prototype – CONDITIONAL PASS; reale Zielgruppen-Tests offen
- 5.10 Final UX/UI Baseline – PASS FOR PHASE 6

## Frozen Produkt-/UX-Prinzipien

- Company ist fester Account-Kontext; Project / Month sind sichtbare operative Kontexte
- Admin: exceptions first / Work Queue statt dekorativem KPI-Dashboard
- Deep Links direkt zum fachlichen Fall
- bekannte Kontextdaten nicht erneut abfragen
- Employee: mobile-first, persönlicher Kontext
- Admin: desktop-first
- Mitarbeiterzuordnung und Monatsplan sind getrennte Fachbereiche
- Absage/Ersatz werden im Case Workspace zusammengeführt
- Status und Fehler in verständlicher Alltagssprache
- kritische Aktionen mit Confirmation/Revalidation
- Status nie ausschließlich über Farbe
- Optimistic-Locking-Konflikte als eigener UI-State
- keine neuen Features aus Design-Tools heraus

## Critical Flows

1. Admin erstellt/bearbeitet/veröffentlicht Monatsplan
2. Mitarbeiter sieht Dienst und beantragt Absage
3. System erzeugt Ersatzbedarf; geeigneter Mitarbeiter gibt Angebot ab
4. Admin öffnet Fall aus Work Queue und wählt Ersatz
5. Planänderung erfolgt atomar
6. Mitarbeiter sieht aktuellen Plan, Status und Statistik
7. Planänderung kann offene Absage/Ersatzangebote gegenstandslos machen

## Wichtiger Implementierungs-Hinweis

Die HTML-Artefakte aus Phase 5.8/5.9 sind **Prototypen**. Sie enthalten keine echte Backend-Datenhaltung, Authentifizierung oder Autorisierung und sind kein Produktionscode.

## Offene Follow-ups

- reale Mitarbeiter-/Admin-Usability-Sessions
- Keyboard/Focus/Screen-Reader-Verifikation in echter UI
- Monatsplan mit realistischem Full-Month-Datensatz testen
- High-Fidelity-Design gegen diese Baseline reviewen

Diese Follow-ups blockieren Phase 6 nicht.
