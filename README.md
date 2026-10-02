# AICS

AICS is being refactored into a multidisciplinary combat-sports training platform.

## Current architecture

- Individual disciplines remain technically distinct.
- AICS provides the shared progression, assessment, readiness, workload, coaching, and Fight Camp platform.
- The Fighting Matrix is the cross-discipline integration layer.
- The original integrated AICS curriculum remains separate from discipline-specific technique libraries.

## Technique database

The current technique database is stored in:

- `data/Techniques.json` — canonical machine-readable source.
- `data/Techniques.xlsx` — human-review workbook.

Current v1.0 coverage:

- Boxing
- Muay Thai
- Kickboxing / K-1
- Freestyle Wrestling
- Greco-Roman Wrestling
- Folkstyle Wrestling
- Judo
- Brazilian Jiu-Jitsu

Technique records include evidence grade, level, canonical status, best-practice notes, prerequisites, rules/safety constraints, source links, and Fighting Matrix tags.

## Source doctrine

Techniques must be grounded in recognized governing-body curricula/classifications, current rules, and/or repeated elite-level direct instruction and competition validation. Individual stylistic preferences are not promoted to canonical technique doctrine without corroboration.

Restricted, historical, or rules-sensitive techniques remain available for taxonomy and research but are excluded from default progression.

## Repository use

This repository is the working and storage source for AICS going forward.
