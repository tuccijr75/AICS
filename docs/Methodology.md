# Technique Database Methodology

## 1. One discipline, one database

AICS does not maintain a combined technique register. Boxing, Muay Thai, Kickboxing/K-1, Freestyle Wrestling, Greco-Roman Wrestling, Folkstyle Wrestling, Judo, and Brazilian Jiu-Jitsu each own an independent canonical database.

The Fighting Matrix may reference records across those databases, but it never changes a discipline's native technical identity.

## 2. No quota / no filler

There is no minimum or target number of techniques.

A record is included only when all of the following are true:

1. The technique has a distinct technical purpose rather than being a renamed duplicate.
2. Its mechanics can be supported by a recognized technical authority and/or convergent elite-level instruction and competition use.
3. It is demonstrably effective within the discipline or a clearly identified specialist/elite variant.
4. Current rules and safety implications are documented.
5. Its prerequisites and progression level can be defended.
6. Its best-practice cues describe repeatable mechanics rather than personal preference.

A database grows only when new material passes those gates.

## 3. Evidence grades

- **A — Canonical:** governing-body, Kodokan, or other official technical framework plus strong competition/elite consistency.
- **B — Competition-proven:** established, rules-compatible technique supported by convergent elite/systematic sources where no complete official syllabus exists.
- **C — Elite variant:** proven and mechanically coherent, but style-dependent rather than a universal default.
- **D — Historical/specialized:** legitimate reference material but excluded from normal lesson generation.

Default curriculum generation uses A and B. C is an advanced optional variant. D is reference-only.

## 4. Beginner → intermediate → advanced

**Beginner**
- foundation, stance, posture, movement, safety
- core attacks/defences/positions
- low prerequisite burden
- mechanics that must exist before chaining or specialization

**Intermediate**
- reliable use of fundamentals under reaction
- combinations, counters, transitions, positional chains
- increased timing, decision-making, and prerequisite requirements

**Advanced**
- specialist systems and variants
- multi-step reaction chains
- high-coordination or high-timing techniques
- rules-sensitive or elevated-risk material
- verified elite variants that should not be universal beginner doctrine

These are AICS pedagogical levels, not official belt/rank substitutions.

## 5. Technique record contract

Every active record contains:

- stable technique ID
- discipline
- technique name
- category / subcategory
- AICS level
- record type
- evidence grade
- canonical status
- effectiveness basis
- best-practice cue set
- prerequisites
- rules/safety requirements
- source IDs and URLs
- verification status and basis
- last rules/source review date
- Fighting Matrix tags

## 6. Source hierarchy

Use the strongest available evidence in this order:

1. current governing-body rules, curricula, classifications, and technical education
2. recognized institutional technical standards
3. direct instruction from historically/competitively elite practitioners and elite coaches
4. repeated high-level competition use
5. peer-reviewed biomechanics, injury, motor-learning, or technical-tactical research where relevant

A single famous athlete's preference is not sufficient to create universal doctrine.

## 7. Effectiveness standard

"Effective" means the technique has a defensible competitive or technical role in its native discipline. It does not mean every athlete should use it.

Specialist techniques remain specialist records. Athlete morphology, stance, ruleset, strategic system, and prerequisite competency may determine whether a verified technique is appropriate.

## 8. Rules and safety

Rules change. Every discipline database carries the applicable current rules source, and legality-sensitive records must be reviewed when rules change.

Restricted or historical techniques may remain for taxonomy/research but must be marked and excluded from normal progression. Joint locks, chokes, throws, head-impact work, and other higher-risk material require discipline-appropriate supervision and progressive practice.

## 9. Quality control

Before promotion into a canonical database, automated validation checks:

- valid schema and discipline
- unique technique IDs
- unique technique names within the discipline
- correct beginner/intermediate/advanced placement
- source references resolve
- current rules source is attached
- verification status is present
- effectiveness basis is present
- best-practice cues are substantive
- safety/rules field is non-empty

Automated validation does not replace technical review; it prevents structural and provenance failures.

## 10. Current scope

The eight discipline databases are the source layer. MMA/IMMAF material is reserved for the integration layer: striking-to-clinch, strike-to-shot, cage/fence work, takedown-to-control, ground-striking interactions, and other cross-discipline transitions.
