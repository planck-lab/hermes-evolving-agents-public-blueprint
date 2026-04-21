# Evidence Register

This page defines the minimum public-facing claim discipline for the roadmap.

## Core rule
Every meaningful statement should be tagged as one of:
- **Observation**
- **Inference**
- **Design Decision**
- **Hypothesis**

## Current public claim set
| Claim ID | Type | Short statement | Status |
|---|---|---|---|
| C-001 | Inference | The system is currently approximately at Phase 1.5. | partially-supported |
| C-002 | Inference | Bridge Closure is currently likely the primary bottleneck. | partially-supported |
| C-003 | Observation | Measurement surfaces, signal logic, and review/adoption staging already exist. | supported |
| C-004 | Observation | A stable repeated closed learning loop is not yet established as fact. | supported |
| C-005 | Design Decision | Controlled Selection should only come after stronger Closed Feedback. | intentional |

## Reading rules
- `supported` means the current evidence is good enough for a bounded statement.
- `partially-supported` means the statement is plausible but still challengeable.
- `intentional` marks governance choices rather than observations.
- Public readers should treat private-source-backed claims as provisional until a more inspectable evidence layer exists.

## Machine-readable files
- `data/claim-source-map.json`
- `data/evidence-register.json`
- `data/phase-gates.json`

## What still needs to mature
- public-friendly evidence excerpts or redacted surrogates
- a stronger gate matrix for phase assignment
- a worked example with explicit uncertainty and attribution
