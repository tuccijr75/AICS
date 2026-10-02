# AICS

AICS is a multidisciplinary combat-sports training platform.

## Architecture

- Each combat discipline owns an independent technique database.
- AICS provides shared progression, assessment, readiness, workload, coaching, and Fight Camp infrastructure.
- The Fighting Matrix is the cross-discipline integration layer; it does not redefine the source disciplines.
- The original integrated AICS curriculum remains a separate first-party method rather than the default curriculum for every discipline.

## Discipline databases

Canonical technique data is split by discipline:

| Discipline | File | Verified records |
|---|---|---:|
| Boxing | `data/boxing.json` | 117 |
| Muay Thai | `data/muaythai.json` | 141 |
| Kickboxing / K-1 | `data/kickboxing.json` | 103 |
| Freestyle Wrestling | `data/freestyle.json` | 111 |
| Greco-Roman Wrestling | `data/greco.json` | 97 |
| Folkstyle Wrestling | `data/folkstyle.json` | 144 |
| Judo | `data/judo.json` | 138 |
| Brazilian Jiu-Jitsu | `data/bjj.json` | 245 |

Current verified total: **1,096 records**.

`data/index.json` is the database manifest and `data/sources.json` is the shared source registry.

There is intentionally **no technique-count target**. A technique is added only when it has a distinct technical purpose and survives the verification standard. Counts are expected to differ substantially by discipline.

## Progression

Every discipline database is organized into:

1. **Beginner** — foundational mechanics, positions, movement, safety, and low-prerequisite techniques.
2. **Intermediate** — timing, reaction, chaining, counters, positional development, and higher prerequisite burden.
3. **Advanced** — specialist systems, high-coordination actions, advanced counters/chains, rules-sensitive material, and verified elite variants.

The levels are AICS pedagogical levels, not replacements for official belts, ranks, or governing-body classifications.

## Verification doctrine

Canonical records must be supported by recognized governing-body curricula/classifications or current rules frameworks and by credible technical evidence such as repeated elite competition use or direct instruction from proven elite practitioners/coaches.

Each record stores its evidence grade, effectiveness basis, best-practice cues, prerequisites, safety/rules constraints, source IDs/URLs, verification status, rules-review date, and Fighting Matrix tags.

- **A:** canonical/official framework with strong competitive consistency.
- **B:** established competition-proven technique supported by convergent authoritative/elite sources.
- **C:** verified elite variant; effective but style-dependent, not a universal default.
- **D:** historical/specialized/reference-only and excluded from normal progression.

No technique is added merely to increase database size.

## Repository doctrine

This repository is the working and storage source of truth for AICS. Material technique, curriculum, rules, source, and Fighting Matrix changes must be committed here rather than existing only in chat artifacts.
