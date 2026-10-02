# AICS

AICS is being refactored into a multidisciplinary combat-sports training platform.

## Current architecture

- Individual disciplines remain technically distinct.
- AICS provides the shared progression, assessment, readiness, workload, coaching, and Fight Camp platform.
- The Fighting Matrix is the cross-discipline integration layer.
- The original integrated AICS curriculum remains separate from discipline-specific technique libraries.

## Technique database

Canonical data:

- `data/Techniques.json` — complete machine-readable technique database.
- `data/index.json` — coverage/index metadata.
- `data/sources.json` — source registry.

Current v1.0 coverage:

- Boxing — 40
- Muay Thai — 44
- Kickboxing / K-1 — 34
- Freestyle Wrestling — 32
- Greco-Roman Wrestling — 28
- Folkstyle Wrestling — 64
- Judo — 100
- Brazilian Jiu-Jitsu — 66

Total: **408 techniques**.

Technique records include evidence grade, level, canonical status, best-practice notes, prerequisites, rules/safety constraints, source links, Fighting Matrix tags, and rules-review date.

## Source doctrine

Techniques must be grounded in recognized governing-body curricula/classifications, current rules, and/or repeated elite-level direct instruction and competition validation. Individual stylistic preferences are not promoted to canonical technique doctrine without corroboration.

Restricted, historical, or rules-sensitive techniques remain available for taxonomy and research but are excluded from default progression.

## Repository use

This repository is the working and storage source for AICS going forward. Material changes should be committed here rather than maintained only in chat artifacts.
