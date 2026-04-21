# Overview

This project describes a phase model for a controlled learning agent system.

## Core idea
Not full autonomy, but:

> cumulative learning under controlled risk.

## What this draft is
This is a **pre-public blueprint**.
It aims to make claims legible, challengeable, and eventually auditable.

## Canonical reading path
### Read these 7 pages first
1. `system-scope.md`
2. `phases.md`
3. `current-state.md`
4. `methodology.md`
5. `evidence.md`
6. `governance-and-guardrails.md`
7. `proof-case-final-verdict.md` *(closing bounded evidence page)*

This is the preferred order for most readers.

## Why this path exists
It gives the shortest honest route to understanding:
- what the system boundary is
- how the phase claim is made
- what evidence model is being used
- what one bounded proof case currently supports as a bounded closing example
- what is still not proven

## Scientific grounding
The public framing in this repo is intentionally aligned with external governance and evaluation sources rather than private authority alone:
- NIST AI RMF and the NIST Generative AI Profile for governance, documentation, and post-deployment measurement [1][2]
- EU AI Act human-oversight language for bounded autonomy and supervision expectations [3]
- HELM for multi-dimensional evaluation design [4]
- ReAct, AgentBench, GAIA, and SWE-bench for agent-loop and task-evaluation framing [5][6][7][8]

## Deep-dive paths
### A. Optional proof-case chain
Read this only if you want the full evidence chain:
1. `trace-spine.md`
2. `proof-case-scaffold.md`
3. `proof-case-signal-recovery.md`
4. `proof-case-outcome-recovery.md`
5. `proof-case-intervention-selection.md`
6. `proof-case-change-record.md`
7. `proof-case-measurement-spec.md`
8. `proof-case-final-verdict.md`

### B. Skeptical reader path
1. `system-scope.md`
2. `methodology.md`
3. `evidence.md`
4. `measurement-limits.md`
5. `governance-and-guardrails.md`
6. `proof-case-final-verdict.md`

## Current build priority
The blueprint is now in **polish and consolidation mode**:
- keep one canonical public story
- reduce navigation overhead
- preserve the deeper evidence chain without forcing every reader through it

## Included pages
### Core narrative
- `system-scope.md`
- `phases.md`
- `current-state.md`
- `methodology.md`
- `evidence.md`
- `governance-and-guardrails.md`
- `proof-case-final-verdict.md`

### Deep evidence chain
- `trace-spine.md`
- `proof-case-scaffold.md`
- `proof-case-execution-plan.md`
- `proof-case-readiness-check.md`
- `proof-case-signal-recovery.md`
- `proof-case-outcome-recovery.md`
- `proof-case-intervention-selection.md`
- `proof-case-change-record.md`
- `proof-case-measurement-spec.md`

### Supporting context
- `milestones.md`
- `worked-example-closed-loop.md`
- `measurement-limits.md`
- `glossary.md`

### Release prep
- `release-readiness-checklist.md`

## References
See `references.md` for the numbered reference base used across the README and website.

[1] NIST AI RMF 1.0, 2023. https://doi.org/10.6028/NIST.AI.100-1  
[2] NIST Generative AI Profile, 2024. https://doi.org/10.6028/NIST.AI.600-1  
[3] EU AI Act, Regulation (EU) 2024/1689. https://eur-lex.europa.eu/eli/reg/2024/1689/oj  
[4] Liang et al., *Holistic Evaluation of Language Models*, TMLR 2023. https://openreview.net/forum?id=iO4LZibEqW  
[5] Yao et al., *ReAct*, ICLR 2023. https://openreview.net/forum?id=WE_vluYUL-X  
[6] Liu et al., *AgentBench*, 2023. https://arxiv.org/abs/2308.03688  
[7] Mialon et al., *GAIA*, 2023. https://arxiv.org/abs/2311.12983  
[8] Jimenez et al., *SWE-bench*, ICLR 2024. https://openreview.net/forum?id=VTF8yNQM66
