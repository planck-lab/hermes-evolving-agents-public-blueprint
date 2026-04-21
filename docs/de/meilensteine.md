# Meilensteine und Gate-Matrix

## Zweck
Diese Seite uebersetzt die Meilenstein-Sprache in eine gate-orientierte Lesart der aktuellen Roadmap.

## Aktuelle Gate-Lage
| Gate ID | Name | Status | Bedeutung |
|---|---|---|---|
| G-1.5-1 | Strong Signal Detection | met | Staerkere Kandidatensignale lassen sich von schwaecherer/noisiger Evidenz unterscheiden. |
| G-1.5-2 | Signal Routing | met | Signale lassen sich in review-orientierte Artefakte ueberfuehren. |
| G-1.5-3 | Review and Inbox Bridge | met | Staerkere Signale koennen in einen Review-Pfad eingehen statt informell zu verschwinden. |
| G-1.5-4 | Adoption Candidate Path | partial | Candidate-State-Logik existiert, ist aber noch nicht proof-tauglich gehaertet. |
| G-2-1 | Adoption Mechanism | open | Ein kanonisches Adoption Object und eine State Machine fehlen noch. |
| G-2-2 | Runtime Change Traceability | open | Das System kann noch keine oeffentlich belastbare Change-Spine end-to-end zeigen. |
| G-2-3 | Measured Effect Verification | open | Noch kein public-ready Prooffall, der Signal, Change und spaetere Wirkung verbindet. |
| G-2-4 | Repeated Closed Loops | open | Closed-Loop-Infrastruktur ist noch nicht als wiederholbar statt ausnahmehaft gezeigt. |

## Empfohlener naechster Meilensteinfokus
### Phase 2A - One-path closed-loop proof
Die naechste Ausbaustufe sollte nur einen engen, auditierbaren Pfad verfolgen:
1. signal
2. review
3. adopted change
4. runtime change
5. measured effect
6. explizite Unsicherheit

## Maschinenlesbare Quelle
- `data/phase-gates.json`
