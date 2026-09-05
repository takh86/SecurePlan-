# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project state

SecurePlan has **no application code yet**. This is a solo-developer THM
internship project (~12 weeks, Mon–Thu) currently in the planning stage —
the repository contains only project-management documentation under `docs/`.
There are no build, lint, or test commands to run because no source tree,
package manifest, or test suite exists yet. Do not invent one; check
`docs/planung/fortschrittsprotokoll.md` for the actual current status before
assuming otherwise.

## Source-of-truth hierarchy

Two baseline documents govern what gets built, expected under
`docs/requirements/`:

- **Phase 2 – Requirements Baseline v1.1 FINAL** — product requirements
- **Phase 3 – Scope & MVP v1.1 FINAL** — authoritative internship scope

**If they conflict on what must be implemented during the internship, Phase 3
wins.** As of the last planning pass, neither document has been committed to
the repo, so the backlog (`docs/planung/arbeitsvorrat.md`) and the week-by-week
roadmap content (`docs/planung/fahrplan-12-wochen.md`) are marked `BLOCKIERT`
beyond week 1. Never invent requirement IDs or backlog content to fill that
gap — check whether the baseline docs have landed in `docs/requirements/`
first.

## Status vocabulary (binding, exactly these five)

`GEPLANT` (planned) · `IN ARBEIT` (in progress) · `FERTIG` (done) ·
`BLOCKIERT` (blocked) · `ZURÜCKGESTELLT` (deferred)

`FERTIG` requires evidence actually present in the repository (a commit, PR,
test run, or reachable URL) — never mark something done because it was
planned. This applies to any status you touch: backlog entries, the weekly
plan, and `docs/planung/fortschrittsprotokoll.md`.

## Capacity model driving scope decisions

12 weeks × 4 days (Mon–Thu) = 48 gross days, planned at ~75% capacity = 36
planned days / 12 buffer days. Feature freeze starts week 10, and week 1 is
foundation-only (no feature work), which leaves **~24 planned developer days
for the entire MUST scope**. When asked to help size or re-plan work, check
proposed scope against this budget rather than treating the roadmap as
elastic.

## Engineering approach: vertical slices

Work is planned as vertical slices, not layer-by-layer:

```
Requirement → Business Rule → Data Model → Migration/Constraint →
Backend → API → required UI → Tests → Documentation → Integration → Demo
```

A slice isn't done until it's demonstrable (through the UI or a reproducible
API call against staging), sized at 1–3 planned days. Guardrails from Phase 3
that any plan or implementation must respect: MUST before SHOULD; SHOULD only
once its entry conditions are met; COULD is out of internship scope without
explicit approval; continuous testing (not testing at the end); early
staging/deployment; feature freeze from week 10; **security, authorization,
and data integrity are never cut to recover schedule** — scope (SHOULD/COULD)
is cut instead.

## AI-assisted development: role boundaries

Every backlog item distinguishes three roles — don't blur them:

- **Student responsibility (non-delegable):** architecture decisions, data
  model, business rules, security/authorization decisions, scope decisions,
  supervisor communication.
- **Agent-assisted work (what Claude may do):** repo analysis, implementation
  proposals, coding, test generation, debugging, refactoring, code review,
  security review, documentation, diff review.
- **Human verification (required for every AI-generated change):** diff
  reviewed line by line, tests exist and are correct, requirement mapping
  confirmed against Phase 2/3 IDs, security check (authz, input validation,
  data access), business-rule edge cases checked.

Generated code is a proposal, not a result — it is not merged until the
student understands and can explain it. At most one mergeable AI-generated
change set per day is expected, to keep review quality from degrading.

## Repository layout

```
docs/
  requirements/   Phase 2 / Phase 3 baseline docs + anforderungs-index.md
                  (requirement ID → slice → test → status traceability matrix)
  planung/        fahrplan-12-wochen.md (roadmap), arbeitsvorrat.md (backlog),
                  aktuelle-woche.md (current week plan, rewritten weekly),
                  fortschrittsprotokoll.md (actual progress log — the only
                  source for status reporting), kapazitaet-und-risiken.md
  architektur/    ueberblick.md (architecture overview) + adr/ (ADRs, using
                  0000-vorlage.md as the template — never edit an existing
                  ADR in place; a changed decision gets a new ADR that
                  supersedes the old one)
  betreuung/      templates for daily check-in/check-out and weekly
                  supervisor reports, plus vorlagen.md
```

`docs/planung/arbeitsvorrat.md` defines the backlog entry schema (ID format
`SP-W<week>-<n>`, requirement IDs quoted verbatim from Phase 2/3, MUST entries
before SHOULD before COULD) — use it as the template for any new backlog item
rather than inventing a different shape.

## Reporting rules

Weekly reports and check-ins are generated from
`docs/planung/fortschrittsprotokoll.md` and actual git history — never from
the roadmap or backlog. Do not draft a supervisor-facing report claiming
progress that isn't evidenced in the repository.

## Language

Planning documents (`docs/`, `README.md`) are written in German, consistently
— including structural headings, not just prose. Requirement IDs from Phase
2/3 stay in their original form.
