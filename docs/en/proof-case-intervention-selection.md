# Proof Case Intervention Selection

## Status
**Selected.**

The chosen first intervention is a **conservative selection-layer gate**:

> do not emit or treat a skill-level regression candidate as evidence
> when task segmentation is missing
> or when success-rate and quality signals indicate an outcome-definition inconsistency.

## Decision question
Which single reversible intervention should be used first for this proof case?

## Candidate options considered
### 1. Selection-layer gate before regression judgment — **selected**
- suppress regression/champion-style judgment when `task_type` is missing
- also suppress when outcome-definition inconsistency is detected
- surface the case as instrumentation-first instead

Why this wins:
- smallest reversible change
- directly matches the recovered evidence
- reduces false-positive skill demotion risk immediately
- does not mutate routing defaults

### 2. Redefine aggregate success semantics — not selected
This would attack the visible `0% success` metric directly, but it is semantically riskier and would weaken comparability with historical aggregates before segmentation is fixed.

### 3. Backfill historical rows first — not selected
Useful later, but too broad and too reconstruction-heavy for the first bounded intervention.

### 4. Change runtime outcome taxonomy first — not selected
Potentially valuable later, but broader than needed for a first proof-case move and not required to stop thin-evidence judgment now.

## Selected intervention
### Name
**Segmentation and outcome-consistency gate before regression judgment**

### Exact statement
Before emitting or acting on a skill-level regression candidate, require non-empty `task_type` segmentation and block the candidate when `success_rate` and quality coverage suggest an outcome-definition inconsistency.

### Change surface
- `internal/hermes-agent/scripts/skill_signal_gates.py`
- `internal/hermes-agent/scripts/generate_regression_draft_from_db.py`

### Why this is the right first move
- It addresses the actual recovered weakness: missing segmentation plus misleading aggregate success semantics.
- It is narrow, reversible, and auditable.
- It prevents escalation from thin evidence without pretending the historical provenance problem is solved.

## What this intervention does **not** do
- it does **not** redefine historical success semantics
- it does **not** repair old `session_id = null` rows
- it does **not** demote the `research` skill
- it does **not** change global routing defaults beyond the gate

## Rollback mechanism
Rollback is straightforward:
- remove or revert the selection-gate invocation
- restore prior regression-draft emission behavior

Canonical rollback refs:
- `scripts/skill_signal_gates.py`
- `scripts/generate_regression_draft_from_db.py`

## Approval posture
- **Selection spec approved by:** project owner
- **Selection date:** 2026-04-21
- **Scope of approval here:** choose and document the intervention
- **Not done in this step:** execute/log a dedicated proof-case runtime change

## Important nuance
The live codebase already contains an analogous conservative gate shape.
That means the conceptual intervention is no longer vague.

But for this proof case, Step 4 is still open because we still lack:
- a dedicated change record
- an activation timestamp for the proof case
- a bounded post-change observation window

## Practical consequence
Step 3 is now **ready**:
- one intervention is selected
- the approval owner is known
- rollback references are known

The bottleneck moves to Step 4:
**change logging and explicit proof-case execution.**

## Machine-readable source
- `data/proof-case-intervention-selection.json`
