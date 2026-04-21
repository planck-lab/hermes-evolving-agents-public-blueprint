# Trace Spine

## Purpose
This page defines the **canonical learning object / trace spine** for one narrow closed-loop proof path.

## Why it exists
Without a linked object chain, claims such as:

> signal -> review -> adopted change -> runtime change -> measured effect

remain a narrative instead of an auditable system path.

## Canonical chain
A proof-grade path should link exactly these objects:
1. `signal`
2. `review`
3. `adoption`
4. `change`
5. `measurement`

## Core IDs
- `signal_id`
- `review_id`
- `adoption_id`
- `change_id`
- `measurement_id`

## Object roles
### Signal
Represents the initial candidate learning trigger.

### Review
Captures human or governed evaluation of whether the signal should move forward.

### Adoption
Represents the explicit decision to turn a reviewed signal into one bounded intervention.

### Change
Records the runtime-affecting implementation of that adoption.

### Measurement
Captures the later observation window, measured effect, uncertainty, and confounders.

## Minimum design rules
- each object must have exactly one parent link to the prior stage
- one narrow proof chain is better than many partially linked chains
- runtime-affecting changes should be reversible
- a measurement without uncertainty disclosure is not proof-grade

## Machine-readable files
- `data/trace-spine-schema.json`
- `data/trace-spine-example.json`
- `data/proof-case-scaffold.json`

## What this unlocks
The trace spine is the missing bridge between:
- evidence discipline
- gate logic
- worked-example structure
- future closed-loop proof cases
