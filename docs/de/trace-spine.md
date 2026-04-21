# Trace Spine

## Zweck
Diese Seite definiert das **kanonische Lernobjekt / die Trace Spine** fuer einen engen Closed-Loop-Prooffall.

## Warum sie existiert
Ohne verknuepfte Objektkette bleiben Aussagen wie:

> signal -> review -> adopted change -> runtime change -> measured effect

Narrativ statt auditierbarer Systempfad.

## Kanonische Kette
Ein proof-tauglicher Pfad sollte genau diese Objekte verknuepfen:
1. `signal`
2. `review`
3. `adoption`
4. `change`
5. `measurement`

## Kern-IDs
- `signal_id`
- `review_id`
- `adoption_id`
- `change_id`
- `measurement_id`

## Objektrollen
### Signal
Repraesentiert den initialen Lerntrigger.

### Review
Haelt die menschliche oder governte Pruefung fest, ob das Signal weitergehen soll.

### Adoption
Repraesentiert die explizite Entscheidung, ein reviewed signal in eine begrenzte Intervention zu ueberfuehren.

### Change
Dokumentiert die runtime-wirksame Umsetzung dieser Adoption.

### Measurement
Erfasst das spaetere Beobachtungsfenster, die gemessene Wirkung, Unsicherheit und Konfundierungen.

## Mindestregeln
- jedes Objekt braucht genau einen Parent-Link zur vorherigen Stufe
- ein enger voll verknuepfter Proof-Pfad ist besser als viele halbe Ketten
- runtime-wirksame Aenderungen sollten reversibel sein
- Measurement ohne Unsicherheitsangabe ist nicht proof-tauglich

## Maschinenlesbare Dateien
- `data/trace-spine-schema.json`
- `data/trace-spine-example.json`
- `data/proof-case-scaffold.json`

## Was das ermoeglicht
Die Trace Spine ist die fehlende Bruecke zwischen:
- Evidenzdisziplin
- Gate-Logik
- Worked-Example-Struktur
- spaeteren Closed-Loop-Prooffaellen
