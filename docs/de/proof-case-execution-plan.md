# Proof-Case-Execution-Plan

## Ziel
Den ausgewaehlten Realfall-Scaffold in einen begrenzten **Phase-2A-Ausfuehrungspfad** ueberfuehren.

Das ist noch nicht der Proof selbst.
Es ist der operative Plan fuer einen ehrlichen ersten Proof-Versuch.

## Gewaehlter Fall
- Skill: `research`
- Haltung: Regression-/Instrumentation-Kandidat
- bevorzugter Pfad: **erst diagnostisch, nicht zuerst selektiv**

## Schritt-fuer-Schritt-Plan
### 1. Trigger-Evidenz sichern
Noetig:
- exakter Metric-/Dashboard-Snapshot
- exakte Sessions/Tasks hinter dem Alert
- aktuelle Success-/Quality-Definition

Output:
- ein voll befuelltes `signal`-Objekt mit echter Provenienz

### 2. Review durchfuehren
Noetig:
- Review-Owner
- Review-Artefakt-Ort
- explizite Alternativen

Output:
- ein befuelltes `review`-Objekt
- eine von drei Lesarten:
  - `true-regression`
  - `measurement-artifact`
  - `inconclusive`

### 3. Eine minimale reversible Intervention definieren
Bevorzugter Typ:
- Instrumentation- oder Segmentierungs-Korrektur
- kein globaler Routing-/Default-Shift

Output:
- ein befuelltes `adoption`-Objekt
- ein Rollback-Plan

### 4. Aenderung implementieren und loggen
Noetig:
- exakter Implementierungspfad
- Aktivierungszeitpunkt
- betroffene Metriken/Views

Output:
- ein voll instanziiertes `change`-Objekt

### 5. Begrenzte Post-Change-Wirkung messen
Noetig:
- Baseline-Vergleich
- Beobachtungsfenster
- Mindestschwelle
- Disconfirmation Rule

Output:
- ein befuelltes `measurement`-Objekt
- ein ehrliches finales Urteil:
  - echte Regression
  - Messartefakt
  - inconclusive

## Guardrails
- keine globalen Default-Shifts
- keine Skill-Demotion auf duenner Evidenz
- keine Erfolgsstory ohne Unsicherheitsangabe
- eine enge reversible Intervention reicht

## Hauptabhaengigkeiten
- truth-aligned Trigger-Snapshot
- benannter Review-Owner
- konkrete diagnostische Aenderung
- Beobachtungsfenster
- Mindest-Evidenzschwelle

## Maschinenlesbare Quelle
- `data/proof-case-execution-plan.json`
- `data/proof-case-readiness-check.json`
