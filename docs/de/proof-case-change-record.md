# Proof-Case-Change-Record

## Status
**Retrospektiv geloggt.**

Dieser Proof Case hat jetzt einen expliziten Step-4-Change-Record.
Die wichtige Nuance ist:

> Es wurde in dieser Session keine frische Runtime-Mutation speziell fuer den Proof Case ausgefuehrt.
> Stattdessen ist die ausgewaehlte Intervention jetzt explizit an bereits live vorhandenen Code und konkrete Git-Commits gebunden.

## Was hier geloggt wird
Die ausgewaehlte Intervention ist das konservative **Selection-Layer-Gate**, das:
- Skill-Level-Regressionsurteile bei fehlendem `task_type` blockiert
- bei Outcome-Definitions-Inkonsistenz ebenfalls blockiert
- den Fall stattdessen in Richtung instrumentation-first behandelt

## Change Surface
- `internal/hermes-agent/scripts/skill_signal_gates.py`
- `internal/hermes-agent/scripts/generate_regression_draft_from_db.py`

## Beste belastbare Aktivierungsreferenzen
### Foundation Commit
- `98adafdb6b9fe90370ec288fe49387fc702fed12`
- `2026-04-13T16:54:24+02:00`
- `feat: add bounded-autonomy telemetry helpers and signal-router tooling`

### Activation Commit
- `1eb678ae5b71212224c82b1893ce972bffef60d9`
- `2026-04-19T19:47:47+02:00`
- `fix: centralize session finalize eval and skill tracking`

Lesart:
- der Commit vom 13. April legt das Fundament der Draft-Erzeugung
- der Commit vom 19. April ist der beste belastbare Aktivierungspunkt fuer die aktuell relevante konservative Gate-Form

## Betroffene Metriken und Views
1. **Regression Candidate Emission**
   - Kandidaten mit fehlendem `task_type` oder Outcome-Definitions-Inkonsistenz werden vor der Draft-Erzeugung unterdrueckt
2. **Skill-Level-Regression-Handling-Posture**
   - null-segmentierte oder intern inkonsistente Faelle werden instrumentation-first behandelt
3. **Downstream Review Candidate Quality**
   - erwartete Reduktion von False-Positive-Regression-Kandidaten

## Rollback
Rollback bleibt eng:
- Gate-Definition/Aufruf entfernen oder revertieren
- frueheres Verhalten der Regression-Candidate-Emission wiederherstellen

Rollback-Referenzen:
- `scripts/skill_signal_gates.py`
- `scripts/generate_regression_draft_from_db.py`

## Warum das als Step 4 zaehlt
Step 4 verlangte:
- Implementierungspfad
- Change-Referenz
- Aktivierungszeit
- betroffene Metriken/Views

Diese vier Punkte liegen jetzt explizit vor.

## Was weiter offen bleibt
- der Record ist retrospektiv, keine neu eingefuehrte Aenderung
- ein Downstream-Effekt ist damit noch nicht bewiesen
- die historische Row-Provenienz bleibt unvollstaendig

## Praktische Konsequenz
Der Engpass verschiebt sich jetzt zu **Step 5**:
**begrenzte Post-Change-Messung.**

## Maschinenlesbare Quelle
- `data/proof-case-change-record.json`
