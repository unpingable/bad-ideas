# Perimeter View / "CounterSocial without the cage" — non-sovereign perimeter intelligence as unified atproto product

**Receipt:** Surfaced 2026-05-15 alongside the OTOS temptation (`otos.md`), in a session that had already concluded *too much self-created work*. The shape: a unified AppView + labeler + community-feed suite + helpdesk + dashboard + receipts viewer + custodian audit, pitched as *"CounterSocial without the cage"* — perimeter tools without perimeter sovereignty. The failure mode differs from OTOS: OTOS was a single big-no; Perimeter View is **eight small-yeses** that sum to a multi-quarter Trust & Safety product the operator did not sign up to run. Worse, several components overlap with active repos (`labelwatch`, `gov-webui`, `verifier`, `rpp`, `atproto-feeds`, `neutral.zone`), so each piece reads as a plausible extension. Death by reasonable next steps.

## Seductive shape

A non-sovereign perimeter lens for atproto communities. AppView surface, optional label subscriptions, scoped community feeds, risk/context labels (advisory and time-limited by default), raid/coordination detectors, impersonation/handle-churn warnings, support-desk routing, moderation receipts viewer, `labelwatch`-style custodian audit. Doctrine line: *"The lens advises. The user/community chooses. The custodian leaves receipts."* Slogan candidates ranging from cursed (*"CounterSocial without the cage"*) to passable (*"A perimeter lens for atproto communities: threat-aware, receipt-bound, and non-sovereign"*).

## Real pressure

The diagnosis is correct. CoSo's useful observation — abuse as *infrastructure pressure*, not merely *bad posts* — names a real gap in atproto's default product voice. Bluesky has moderation primitives (subscribable labelers, expirable labels, account/content scope), but the layer making them coherent to normal users without enthroning the labeler is underserved. The operator already builds adjacent infrastructure (`labelwatch`, `gov-webui`, receipt machinery in `agent_gov`/`receipt_kernel`). Pressure not imagined.

## Why building it is wrong (as a unified product)

1. **Trust & Safety is a polity.** Even a "non-sovereign" T&S product needs reviewers, appeals processing, evidence handling, abuse-of-the-tool defense, and burn-out absorption. A polity of one cannot run it. *"I accidentally became Trust & Safety for a social graph because I had one good idea after midnight"* is the predictable terminus.

2. **The additive smuggle.** Each component looks like a small extension of existing work. The unified-product framing is what converts eight reasonable next steps into a multi-quarter undertaking. Bundling is the failure mode, not the components.

3. **Active-repo conflict.** Pieces overlap with `labelwatch` (123 commits / 90d), `gov-webui`, `verifier`, `rpp`, `atproto-feeds`. Bundling under a new product surface would either fork existing repos or absorb them into a charter that wasn't theirs. Both worse than letting individual repos absorb individual extensions on their own terms.

4. **Ship obligations.** The same conversation surfaced active critical paths: ship code, ship book. Perimeter View as a product is antagonistic to both for the foreseeable future.

## Useful isotope

The portable extract is the **Non-Sovereign Perimeter Doctrine** (`gnat/good_actually/non-sovereign-perimeter-doctrine.md`) — lens-advises / user-chooses / custodian-receipts, receipted *interpretation* vs receipted *emission*, advisory-and-time-limited defaults, subscribe-and-swap posture, pressure-shape vocabulary.

The threat-context label vocabulary itself (`possible-automation`, `handle-churn-risk`, `coordinated-reply-burst`, `impersonation-proximity`) is also extractable as a candidate vocabulary that *could* land as a `labelwatch` extension if and when the doctrine is dogfooded there. Vocabulary, not product.

## Bad Idea Review Board — gate criteria

Promotion from *filed* to *permitted as a discrete extension of an existing repo* requires affirmative answers to all five:

1. **Is this actually different from running a labeler?** If it quietly collapses into *"James emits safety judgments,"* it's a labeler with mood lighting. Kill it.
2. **Can it stay a lens, not a sovereign?** Context / risk / receipts / viewing tools: maybe. Binding labels or sanctions: refuse.
3. **Does it create value without becoming CoSo-in-a-trenchcoat?** Perimeter *intelligence* good. Hardened *bunker* vibe bad.
4. **Can it be useful for a polity of one?** If it only works after recruiting a moderation staff, congratulations — you invented work.
5. **Does it dogfood `labelwatch` / NQ / Wicket-shaped discipline?** Receipts, expiry, advisory state, cannot-testify boundaries, inspectable refusal. Otherwise it's *"safety dashboard"* fog.

A negative on any one revokes the permit.

## Not authorized as

- unified product, AppView, or `atproto-perimeter` mono-repo
- replacement for or wrapper around existing labeler infrastructure
- vehicle for the operator to become Trust & Safety for any social graph
- excuse to deprioritize ship-code-and-ship-book

Permitted as: the doctrine (filed separately), plus discrete component-shaped extensions of existing repos that pass the Board.

## Keeper line

> Perimeter View diagnoses a real pressure, but proposes accidental Trust & Safety as the answer. Preserve the doctrine; do not promote the mascot to product.
