# Proof Case Measurement Spec

## Status
**Initial bounded measurement completed.**

This is an honest Step-5 artifact, but it is still **narrow**.
It does not claim a full longitudinal proof.

## Measurement design
### Baseline comparator
Because there is no preserved historical pre-gate candidate stream, the most honest comparator is:

> the same live `state.db` snapshot
> viewed once through the ungated SQL ranking
> and once through the gated live emission path.

### Why this comparator is acceptable
It does not pretend we have evidence we do not have.
Instead, it asks the smallest meaningful question:

> does the selected gate actually suppress the known thin-evidence case on the current live system?

## Bounded live observations
### 1. Ungated counterfactual snapshot
From the live 30-day `skill_performance` ranking, the top ungated candidate is still:
- `skill_name = research`
- `task_type = null`
- `uses = 5`
- `avg_quality = 0.5`
- `quality_coverage_pct = 100.0`
- `success_rate = 0.0`
- `last_seen = 2026-03-22 15:08:49`

Interpretation:
Without the gate, the same recovered thin-evidence case still sits at the top of the regression-candidate pool.

### 2. Gated live path
Running:
`python3 scripts/generate_regression_draft_from_db.py --json`

returns:
`No regression candidate found for current filters.`

Interpretation:
With the live gate active, that case is no longer emitted as a regression candidate.

### 3. Direct gate checks
The live gate reasons are:
- for `task_type = null`:
  `task_type fehlt; zuerst Segmentierung sichern, nicht Skill bewerten`
- for `task_type = research` with `avg_quality = 0.5` and `success_rate = 0%`:
  `Outcome-Definition wirkt inkonsistent ...`

Interpretation:
The suppression logic matches the proof-case rationale exactly.

## Threshold
This measurement counts as minimally informative if:
- an ungated candidate exists
- the gated path suppresses it
- the suppression reason matches segmentation/outcome-consistency logic

That threshold is met.

## Disconfirmation rule
The measurement would be disconfirmed if:
- the gated path still emitted the `research` / `task_type = null` candidate
- or the gate reason did not match the documented rationale

## Observed effect
### Supported
- the selected case no longer escalates into emitted regression-candidate handling
- the gate is behaviorally active on the live system
- the current evidence supports an **instrumentation-first** reading

### Not yet supported
- broad downstream improvement across time
- repeated reduction in false-positive review load
- a full end-to-end closed-loop proof

## Verdict posture
**Partially supported; measurement-artifact leaning.**

Best current reading:
> the selected gate is active and successfully suppresses the recovered thin-evidence case,
> but the overall proof remains bounded and should not be oversold.

## Main limitation
This is a **counterfactual same-snapshot comparison**, not a preserved historical pre/post stream.
That is the right honest limitation to disclose.

## Machine-readable source
- `data/proof-case-measurement-spec.json`
