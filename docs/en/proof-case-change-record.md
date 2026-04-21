# Proof Case Change Record

## Status
**Retrospectively logged.**

This proof case now has an explicit Step-4 change record.
The important nuance is:

> this was not a fresh runtime mutation executed for the proof case in this session.
> Instead, the selected intervention is now anchored to the already-live code and to concrete git commits.

## What is being logged
The selected intervention is the conservative **selection-layer gate** that:
- blocks skill-level regression judgment when `task_type` is missing
- blocks it when outcome-definition inconsistency is detected
- routes the case toward instrumentation-first handling instead

## Change surface
- `internal/hermes-agent/scripts/skill_signal_gates.py`
- `internal/hermes-agent/scripts/generate_regression_draft_from_db.py`

## Best grounded activation references
### Foundation commit
- `98adafdb6b9fe90370ec288fe49387fc702fed12`
- `2026-04-13T16:54:24+02:00`
- `feat: add bounded-autonomy telemetry helpers and signal-router tooling`

### Activation commit
- `1eb678ae5b71212224c82b1893ce972bffef60d9`
- `2026-04-19T19:47:47+02:00`
- `fix: centralize session finalize eval and skill tracking`

Interpretation:
- the April 13 commit created the draft-generation foundation
- the April 19 commit is the best grounded activation point for the current conservative gate shape used by this proof case

## Affected metrics and views
1. **Regression candidate emission**
   - candidates with missing `task_type` or outcome-definition inconsistency are suppressed before draft generation
2. **Skill-level regression handling posture**
   - null-segmented or internally inconsistent cases are treated as instrumentation-first
3. **Downstream review candidate quality**
   - expected reduction in false-positive regression candidates

## Rollback
Rollback remains narrow:
- remove or revert the gate definition/invocation
- restore the earlier regression-candidate emission behavior

Rollback refs:
- `scripts/skill_signal_gates.py`
- `scripts/generate_regression_draft_from_db.py`

## Why this counts as Step 4
Step 4 asked for:
- implementation path
- change reference
- activation time
- affected metrics/views

We now have all four in explicit form.

## What remains unresolved
- this record is retrospective, not a newly introduced change
- it does not prove downstream effect yet
- historical row provenance is still incomplete

## Practical consequence
The bottleneck now moves to **Step 5**:
**bounded post-change measurement.**

## Machine-readable source
- `data/proof-case-change-record.json`
