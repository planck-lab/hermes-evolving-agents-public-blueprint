# Überblick

Dieses Projekt beschreibt ein Phasenmodell für ein kontrolliert lernendes Agentensystem.

## Kernidee
Nicht Vollautonomie, sondern:

> kumulativer Erkenntnisgewinn bei kontrollierbarem Risiko.

## Was dieser Entwurf ist
Dies ist ein **Vorstufen-Blueprint** vor einer möglichen Veröffentlichung.
Er soll Aussagen lesbar, kritisierbar und später prüfbar machen.

## Kanonischer Lesepfad
### Diese 7 Seiten zuerst lesen
1. `system-scope.md`
2. `phasenmodell.md`
3. `current-state.md`
4. `methodik.md`
5. `evidenz.md`
6. `governance-and-guardrails.md`
7. `proof-case-final-verdict.md` *(abschließende bounded evidence page)*

Das ist jetzt die bevorzugte Reihenfolge für die meisten Leser.

## Warum es diesen Pfad gibt
Er liefert den kuerzesten ehrlichen Weg zu:
- Systemgrenze
- Phasen-Claim
- Evidenzmodell
- Guardrails
- begrenztem Proof Case und seinen Grenzen als abschließendem bounded example

## Deep-Dive-Pfade
### A. Optionale Proof-Case-Kette
Nur in dieser Reihenfolge lesen, wenn die volle Evidenzkette wichtig ist:
1. `trace-spine.md`
2. `proof-case-scaffold.md`
3. `proof-case-signal-recovery.md`
4. `proof-case-outcome-recovery.md`
5. `proof-case-intervention-selection.md`
6. `proof-case-change-record.md`
7. `proof-case-measurement-spec.md`
8. `proof-case-final-verdict.md`

### B. Skeptische Leseroute
1. `system-scope.md`
2. `methodik.md`
3. `evidenz.md`
4. `messgrenzen.md`
5. `governance-and-guardrails.md`
6. `proof-case-final-verdict.md`

## Aktuelle Build-Priorität
Der Blueprint ist jetzt im Modus **Polish und Konsolidierung**:
- eine kanonische öffentliche Story
- weniger Navigations-Overhead
- tiefe Evidenzkette bleibt erhalten, wird aber nicht jedem Leser aufgezwungen

## Inhalte
### Kernnarrativ
- `system-scope.md`
- `phasenmodell.md`
- `current-state.md`
- `methodik.md`
- `evidenz.md`
- `governance-and-guardrails.md`
- `proof-case-final-verdict.md`

### Tiefe Evidenzkette
- `trace-spine.md`
- `proof-case-scaffold.md`
- `proof-case-execution-plan.md`
- `proof-case-readiness-check.md`
- `proof-case-signal-recovery.md`
- `proof-case-outcome-recovery.md`
- `proof-case-intervention-selection.md`
- `proof-case-change-record.md`
- `proof-case-measurement-spec.md`

### Kontext / Support
- `meilensteine.md`
- `worked-example-closed-loop.md`
- `messgrenzen.md`
- `glossar.md`

### Release prep
- `release-readiness-checklist.md`


## Wissenschaftliche Verankerung
Die öffentliche Rahmung dieses Blueprints orientiert sich bewusst an externen Governance- und Evaluationsquellen statt nur an interner Autorität:
- NIST AI RMF und NIST GenAI Profile für Governance, Dokumentation und Post-Deployment-Messung [1][2]
- EU AI Act für bounded autonomy und menschliche Aufsicht [3]
- HELM für mehrdimensionale Evaluation [4]
- ReAct, AgentBench, GAIA und SWE-bench für Agent-Loop- und Task-Evaluationslogik [5][6][7][8]

## Referenzen
Siehe `referenzen.md` für die ausführlichere Referenzbasis.

[1] NIST AI RMF 1.0, 2023. https://doi.org/10.6028/NIST.AI.100-1  
[2] NIST Generative AI Profile, 2024. https://doi.org/10.6028/NIST.AI.600-1  
[3] EU AI Act, Regulation (EU) 2024/1689. https://eur-lex.europa.eu/eli/reg/2024/1689/oj  
[4] Liang et al., *Holistic Evaluation of Language Models*, TMLR 2023. https://openreview.net/forum?id=iO4LZibEqW  
[5] Yao et al., *ReAct*, ICLR 2023. https://openreview.net/forum?id=WE_vluYUL-X  
[6] Liu et al., *AgentBench*, 2023. https://arxiv.org/abs/2308.03688  
[7] Mialon et al., *GAIA*, 2023. https://arxiv.org/abs/2311.12983  
[8] Jimenez et al., *SWE-bench*, ICLR 2024. https://openreview.net/forum?id=VTF8yNQM66
