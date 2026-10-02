# AICS conversion migration contract

This contract defines what the new AICS build must preserve while allowing a clean reimplementation.

## 1. Preserve identities and meaning

The legacy AICS Method must preserve:

- `AICS-001` → `AICS-400` ordered lesson identity
- all 97 AICS Method technique identities
- mastery/progression semantics
- assessment and promotion semantics
- evidence ownership
- safety/medical constraints
- Fight Camp overlay semantics

Do not renumber or silently reinterpret these IDs during conversion. If the new schema changes, use an explicit migration map.

## 2. Keep source disciplines independent

The new repository's discipline databases are the canonical technical source layer.

Do **not** flatten the 97 integrated AICS Method techniques into those discipline databases. A Method technique may reference one or more source-discipline records, but the source record remains owned by its discipline.

No technique is added to a source database merely to satisfy a target count.

## 3. AICS Platform versus AICS Method

Platform responsibilities include:

- athlete/student identity and roster
- readiness
- medical holds and clearance
- workload
- training occurrence ledger
- curriculum/progression engine
- assessments and mastery
- Trainer authority
- secure synchronization
- Fight Camp rule verification and plan invalidation
- calendars
- backups
- UI/PWA/deployment infrastructure

AICS Method responsibilities include the integrated 400-lesson curriculum, its technique graph, pedagogical sequencing, and method-specific assessments.

The Platform must be able to host the AICS Method without making it the default curriculum for every source discipline.

## 4. Progression invariants

Required invariants:

- new student begins at the first canonical lesson
- immediate predecessor locking is enforced
- completion evidence is bounded to the actual occurrence
- optional zero-minute components do not fabricate completion requirements
- calendar/reminders cannot progress curriculum
- belt/rank is never auto-awarded by lesson completion
- promotion is a separate explicit Trainer decision
- candidate/capstone requirements remain enforceable
- Student data cannot overwrite Trainer-owned promotion/mastery/assessment/medical state

## 5. Safety invariants

- RED readiness changes or blocks the effective plan; it is not cosmetic.
- Persistent medical holds supersede daily readiness.
- Independent concurrent holds remain independent.
- Contact-risk return requires appropriate clearance.
- Load governance remains continuous across ordinary training and Fight Camp.
- Rules-sensitive actions fail closed when legality is unknown.

## 6. Sync/security invariants

Preserve or supersede with equally strong guarantees:

- stable athlete IDs
- field ownership
- source/parent revision checks
- pairing epoch/generation checks
- stale/replay rejection
- authenticated encryption for exchanged packets/backups
- long-lived pairing secret is not embedded in invitations
- Trainer backup secret is independent
- PIN is labeled convenience access control, not encryption
- no silent cloud upload of athlete records

If a new backend is deliberately introduced later, that is a separate architecture decision and requires an explicit privacy/security migration.

## 7. Fight Camp invariants

- Fight Camp is an overlay on curriculum/progression.
- Action-specific tactics require verified event rules.
- Legality must use structured action/target/state/bout-format data.
- Free text cannot authorize a technique.
- Rule changes invalidate stale tactical plans.
- Athlete strategy is athlete-specific, not hard-coded to the historical Long-Frame profile.
- Competition calendars cannot control lesson progression.

## 8. Build/release invariants

The new build should retain equivalent gates for:

- schema/data validity
- stable IDs and references
- full curriculum reachability
- no duplicate/broken knowledge checks
- mechanics/legality consistency
- security/sync invariants
- service-worker behavior
- package completeness
- JavaScript/source syntax
- deterministic generated artifacts
- clean-package revalidation

Do not call a rebuilt release certified merely because source tests pass; browser/device/live-host acceptance is a separate gate.

## 9. Ingestion priority

When reconciling old and new material, use this order:

1. current repository doctrine and independently verified source-discipline records
2. this handoff's v1.9.5 behavioral contracts
3. AICS Method legacy curriculum/mechanics with stable IDs
4. post-v1.9.5 directives in `COACHING_PHYSICS_DIRECTIVE.md`
5. older artifacts only for provenance or migration compatibility

Where these conflict, do not silently merge them. Record the conflict and choose explicitly.
