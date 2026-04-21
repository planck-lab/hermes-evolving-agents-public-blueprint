# Proof Case Signal Recovery

## Status
**Partial but meaningful recovery.**

The original trigger snapshot can now be reconstructed more concretely than before.
We still do not have full task-level provenance, but we do have:
- the original signal artifact
- live aggregate evidence from `state.db`
- the raw `skill_performance` rows behind the aggregate

## Recovered trigger picture
### Signal artifact
- `agent-exchange/signals/macbook/2026-04-10-regression-kandidat-in-aktueller-skill-performance.md`

### Recovered aggregate
- skill: `research`
- task_type: `null`
- uses: `5`
- avg_quality: `0.5`
- success_rate: `0.0`
- last_used: `2026-03-22 15:08:49`

### Recovered raw rows
All 5 currently recoverable rows share the same pattern:
- agent_role: `builder`
- task_type: `null`
- quality_score: `0.5`
- outcome: `partial`
- notes: `Auto-tracked dispatch`

Timestamps:
- `2026-03-22 13:13:34`
- `2026-03-22 13:15:37`
- `2026-03-22 14:17:46`
- `2026-03-22 14:17:46`
- `2026-03-22 15:08:49`

## Most important finding
The critical downstream issue is now clearer:

> the raw rows are real,
> but they are not linked to sessions/tasks,
> and they all show `outcome = partial`.

So the case is not just "0% success" in the abstract.
It is a case where:
- all rows are null-segmented
- all rows are only partially successful
- quality and outcome semantics are not strong enough for a hard regression claim
- the aggregate's `0% success` comes from counting only `outcome = success`

## What is still missing
- `session_id` linkage for the five rows
- task-level provenance
- explicit source for the success/outcome definition at signal time

## What this changes
Step 1 is still not fully complete, but it is now materially stronger.
We can now ground the signal block in:
- one explicit signal artifact
- one explicit aggregate query
- one explicit raw-row recovery

## Machine-readable source
- `data/proof-case-signal-recovery.json`
