# References

This page collects the current public-facing reference base for the blueprint.
The goal is not to imply that every claim is fully proven, but to anchor methodology, governance, evaluation, and limitation language in inspectable sources.

## Core scientific and institutional references

[1] National Institute of Standards and Technology. *Artificial Intelligence Risk Management Framework (AI RMF 1.0).* NIST AI 100-1, 2023. https://doi.org/10.6028/NIST.AI.100-1

[2] National Institute of Standards and Technology. *Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile.* NIST AI 600-1, 2024. https://doi.org/10.6028/NIST.AI.600-1

[3] European Union. *Regulation (EU) 2024/1689 laying down harmonised rules on artificial intelligence (Artificial Intelligence Act).* Official Journal of the European Union, 2024. https://eur-lex.europa.eu/eli/reg/2024/1689/oj

[4] Liang, P., Bommasani, R., Lee, T., et al. *Holistic Evaluation of Language Models.* Transactions on Machine Learning Research, 2023. https://openreview.net/forum?id=iO4LZibEqW

[5] Yao, S., Zhao, J., Yu, D., et al. *ReAct: Synergizing Reasoning and Acting in Language Models.* ICLR, 2023. https://openreview.net/forum?id=WE_vluYUL-X

[6] Liu, X., Xu, Y., Zhang, S., et al. *AgentBench: Evaluating LLMs as Agents.* arXiv, 2023. https://arxiv.org/abs/2308.03688

[7] Mialon, G., Dessì, R., et al. *GAIA: a benchmark for General AI Assistants.* arXiv, 2023. https://arxiv.org/abs/2311.12983

[8] Jimenez, C. E., Yang, J., Friedman, D., et al. *SWE-bench: Can Language Models Resolve Real-World GitHub Issues?* ICLR, 2024. https://openreview.net/forum?id=VTF8yNQM66

[9] OpenAI. *Preparedness Framework.* 2023–2024. https://openai.com/index/openai-preparedness-framework/

## How these references are used

| Reference | Primary use in this blueprint |
|---|---|
| [1] | Risk governance, documentation, measurement, management |
| [2] | GenAI-specific operational controls, human oversight, post-deployment monitoring |
| [3] | Bounded autonomy and human oversight language |
| [4] | Multi-dimensional evaluation instead of one-metric benchmarking |
| [5] | Agent loop design: reasoning plus acting plus environment feedback |
| [6] | Agent-specific evaluation beyond static QA |
| [7] | Realistic assistant tasks and practical competence framing |
| [8] | Verified task completion in real software environments |
| [9] | Deployment gating and preparedness framing |

## Citation rule

- Inline citations use numbered references like `[1]`, `[2]`.
- Public-facing claims should prefer institutional or peer-reviewed sources when possible.
- Internal observations in this repo remain distinct from external citations and should not be presented as interchangeable evidence.
