# ATopher / Gopher-on-atproto — small-web revival as unified bridge product

**Receipt:** Surfaced 2026-05-18 with the opener *"scratching that itch again: gopher."* Recurrence is the qualifying signal — small-web / Gopher / Gemini revivals are an established recurring temptation across the broader scene, and the operator named the itch as already-prior. DeepSeek's pamphlet escalated the riff into a reborn-protocol blueprint ("ATopher"): Lexicon family, AppView, Relay-indexed search, gopher-to-atproto bridge translator, "the small web with the tools of a decentralized future." Chatty filtered the kernel back to its actual size — *a small-web publication profile for ordered, human-curated menus over ATProto records* — then named the remaining hazard.

Classification: **RPP-native.** The relevant doctrine already lives in `rpp/docs/RPP-000-publication-vs-validity.md` (`projected ≠ issued`, projection/publication profile split). ATopher is a specimen forcing an RPP boundary, not a new doctrine source.

## Seductive shape

A Gopher-shaped publication+navigation grammar layered on atproto's identity/discovery rails. `zone.gopher.menu`, `zone.gopher.document`, `zone.gopher.link`, optional `zone.gopher.collection`. AppView as reader. A bridge service that fetches `gopher://` content and republishes it as DID-authored atproto records. Slogan candidates: *"a calmer corner of the decentralized future,"* *"plaintext was right the first time,"* *"a publication profile for ordered menus."* Naming flurry already starting (*ATopher*). Pitch: minimal, intentional, reuses existing atproto plumbing — *not* a new protocol, just a tiny lexicon family.

## Real pressure

The diagnosis is correct on two axes. (1) The small-web aesthetic — ordered menus, plaintext, no algorithmic feed, no engagement loop — names a real gap that adjacent active repos (`rpp`, `wlp`, `labelwatch`, `gov-webui`) gesture at in their own register. (2) The atproto substrate genuinely is good for the *notice / discovery* layer of small-web objects. RPP-000 itself ranks atproto as the best public-notice substrate. Pressure not imagined.

## Why building it is wrong (as a unified product)

1. **Bridge laundering is the load-bearing hazard.** A bridge that fetches `gopher://` content and republishes it as a DID-authored atproto record produces records that are *signature-authentic* (the bridge operator's DID signed them) but *authorially misattributed* (the original gopher writer signed nothing in atproto). RPP-000 already names this as `projected ≠ issued`. Of the eight imagined components, the bridge is the only one where laundering can hide inside otherwise-valid records — it is the dangerous part independent of the rest of the design.

2. **The kernel is much smaller than the product.** The useful object chatty named is a tiny lexicon family for ordered menus. That is not a protocol revival, an AppView project, a "Veronica reimagined" indexer, or a bridge service. Bundling those together is OTOS-shape: a coherent "ATopher" identity recruiting effort larger than the primitive justifies. The naming flurry is the tell.

3. **Ship obligations.** Same standing context: ship code, ship book. ATopher as a product is antagonistic to both. ATopher as a forcing specimen for an RPP gap-spec is small and useful.

## Useful isotope

The portable extract is **not** a fresh `gnat/good_actually/` doctrine. The relevant doctrine already lives in RPP. The narrower extract — **bridge provenance for projected artifacts** — earns a RPP gap-spec stub: `docs/gaps/GAP-005-BRIDGE-PROJECTION-PROVENANCE.md`.

Core invariant: *projection into a substrate is not publication by the projected subject.* Required markers for bridged/imported records: `mirrored`/`imported`, `fetched_at`, `source_uri`, `source_claimed_owner`, `bridge_operator`, `verification_status`, `original_protocol`, `custody_basis`.

Composition (in the gap-spec, not here): WLP may validate artifact/transition shape but does not mint publication standing; non-sovereign perimeter doctrine's *receipted interpretation ≠ receipted emission* is the same shape one register down.

## Not authorized as

- unified "ATopher" product, AppView, distro, or mono-repo
- gopher→atproto bridge service (the dangerous part)
- new Lexicon family until at least one existing operator-owned surface dogfoods ordered-menu publication and finds an actual gap
- new protocol revival vehicle
- excuse to deprioritize ship-code-and-ship-book

Permitted as: the RPP gap-spec (filed separately), plus the menu-lexicon shape as a candidate to be picked up *only* when an actual surface needs it.

## Forbidden unless

Promotion beyond "specimen + gap-spec" requires all of:

1. An existing operator-owned surface has a real need for ordered-menu publication that no current vocabulary serves.
2. The bridge-provenance gap-spec (GAP-005) has been ratified and the markers are usable.
3. The proposed implementation is a discrete extension of an existing repo (most likely `rpp`), not a new product or a new repo.
4. Ship-code and ship-book obligations are not the active critical path.

Until all four hold, the answer is *"the gap-spec is the deliverable; the lexicon is a candidate."*

## Keeper line

> ATopher diagnoses a real pressure, but the dangerous bit is the bridge — not the menu. Preserve the RPP gap-spec; do not promote the mascot to product. Gopher is the raccoon that found the door.
