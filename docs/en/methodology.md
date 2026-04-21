# Methodology

## Evidence classes
- **E1** - Primary Internal Observation
- **E2** - Primary External Source
- **E3** - Secondary Source
- **E4** - Inference
- **E5** - Design Decision
- **E6** - Open Hypothesis

## Core discipline
Strong public statements should never appear without three things:
1. claim type
2. evidence class
3. source trail

This follows the spirit of established AI governance and evaluation practice: map the system, measure it, document caveats, and avoid collapsing design intent into evidence [1][2][4].

## Distinction rules
### Observation
A statement about what is directly present in the current system or artifact set.

### Inference
A model-based interpretation drawn from multiple observations.

### Design Decision
A governance or operating choice for this project.

### Hypothesis
A plausible but not yet established claim.

## Claim-to-source rule
Each stronger claim should map to a claim entry with:
- claim ID
- DE/EN wording
- claim type
- evidence class
- support status
- source list
- caveats

## Public-writing rule
Do not let:
- inference read like observation
- governance read like evidence
- ambition read like current state

## Measurement discipline
A future closed-loop proof should disclose:
- what changed
- why it changed
- when it changed
- what effect was expected
- what was later observed
- what alternative explanations remain

## Known current limits
See `measurement-limits.md` for current public evidence limits and observability caveats.

## References
[1] NIST AI RMF 1.0, 2023. https://doi.org/10.6028/NIST.AI.100-1  
[2] NIST Generative AI Profile, 2024. https://doi.org/10.6028/NIST.AI.600-1  
[3] EU AI Act, Regulation (EU) 2024/1689. https://eur-lex.europa.eu/eli/reg/2024/1689/oj  
[4] Liang et al., *Holistic Evaluation of Language Models*, TMLR 2023. https://openreview.net/forum?id=iO4LZibEqW
