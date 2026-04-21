# Proof Case Intervention Selection

## Status
**Ausgewählt.**

Die erste gewählte Intervention ist ein **konservativer Gate-Mechanismus auf der Selection-Ebene**:

> Ein Skill-Level-Regression-Kandidat soll nicht erzeugt oder als Evidenz behandelt werden,
> wenn Task-Segmentierung fehlt
> oder wenn Erfolgsrate und Quality-Signal auf eine inkonsistente Outcome-Definition hindeuten.

## Entscheidungsfrage
Welche einzelne reversible Intervention sollte für diesen Proof Case zuerst verwendet werden?

## Betrachtete Optionen
### 1. Selection-Layer-Gate vor Regressionsurteil — **ausgewählt**
- unterdrückt Regressions-/Champion-Urteile bei fehlendem `task_type`
- unterdrückt auch bei erkennbarer Outcome-Definitions-Inkonsistenz
- klassifiziert den Fall stattdessen zuerst als Instrumentation-Thema

Warum diese Option gewinnt:
- kleinste reversible Änderung
- passt direkt zum rekonstruierten Evidenzbild
- senkt sofort das Risiko von False-Positive-Skill-Demotion
- mutiert keine Routing-Defaults

### 2. Aggregierte Success-Semantik neu definieren — nicht ausgewählt
Würde direkt die sichtbare `0% success`-Metrik adressieren, ist aber semantisch riskanter und verschlechtert die Vergleichbarkeit historischer Aggregate, bevor Segmentierung sauber ist.

### 3. Historische Rows zuerst backfillen — nicht ausgewählt
Später sinnvoll, aber für die erste begrenzte Intervention zu breit und zu rekonstruktionslastig.

### 4. Runtime-Outcome-Taxonomie zuerst ändern — nicht ausgewählt
Möglicherweise später wertvoll, aber für den ersten Proof-Case-Schritt breiter als nötig und nicht erforderlich, um dünne Evidenz jetzt zu stoppen.

## Gewählte Intervention
### Name
**Segmentation and outcome-consistency gate before regression judgment**

### Exakte Aussage
Bevor ein Skill-Level-Regression-Kandidat erzeugt oder verwendet wird, muss `task_type` nicht leer sein; zusätzlich wird der Kandidat blockiert, wenn `success_rate` und Quality-Coverage auf eine inkonsistente Outcome-Definition hindeuten.

### Change Surface
- `internal/hermes-agent/scripts/skill_signal_gates.py`
- `internal/hermes-agent/scripts/generate_regression_draft_from_db.py`

### Warum das der richtige erste Move ist
- Es adressiert die tatsächlich rekonstruierte Schwäche: fehlende Segmentierung plus irreführende aggregierte Success-Semantik.
- Es ist eng, reversibel und auditierbar.
- Es verhindert Eskalation aus dünner Evidenz, ohne so zu tun, als sei das historische Provenienzproblem gelöst.

## Was diese Intervention **nicht** tut
- sie definiert historische Success-Semantik **nicht** neu
- sie repariert alte `session_id = null`-Rows **nicht**
- sie demotet den Skill `research` **nicht**
- sie ändert keine globalen Routing-Defaults jenseits dieses Gates

## Rollback-Mechanismus
Rollback ist geradlinig:
- Selection-Gate-Aufruf entfernen oder revertieren
- altes Verhalten der Regression-Draft-Erzeugung wiederherstellen

Kanonische Rollback-Referenzen:
- `scripts/skill_signal_gates.py`
- `scripts/generate_regression_draft_from_db.py`

## Approval-Posture
- **Selection Spec freigegeben von:** project owner
- **Datum:** 2026-04-21
- **Freigabeumfang hier:** Intervention auswählen und dokumentieren
- **Nicht Teil dieses Schritts:** dedizierte Proof-Case-Runtime-Änderung ausführen/loggen

## Wichtige Nuance
Im Live-Code existiert bereits eine analoge konservative Gate-Form.
Damit ist die konzeptionelle Intervention nicht mehr vage.

Aber für diesen Proof Case bleibt Step 4 offen, weil noch fehlt:
- ein dedizierter Change Record
- ein Aktivierungszeitpunkt für den Proof Case
- ein begrenztes Post-Change-Beobachtungsfenster

## Praktische Konsequenz
Step 3 ist jetzt **ready**:
- eine Intervention ist ausgewählt
- der Approval Owner ist bekannt
- Rollback-Referenzen sind bekannt

Der Engpass verschiebt sich damit zu Step 4:
**Change Logging und explizite Proof-Case-Ausführung.**

## Maschinenlesbare Quelle
- `data/proof-case-intervention-selection.json`
