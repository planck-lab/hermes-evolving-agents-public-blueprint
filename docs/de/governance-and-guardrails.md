# Governance and Guardrails

## Kernprinzip
Das Ziel ist **kontrolliertes Lernen bei kontrollierbarem Risiko**.

## Governance-Haltung
Die folgenden Punkte sind Designentscheidungen, keine empirischen Fakten:
- kein Vollautonomie-Ziel
- konservative Progression in Richtung Anpassung
- Human-in-the-Loop vor relevanten runtime-wirksamen Änderungen
- Reversibilität und Auditierbarkeit vor stärkerer Selection-Logik

## Warum das wichtig ist
Ein System kann adaptiver werden, ohne unkontrollierbarer zu werden.
Dieser Blueprint geht davon aus, dass Lernqualität ohne Rollback, Traceability und Review nicht genügt.

## Praktische Guardrails
- Empfehlung vor Mutation bevorzugen
- kleine Blast Radius vor breitem Rollout
- Beobachtung von Interpretation von Intention trennen
- keine Claim-Aufwertung bei überwiegend privater oder dünner Evidenz

## Öffentliche Leseregel
Wenn eine Aussage auf dieser Seite normativ klingt, sollte sie meist gelesen werden als:

> Governance-Entscheidung dieses Projekts,
> nicht als universelles Gesetz für Agentendesign.
