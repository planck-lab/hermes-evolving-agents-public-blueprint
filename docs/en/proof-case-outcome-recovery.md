# Proof Case Outcome-Definition Recovery

## Status
**Partially recovered, with one strong technical conclusion.**

We can now explain the `0% success` aggregate technically:

> the regression draft logic counts only rows with `outcome = success`,
> and all five recovered `research` rows are `outcome = partial`.

## What was located
### 1. Aggregate logic
In `scripts/generate_regression_draft_from_db.py`, success rate is computed as:
- `SUM(CASE WHEN outcome = 'success' THEN 1 ELSE 0 END) / COUNT(*)`

That means `partial` rows count as zero successes.

### 2. Current finalize logic
In `hermes_state.py`, the current centralized finalize path infers outcome via `_infer_outcome()`.
That function currently maps:
- empty/non-error end reasons -> `success`
- failure/error-like end reasons -> `failure`

So the current centralized finalize path does **not** itself explain historical `partial` rows.

### 3. Historical recovered rows
The five `research` rows in `state.db` all have:
- `task_type = null`
- `session_id = null`
- `quality_score = 0.5`
- `outcome = partial`
- `notes = Auto-tracked dispatch`

## Most important interpretation
This gives us a sharper explanation of the case:

- the `0% success` signal is **technically real** as an aggregate
- but it is still **epistemically weak** as a regression claim

Why?
- `partial` is being treated as non-success in the aggregate
- task segmentation is missing
- session/task provenance is missing
- the exact historical writer that created these `partial` rows is still not fully recovered

## Minimum intervention now justified
The smallest intervention that is now technically supported is:

### Outcome-definition and segmentation gate before skill judgment
1. require `task_type` before evaluating skill-level regression/champion signals
2. document or tighten how `outcome` maps to `success` / `partial` / `failure`
3. avoid skill demotion or routing/default shifts until both are true

## What is still not justified
- a hard regression claim against `research`
- a routing/default change based on this signal alone

## Machine-readable source
- `data/proof-case-outcome-recovery.json`
