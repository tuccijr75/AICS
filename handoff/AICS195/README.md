# AICS current-app handoff

This directory is a **migration input** for the ongoing AICS repository conversion. It is intentionally isolated on `handoff/aics-1.9.5-current-app` so the active `main` workflow can continue uninterrupted.

## Authoritative legacy application baseline

- Release: **AICS v1.9.5**
- Artifact: `AICS195.zip`
- ZIP SHA-256: `ff399292a810929aa7304ff991382057b4d0a853d90cc27bd369cec75138e2b1`
- Release state: package/release-clean baseline
- Automated release gate: **222/222 PASS**
- App version constant: `1.9.5`
- Persistent storage namespace: `aics.v4.` for legacy compatibility

This is the application state that should be ingested when rebuilding the new AICS platform. Do not infer current behavior from older v1.3 or early v1.9 artifacts.

## Relationship to the new repository

The new repository has correctly separated the system into:

1. **Source-discipline databases** — Boxing, Muay Thai, Kickboxing/K-1, Freestyle Wrestling, Greco-Roman Wrestling, Folkstyle Wrestling, Judo, and BJJ. These remain canonical in their own independent files.
2. **AICS Platform** — shared training, progression, assessment, readiness, workload, coaching, synchronization, safety, Fight Camp, and application infrastructure.
3. **AICS Method** — the existing first-party integrated AICS curriculum: 97 techniques and the AICS-001 → AICS-400 progression spine.
4. **Fighting Matrix** — cross-discipline integration/reference graph. It may link source disciplines and the AICS Method but must not redefine or duplicate the source disciplines.

The old integrated 97-technique AICS Method must **not** be imported as if it were the new canonical database for Boxing, Wrestling, Judo, BJJ, etc. Preserve its IDs and curriculum semantics as a first-party method and map it to source-discipline records only where the relationship is explicitly defensible.

## Files in this handoff

- `CURRENT_APP_STATE.md` — operational behavior that exists in v1.9.5.
- `MIGRATION_CONTRACT.md` — semantic requirements the conversion must preserve.
- `COACHING_PHYSICS_DIRECTIVE.md` — current post-release AICS doctrine that must be implemented in the rebuild.
- `RELEASE_PROVENANCE.md` — exact release counts, gates, source layout, and hashes.
- `manifest.json` — machine-readable migration manifest.

## Conversion rule

Treat v1.9.5 as **behavioral and data provenance**, not as an instruction to preserve its monolithic implementation. Rebuild cleanly around the new repository architecture while preserving the contracts documented here.

Do not merge this handoff branch into `main` blindly. Ingest/reconcile it through the conversion workflow.
