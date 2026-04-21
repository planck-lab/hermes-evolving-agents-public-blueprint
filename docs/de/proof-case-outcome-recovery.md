# Proof-Case-Outcome-Definition-Recovery

## Status
**Teilweise rekonstruiert, mit einer starken technischen Schlussfolgerung.**

Wir koennen das Aggregat `0% success` jetzt technisch erklaeren:

> die Regression-Draft-Logik zaehlt nur Rows mit `outcome = success`,
> und alle fuenf rekonstruierten `research`-Rows sind `outcome = partial`.

## Was lokalisiert wurde
### 1. Aggregat-Logik
In `scripts/generate_regression_draft_from_db.py` wird die Success Rate berechnet als:
- `SUM(CASE WHEN outcome = 'success' THEN 1 ELSE 0 END) / COUNT(*)`

Das heisst: `partial`-Rows zaehlen als null Successes.

### 2. Aktuelle Finalize-Logik
In `hermes_state.py` leitet der aktuelle zentralisierte Finalize-Pfad den Outcome via `_infer_outcome()` ab.
Diese Funktion mappt aktuell:
- leere/nicht-fehlerhafte end reasons -> `success`
- fehlerartige end reasons -> `failure`

Der aktuelle zentralisierte Finalize-Pfad erklaert historische `partial`-Rows also **nicht** direkt.

### 3. Historische rekonstruierte Rows
Die fuenf `research`-Rows in `state.db` haben alle:
- `task_type = null`
- `session_id = null`
- `quality_score = 0.5`
- `outcome = partial`
- `notes = Auto-tracked dispatch`

## Wichtigste Interpretation
Damit wird die Fallerklaerung schaerfer:

- das Signal `0% success` ist als Aggregat **technisch real**
- als Regressionsclaim bleibt es aber **epistemisch schwach**

Warum?
- `partial` wird im Aggregat als non-success behandelt
- Task-Segmentierung fehlt
- Session-/Task-Provenienz fehlt
- der exakte historische Writer dieser `partial`-Rows ist weiterhin nicht voll rekonstruiert

## Minimalintervention, die jetzt gerechtfertigt ist
Die kleinste jetzt technisch tragfaehige Intervention ist:

### Outcome-Definition- und Segmentierungs-Gate vor Skill-Urteil
1. `task_type` verlangen, bevor skill-level Regression-/Champion-Signale bewertet werden
2. dokumentieren oder schaerfen, wie `outcome` auf `success` / `partial` / `failure` abgebildet wird
3. Skill-Demotionen oder Routing-/Default-Shifts vermeiden, bis beides geklaert ist

## Was weiter nicht gerechtfertigt ist
- ein harter Regressionsclaim gegen `research`
- ein Routing-/Default-Change allein aus diesem Signal

## Maschinenlesbare Quelle
- `data/proof-case-outcome-recovery.json`
