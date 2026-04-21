# Proof-Case-Measurement-Spec

## Status
**Initiale begrenzte Messung abgeschlossen.**

Das ist ein ehrliches Step-5-Artefakt, aber weiterhin **eng begrenzt**.
Es behauptet keinen vollwertigen longitudinalen Nachweis.

## Messdesign
### Baseline Comparator
Weil kein konservierter historischer Pre-Gate-Candidate-Stream vorliegt, ist der ehrlichste Comparator:

> derselbe live `state.db`-Snapshot
> einmal durch das ungated SQL-Ranking betrachtet
> und einmal durch den gated Live-Emissionspfad.

### Warum dieser Comparator akzeptabel ist
Er tut nicht so, als haetten wir Evidenz, die wir nicht haben.
Stattdessen beantwortet er die kleinste sinnvolle Frage:

> unterdrueckt das ausgewaehlte Gate den bekannten Thin-Evidence-Fall auf dem aktuellen Live-System tatsaechlich?

## Begrenzte Live-Beobachtungen
### 1. Ungated Counterfactual Snapshot
Aus dem live 30-Tage-`skill_performance`-Ranking ist der Top-Kandidat ohne Gate weiterhin:
- `skill_name = research`
- `task_type = null`
- `uses = 5`
- `avg_quality = 0.5`
- `quality_coverage_pct = 100.0`
- `success_rate = 0.0`
- `last_seen = 2026-03-22 15:08:49`

Lesart:
Ohne Gate sitzt derselbe rekonstruierte Thin-Evidence-Fall weiter oben im Regression-Candidate-Pool.

### 2. Gated Live Path
Der Lauf von:
`python3 scripts/generate_regression_draft_from_db.py --json`

ergibt:
`No regression candidate found for current filters.`

Lesart:
Mit aktivem Live-Gate wird dieser Fall nicht mehr als Regression Candidate emittiert.

### 3. Direkte Gate-Checks
Die live beobachteten Gate-Gruende sind:
- fuer `task_type = null`:
  `task_type fehlt; zuerst Segmentierung sichern, nicht Skill bewerten`
- fuer `task_type = research` mit `avg_quality = 0.5` und `success_rate = 0%`:
  `Outcome-Definition wirkt inkonsistent ...`

Lesart:
Die Unterdrueckungslogik passt exakt zur Proof-Case-Begruendung.

## Threshold
Diese Messung gilt als minimal informativ, wenn:
- ein ungated Kandidat existiert
- der gated Pfad ihn unterdrueckt
- und der Unterdrueckungsgrund zur Segmentierungs-/Outcome-Konsistenzlogik passt

Diese Schwelle ist erreicht.

## Disconfirmation Rule
Die Messung waere widerlegt, wenn:
- der gated Pfad den `research` / `task_type = null`-Kandidaten trotzdem emittiert
- oder der Gate-Grund nicht zur dokumentierten Logik passt

## Beobachteter Effekt
### Gestuetzt
- der ausgewaehlte Fall eskaliert nicht mehr in emitierte Regression-Candidate-Behandlung
- das Gate ist auf dem Live-System verhaltensrelevant aktiv
- die aktuelle Evidenz stuetzt eine **instrumentation-first**-Lesart

### Noch nicht gestuetzt
- breite Downstream-Verbesserung ueber die Zeit
- wiederholte Reduktion von False-Positive-Review-Load
- ein vollwertiger end-to-end Closed-Loop-Proof

## Verdict-Posture
**Teilweise gestuetzt; measurement-artifact leaning.**

Beste aktuelle Lesart:
> das ausgewaehlte Gate ist aktiv und unterdrueckt den rekonstruierten Thin-Evidence-Fall erfolgreich,
> aber der Gesamtbeweis bleibt begrenzt und darf nicht ueberverkauft werden.

## Hauptlimitierung
Das ist ein **counterfactual same-snapshot comparison**, kein konservierter historischer Pre/Post-Stream.
Genau das ist die ehrlich offenzulegende Grenze.

## Maschinenlesbare Quelle
- `data/proof-case-measurement-spec.json`
