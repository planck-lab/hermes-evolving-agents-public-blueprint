# Proof Case Execution Plan

## Goal
Turn the selected real-case scaffold into one bounded **Phase-2A execution path**.

This is not the proof itself.
It is the operational plan for producing one honest proof attempt.

## Selected case
- skill: `research`
- posture: regression / instrumentation candidate
- preferred interpretation path: **diagnostic first, not selection first**

## Step-by-step plan
### 1. Capture trigger evidence
Needed:
- exact metric/dashboard snapshot
- exact sessions/tasks behind the alert
- current success/quality definition

Output:
- a fully populated `signal` object with real provenance

### 2. Run the review
Needed:
- review owner
- review artifact location
- explicit alternatives considered

Output:
- a filled `review` object
- one of three current readings:
  - `true-regression`
  - `measurement-artifact`
  - `inconclusive`

### 3. Define one minimal reversible intervention
Preferred type:
- instrumentation or segmentation correction
- not a global routing/default shift

Output:
- a filled `adoption` object
- a rollback plan

### 4. Implement and log the change
Needed:
- exact implementation path
- activation timestamp
- affected metrics/views

Output:
- a fully instantiated `change` object

### 5. Measure bounded post-change effect
Needed:
- baseline comparator
- observation window
- minimum threshold
- disconfirmation rule

Output:
- a filled `measurement` object
- a final honest verdict:
  - true regression
  - measurement artifact
  - inconclusive

## Guardrails
- no global default shifts
- no skill demotion from thin evidence
- no success narrative without uncertainty disclosure
- one narrow reversible intervention is enough

## Main open dependencies
- truth-aligned trigger snapshot
- named review owner
- concrete diagnostic change
- observation window
- minimum evidence threshold

## Machine-readable source
- `data/proof-case-execution-plan.json`
- `data/proof-case-readiness-check.json`
