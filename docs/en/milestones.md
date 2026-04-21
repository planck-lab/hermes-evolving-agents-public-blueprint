# Milestones and Gate Matrix

## Purpose
This page turns milestone language into a gate-oriented reading of the current roadmap.

## Current gate posture
| Gate ID | Name | Status | What it means |
|---|---|---|---|
| G-1.5-1 | Strong Signal Detection | met | Stronger candidate signals can be distinguished from weaker/noisier evidence. |
| G-1.5-2 | Signal Routing | met | Signals can be translated into review-oriented artifacts. |
| G-1.5-3 | Review and Inbox Bridge | met | Stronger signals can enter a review path instead of disappearing informally. |
| G-1.5-4 | Adoption Candidate Path | partial | Candidate-state logic exists, but is not yet hardened enough for proof-grade use. |
| G-2-1 | Adoption Mechanism | open | A canonical adoption object and state machine are still missing. |
| G-2-2 | Runtime Change Traceability | open | The system cannot yet publicly show an audited change spine end to end. |
| G-2-3 | Measured Effect Verification | open | No public-ready proof case yet links signal, change, and measured later effect. |
| G-2-4 | Repeated Closed Loops | open | Closed-loop infrastructure is not yet shown as repeatable rather than exceptional. |

## Recommended next milestone focus
### Phase 2A - One-path closed-loop proof
The next build phase should focus on one narrow, auditable path:
1. signal
2. review
3. adopted change
4. runtime change
5. measured effect
6. explicit uncertainty

## Machine-readable source
- `data/phase-gates.json`
