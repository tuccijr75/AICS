# AICS v1.9.5 release provenance

## Release identity

- Version: **1.9.5**
- Artifact: `AICS195.zip`
- Artifact size: **1,242,972 bytes**
- SHA-256: `ff399292a810929aa7304ff991382057b4d0a853d90cc27bd369cec75138e2b1`

Recovered from the project's release-clean file set.

## Source-of-truth layout inside the release

- `source-data/core.json` — curriculum, progression, assessments, quizzes, Fight Camp legality, application doctrine
- `source-data/biomechanics.json` — 97 technique-specific mechanics/faults/safety
- `aics-app.js` — shared Student/Trainer application engine
- `aics-data.js` — generated core runtime data
- `aics-biomechanics.js` — generated biomechanics bundle
- `desktop.css` / `mobile.css`
- `build-data.py`
- `build-review.py`
- `validate.js`
- `mechanics-audit.py`
- `sw-audit.js`
- `package-audit.py`
- `browser-audit.py`
- `release.py`
- `index.html`, `student.html`, `trainer.html`
- PWA manifests/icons, `sw.js`, and portable `_headers`

## Canonical counts from source data

- lessons: **400**
- techniques: **97**
- biomechanics records: **97**
- assessments: **40**
- quizzes: **400**
- modules: **61**
- belts: **8**
- Fight Camp technique records: **31**
- biomechanics crosswalk entries for Fight Camp: **31**

## Key source hashes

- `source-data/core.json`: `044a142a3dcaea5cd704bbe54a1144e51785c2c71116be2e31e23e81467ac922`
- `source-data/biomechanics.json`: `ed7b7e1238b5b4b467d59daca1b41cd960461870c2f643d0425118b6cc53ee50`
- `aics-app.js`: `ea67aae7d0a5f6143000abcd64ae626907dfead3b99777cf6315fb26d91592f6`
- `aics-data.js`: `a438da5071d9609253b8a30602eaf3fd05427c9e4bc4aeb725df6752223c6f68`
- `aics-biomechanics.js`: `b91ef858172ad3069c710fd5bc027e8357852881293542d6573150043c80f7c3`
- `validate.js`: `671a579d75352ff7260b9baaacd760379b2f84ece7241f5165bf0a6ace476a58`
- `mechanics-audit.py`: `6e9d70a9fda8d08abb8559144f9aaf440c722f880aeb1b55eb91898f711d3c38`
- `release.py`: `f8a3a1ae6887da3fdf5d8b361b73c885dc60df2780fd5891547271ed018bfd06`

## Release gates

The final v1.9.5 package reports:

- 95 application/integrity/security/data checks
- 91 mechanics/technique/rules checks
- 15 service-worker checks
- 21 package/deployment checks
- **222/222 PASS**

Syntax, generated-data consistency, package completeness, deterministic review generation, and clean-package revalidation passed.

This is a **source/package certification**. Browser/device visual acceptance and host-enforced header behavior are separate deployment concerns.

## Notable v1.9.5 hardening

- explicit structured Fight Camp legality metadata for all 97 techniques
- legality resolved by action/target/state/bout format instead of technique-name inference
- fail-closed behavior for unknown legality
- Fight Camp plan invalidation after relevant rule changes
- lesson-linked knowledge checks
- Student lazy biomechanics loading / Trainer eager loading
- hardened service worker
- validated IANA calendar time zones
- application/data mismatch fail closed
- strict CSP-compatible application
- desktop/mobile accessibility hardening
- package/deployment audit coverage

## Compatibility

The legacy runtime retains `aics.v4.` as its local-storage namespace for migration compatibility. A new implementation may replace the storage design, but it should provide an explicit migration/import path for existing AICS records rather than silently abandoning them.
