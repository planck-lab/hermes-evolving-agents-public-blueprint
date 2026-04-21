# Proof-Case-Signal-Recovery

## Status
**Teilweise, aber sinnvoll rekonstruiert.**

Der urspruengliche Trigger-Snapshot laesst sich jetzt konkreter rekonstruieren als zuvor.
Wir haben zwar noch keine volle Task-Provenienz, aber bereits:
- das urspruengliche Signal-Artefakt
- live aggregierte Evidenz aus `state.db`
- die rohen `skill_performance`-Rows hinter dem Aggregat

## Rekonstruiertes Trigger-Bild
### Signal-Artefakt
- `agent-exchange/signals/macbook/2026-04-10-regression-kandidat-in-aktueller-skill-performance.md`

### Rekonstruiertes Aggregat
- Skill: `research`
- task_type: `null`
- Uses: `5`
- Avg Quality: `0.5`
- Success Rate: `0.0`
- Last Used: `2026-03-22 15:08:49`

### Rekonstruierte Raw Rows
Alle 5 derzeit rekonstruierbaren Rows haben dasselbe Muster:
- agent_role: `builder`
- task_type: `null`
- quality_score: `0.5`
- outcome: `partial`
- notes: `Auto-tracked dispatch`

Zeitstempel:
- `2026-03-22 13:13:34`
- `2026-03-22 13:15:37`
- `2026-03-22 14:17:46`
- `2026-03-22 14:17:46`
- `2026-03-22 15:08:49`

## Wichtigste Einsicht
Das kritische Downstream-Problem ist jetzt klarer:

> die Raw Rows sind real,
> aber sie sind nicht mit Sessions/Tasks verknuepft,
> und sie zeigen durchgehend `outcome = partial`.

Der Fall ist also nicht nur abstrakt "0% success".
Es ist ein Fall, in dem:
- alle Rows null-segmentiert sind
- alle Rows nur teilweise erfolgreich sind
- Quality- und Outcome-Semantik nicht stark genug ausgerichtet sind fuer eine harte Regressionsaussage
- das Aggregat `0% success` entsteht, weil nur `outcome = success` als Erfolg gezaehlt wird

## Was noch fehlt
- `session_id`-Linkage fuer die fuenf Rows
- Task-Level-Provenienz
- explizite Quelle der Success-/Outcome-Definition zum Signalzeitpunkt

## Was das veraendert
Schritt 1 ist noch nicht vollstaendig abgeschlossen, aber jetzt materiell staerker.
Der Signal-Block kann nun auf drei Dinge geerdet werden:
- ein explizites Signal-Artefakt
- eine explizite Aggregat-Query
- eine explizite Raw-Row-Rekonstruktion

## Maschinenlesbare Quelle
- `data/proof-case-signal-recovery.json`
