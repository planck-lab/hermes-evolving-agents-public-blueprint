# Governance and Guardrails

## Core principle
The aim is **controlled learning under controlled risk**.

## Governance stance
The following items are design decisions, not empirical facts:
- no full-autonomy target
- conservative progression toward adaptation
- human-in-the-loop review before meaningful runtime-affecting changes
- reversibility and auditability before stronger selection logic

## Why this matters
A system can become more adaptive without becoming less governable.
This blueprint assumes that learning quality without rollback, traceability, and review is not enough.

## Practical guardrails
- prefer recommendation before mutation
- prefer narrow blast radius before broad rollout
- separate observation from interpretation from intention
- do not upgrade claims when evidence is still mostly private or low-coverage

## Public reading rule
If a statement on this topic looks normative, it should usually be read as:

> a governance choice for this project,
> not a universal law of agent design.
