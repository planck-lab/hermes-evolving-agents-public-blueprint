# Worked Example - Closed Loop

## Status
This page is still a template, but now as a more explicit proof schema.

## Proof goal
A future worked example should make one narrow claim auditable:

> one reviewed signal led to one reversible runtime-affecting change and a later measured effect.

## Canonical object spine
The example should use the linked ID chain defined in `trace-spine.md` and `data/trace-spine-schema.json`:
- `signal_id`
- `review_id`
- `adoption_id`
- `change_id`
- `measurement_id`

## Required sections
### 1. Signal
- What happened?
- Why was it considered strong enough?
- What evidence class applies?

### 2. Review
- Who reviewed it?
- What alternatives were considered?
- Why did it move forward?

### 3. Adopted change
- What exactly changed?
- Was the change reversible?
- What was the expected effect?

### 4. Runtime trace
- Where can the change be seen?
- When did it become active?
- What system surface records it?

### 5. Measurement
- What observation window was used?
- What metric or qualitative signal was checked?
- What changed afterward?

### 6. Uncertainty and confounders
- What else could explain the result?
- What remains unproven?
- What would count as disconfirmation?

## Minimum verdict fields
- `claim_status`
- `confidence_posture`
- `review_date`
- `limitations`
- `follow_up_needed`

## Current state
No public-ready worked example has been populated yet.
That absence is itself an important part of the current maturity reading.
