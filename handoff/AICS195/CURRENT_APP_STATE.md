# AICS v1.9.5 current application state

## Canonical training spine

The release-clean legacy app contains:

- **400 ordered curriculum lessons**
- stable **AICS-001 through AICS-400** IDs
- **97 curriculum techniques**
- **97 technique-specific biomechanics records**
- **40 assessments**
- **400 lesson-linked knowledge checks**
- **61 modules**
- **8 belt definitions**
- **31 Fight Camp technique records**

Progression uses strict immediate-predecessor locking. A new student starts at lesson 1. Calendar events cannot select or advance curriculum lessons. Instructor overrides do not silently bypass canonical progression.

## Student / Trainer architecture

AICS v1.9.5 has separate Student and Trainer entry points on shared application logic.

Student owns evidence such as completed sessions, readiness, training evidence, and submitted progress. Trainer owns belt/rank decisions, mastery approvals, assessments, promotion decisions, medical clearance, and override authority.

Synchronization is field-owned and revision-aware rather than whole-state replacement.

## Synchronization integrity

The current application carries the hardened sync model developed across v1.9.x:

- stable student IDs
- source revisions / parent revisions
- pairing epochs
- stale and replay rejection
- safe device re-pairing
- Student packets cannot overwrite Trainer-owned authority
- Trainer merges preserve Student-owned evidence
- invitation/setup flows do not expose the long-lived pairing secret

Encrypted packets and backups use authenticated encryption. Local PIN is explicitly a convenience lock, not equivalent to storage encryption.

## Readiness, safety, and medical holds

Readiness affects the effective session rather than displaying advisory text only.

The architecture includes persistent, concurrent medical holds. Daily readiness cannot clear a persistent hold. Contact-risk participation remains blocked until the appropriate Trainer-recorded qualified-healthcare clearance is present.

The safety model covers neurological symptoms, significant musculoskeletal injury, healthcare-directed restrictions, post-procedure restrictions, and other Trainer-entered medical restrictions.

## Workload and occurrence integrity

Training evidence uses a unique training-occurrence model so a formal session and its curriculum evidence are not double-counted as separate hours.

The aggregate load governor spans formal training, roadwork, strength, micro work, Fight Camp, fight day, and post-fight. Session-RPE load, contact exposure, hard rounds/impact rounds, strength intensity, and roadwork intensity are part of workload history.

## Fight Camp

Fight Camp is an overlay; it does not replace the underlying curriculum.

v1.9.5 hardened legality so action-specific plans are available only when required event rules are verified. Legality is resolved from structured fields such as action domain, target region, position/state, bout format, and technique decision. Free text is documentary only.

Unknown/incomplete legality fails closed for action-specific planning.

Fight Camp plan fingerprints invalidate stale plans when verified rules change.

The old single-athlete/Long-Frame profile is not the generic runtime model; athlete tactics are modeled per athlete.

## Nutrition and athlete-specific planning

Nutrition targets are estimates and require real athlete inputs. The system does not invent a competition deadline. Dietary preferences, allergies, GI tolerance, cultural food considerations, and budget are inputs. Under-19 automated weight-loss prescription is blocked.

## Calendars

Personal and competition calendars are generated from the athlete's actual schedule. UIDs are deterministic and time zones are validated IANA zones. Calendar events are reminders only and never drive progression.

## Local-first privacy model

The legacy application is local-first and browser-based.

- Operational state is stored locally.
- There is no requirement for a remote plaintext athlete database.
- Personal records move between Student and Trainer only through explicit encrypted packet exchange/export.
- LocalStorage itself is **not encrypted at rest**; device security and the optional PIN should not be misrepresented as full application-level encryption.
- Trainer backups use a secret independent from the Student pairing mechanism.

## Release / deployment behavior

The release includes strict CSP-compatible code, separate desktop/mobile styles, PWA manifests, a hardened service worker, lazy Student biomechanics loading, eager Trainer biomechanics loading, application/data version mismatch fail-closed behavior, and deployment/package audits.

The release package passed its automated package gates. Live-host/browser acceptance remains a separate deployment gate and should not be inferred from source-gate success alone.
