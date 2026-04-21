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

That posture is consistent with risk-management and human-oversight expectations in NIST guidance and the EU AI Act, both of which emphasize documentation, supervision, and managed deployment over unconstrained autonomy [1][2][3].

## Practical guardrails
- prefer recommendation before mutation
- prefer narrow blast radius before broad rollout
- separate observation from interpretation from intention
- do not upgrade claims when evidence is still mostly private or low-coverage

## Public reading rule
If a statement on this topic looks normative, it should usually be read as:

> a governance choice for this project,
> not a universal law of agent design.

## References
[1] NIST AI RMF 1.0, 2023. https://doi.org/10.6028/NIST.AI.100-1  
[2] NIST Generative AI Profile, 2024. https://doi.org/10.6028/NIST.AI.600-1  
[3] EU AI Act, Regulation (EU) 2024/1689. https://eur-lex.europa.eu/eli/reg/2024/1689/oj
