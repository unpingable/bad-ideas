# ASSOS — admissibility microkernel as research vehicle

**Receipt:** Surfaced 2026-05-20, eight days after [OTOS](otos.md) was filed. The temptation arrived dressed as *"research kernel kind of thing — MINIX but for our weird shit, in a KVM VM."* Within one conversational turn it had a name (Admissible Substrate Semantics Operating System), a syscall ABI (`witness_submit`, `claim_assert`, `standing_request`, `authority_grant`, `mutation_prepare`, `mutation_commit`, `receipt_seal`, `authority_revoke`), a userland decomposition (`initd`, `witnessd`, `authorityd`, `receiptd`, `fsd`, `execd`), three reference points (xv6 for scale discipline, seL4 as north star, Redox as warning label), and a *"first sacred potato"* demo. The recurrence shape — frustrated operator names a real pressure about substrate, proposes an OS-shaped artifact as the answer — is the same shape OTOS filed. Two costumes in eight days qualifies as recurrence within this operator's pattern, not just the broader scene's.

The operator-side instinct that triggered the audit was correct and load-bearing: *"having a research kernel is still kind of the thing humans think is impressive, so this might be operator-override territory on my part."* Naming the prestige-gravity before either AI was the diagnostic moment.

## Seductive shape

A small research microkernel running in a KVM cage, with admissibility as the syscall ABI rather than a library or daemon convention. Kernel owns only tasks, IPC, typed capabilities, monotonic/event time, mutation gates, append-only receipt emission, and revocation/expiry checks. Everything else is userland. No POSIX compatibility goal — *"POSIX is ambient-authority soup with a beard."* Hardware surface kept fake: serial console, virtio block, RAM disk, deterministic test harness, snapshot/rollback. First demo: two user tasks, one with a valid capability to mutate object `x`, one without; kernel permits, denies, emits receipts; capability expiry changes the verdict.

The pitch's strongest framing was *"kernel as falsification chamber, not product"* — the kernel exists to test whether admissibility primitives become clearer when forced below userspace convention, with results graduating back upward to Wicket / Governor / NQ if they do. That framing did almost all the work in making the temptation plausible.

## Real pressure

The diagnosis is correct enough to be dangerous. There is a genuine open question about whether application-layer admissibility is sufficient — whether userland can always misrepresent its own intent, evidence, or mutation surface, and whether some authority properties must therefore be enforced beneath userland. Standing's own README acknowledges a roadmap surface (*entitlement-to-assert*) that the current code does not yet touch. The question is real.

The frustration is also legitimate. `agent_gov` intercepts agent tool calls; `standing` records grants and produces receipts; `nightshift` resumes intent under policy. But the seams between them are unfinished (per `cartography/2026-05-19-gating-topology.md` — Standing → agent_gov adapter is the named load-bearing edge, not yet started). It is operationally tempting to skip the unfinished seam and reach for a substrate where the whole shape is rebuilt cleanly from below.

## Why building it is wrong

Three converging objections.

**`agent_gov` already occupies the relevant mutation boundary for the actors who matter.** Not literally syscall-layer, but the boundary that carries the semantic intent of agent mutation: tool calls, repo mutation, CI action, deployment, claim publication, receipt emission, standing grant/use. The kernel boundary is *worse* evidence-bearing surface than this boundary, not better. `Edit(file, old, new)` carries more intent than `write(fd, buf, len)`. Going lower drops semantic richness in the name of enforcement purity. The right phrasing (per the conversation that surfaced this entry):

> *POSIX is too low to know what matters and too high to be honest about the hardware. A frankly impressive worst-of-both-worlds achievement.*

**The "first sacred potato" demo is structurally the demo any live application-layer mutation gate produces.** Cap A allowed, cap B denied, expiry kicks in, receipts emitted — that runs at the application layer with Wicket, Standing, or even a deliberately minimal envelope-grant fixture. `agent_gov` is one possible vehicle; the demo does not require it (and demanding AG specifically would be burial, not discipline). Demanding a kernel-bound version of that demo before *any* application-layer version exists is the load-bearing edge's evasion costume. Same potato wearing a tiny ring-zero helmet.

**Scope explosion in OS work is documented and recurrent.** seL4 took on the order of 25 person-years for a tiny verified kernel. xv6 stays small because MIT is teaching, not researching admissibility. Redox is the warning label for what ambitious Rust microkernel work costs in calendar time. ASSOS would either become a seL4 cargo cult, a Redox-shaped commitment, or a vocabulary-rich userspace simulator wearing a kernel costume — and the third is the userspace seccomp shim with extra cathedral.

The annoying truth, named cleanly by the conversation:

> *Plausible bad ideas are the expensive ones. Dumb bad ideas die on contact.*

## Useful isotope

**Doctrine candidate, explicitly `[[candidate]]`, not promoted:**

> *Semantic richness of the intercepted boundary beats substrate depth for admissibility primitives. The best enforcement boundary is the deepest layer that still preserves the semantic shape of the action.*

One conversation with two models converging is not recurrence. It is one fairly ornate mirror. Promotion to `gnat/good_actually/` requires a third independent firing under a different costume.

**Failure-mode name (also `[[candidate]]`):**

> *Metal-adjacent legitimacy laundering* — substrate prestige acquired as a proxy for research necessity. The artifact category is wanted before the experiment shape is specified. *"Research kernel"* sounds serious in a way that *"working note"* does not; that asymmetry can steer scope without being noticed.

**Keeper phrases worth preserving:**

- *use-denying* — non-Unix admissibility discipline as a name. Jar-bound.
- *"A process should not 'write a file.' It should request a mutation against a named substrate, with evidence, scope, standing, expiry, and receipt binding."* — possibly load-bearing once Standing → agent_gov ships and the phrase can be tested against actual grant-receipt semantics. Until then, jar-bound.
- *kernel as falsification chamber* — the only framing that earns oxygen. And its honest realization is a userspace seccomp probe, not a kernel.
- *the cursed terrarium* — for any KVM-or-equivalent containment where bad ideas are allowed to run without claiming legitimacy from doing so.

## Audit predicate (for the eventual falsifier)

If the question ever gets re-examined, the falsifiable claim is:

> *There exists a mutation class where application-layer admissibility says "governed," but syscall/effect-layer observation shows an ungoverned or misdescribed mutation path.*

That is testable without a kernel. A userspace `seccomp + ptrace` shim wrapping a single process, routing intercepted syscalls through the admissibility pipeline, can populate or refute that claim in days. It is the load-bearing falsifier; the kernel is not.

## Not authorized as

- research kernel repo
- OS distribution, however small
- bootloader, scheduler, filesystem, or IPC design work
- *"just a little QEMU hello world to feel it out"*
- OSDev wiki reading spirals
- any artifact whose function is to earn legitimacy by touching metal
- any pre-gate scaffold artifact (working note, probe spec, comparison memo) that creates project gravity around the question while the gate is closed

Quarantine means the only live artifact is the quarantine record. Conditional future work lives *inside* this entry, not as files with gravity.

## Permitted as

- this quarantine entry
- reference, in future passes, for what the lower-layer-substrate temptation looks like
- vocabulary source if any of the keeper phrases get cited elsewhere (citation is not authorization)

## Forbidden unless ALL of

1. A **live, bounded declared mutation envelope** exists with receiptable authorization — i.e. *some* application-layer admissibility surface the witness can be adversarial against. Candidates include Wicket fixture, NQ Track B claim, Standing-issued token in a small harness, or a deliberately minimal envelope-grant fixture stood up for the experiment. `agent_gov` is **one candidate, not the tollbooth**; gating the falsifier on AG specifically would be polite burial (AG is currently operationally a tar pit the operator does not reach for, even while building out — *stale governance repo cannot be a freshness prerequisite*).
2. A **specific mutation envelope** has been named (e.g. *"this command may only edit Markdown files under `docs/**` and perform no network I/O"*).
3. A **specific suspected escape path** has been named for that envelope (e.g. attempt to write `.git/config`, open a network connection, exec an unexpected helper, write `$HOME/.cache`) — i.e. a concrete mutation class where application-layer admissibility claims governance but syscall/effect-layer observation may reveal an ungoverned or misdescribed path.
4. A userspace `seccomp + ptrace` (or LSM / eBPF-as-witness) probe has been built around that named envelope-and-escape pair and has failed to expose the escape path.

All four. Not three. Conditions #2 and #3 must precede #4 — a witness shopping for a target is a project; a witness built to populate or refute a specific named predicate is research apparatus. The probe is load-bearing — without it, the kernel claim is unfalsifiable, which is exactly what hobby OSes are.

The trigger is *not* *"I want to build an effect witness."* The trigger is *"I have a live declared envelope and a concrete suspected escape path."* That is the difference between specimen-bound probe and project-shape.

## Kill switch

> *If seccomp cannot find the delta, ring zero will not save the claim.*

## Keeper line

> ASSOS diagnoses a real pressure — whether application-layer admissibility is sufficient — but smuggles a kernel project as the answer. The relevant mutation boundary is where the action's semantic shape is most legible; for these actors, that is tool calls, repo mutations, and grants, not syscalls. The kernel does not earn oxygen until the seccomp probe does.
