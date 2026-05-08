# Δbase / DeltaDB — temporal admissibility substrate

**Receipt:** Pushed at least ten times in various costumes. Each angle fails differently — LMDB + Datalog VM, embedded triple store, SQLite + temporal extension, custom property graph — but the temptation persists across failures. The danger is not novelty; the danger is recurrence under plausible justification.

This is the inaugural entry. **Operator override accepted:** a recurrent substrate temptation with multiple prior passes qualifies as receipt-bearing even without active implementation, because the failure mode this repo catches is precisely "designs that become tempting because they correctly diagnose a real pressure, then smuggle in an implementation project larger than the problem."

## Seductive shape

A purpose-built append-only temporal fact store with Datalog querying. Immutable assertions `(time, entity, attribute, value)`. Governor rules reject writes that violate admissibility invariants. Time-travel via snapshots. Transitive-dependency closure for impact analysis. Lean integration through metaprogramming. Built on LMDB plus a custom Datalog VM. *"Under 5,000 lines of Rust."* Maps cleanly onto the corpus/governor/admissibility model because that model **is** a versioned property graph with rule-based rejection.

## Real pressure

Existing substrates (SQLite, Datomic, generic graph DBs, Soufflé) do not express temporal admissibility cleanly. The work has a genuine shape mismatch with off-the-shelf stores: append-only assertions, governor-based rejection, Lean-derived rules, dependency-impact queries that need to compose with admissibility. No existing substrate makes that combination natural. The pressure is not imagined.

## Why building it is wrong

Scope explosion is reliable here. A Datalog VM with stratified negation, recursion, and temporal semantics is a research project, not a weekend. Add LMDB transaction management, secondary indices, edge iteration, materialization, truth maintenance, retraction semantics, Lean FFI, and a query language — and "5,000 lines" becomes 25,000 plus a README apologizing to future archaeologists.

The "tentative state, run governors, rollback if invalid" pattern handwaves itself into "commit first, retract later," which is exactly where the governor becomes decorative. Maintenance cost is permanent: a custom database is forever.

## Useful isotope

The real product is not a database. It is a **query-shape inventory** for temporal admissibility — enumerate the actual queries the work needs that existing substrates fail to express cleanly. The inventory itself is the substrate-shopping criterion.

Most likely outcome: the inventory motivates a 200-line layer on top of SQLite or DuckDB, not a new database. Possible outcome: the inventory proves the shape mismatch is structural and a small DSL (not a database) would help. Building the database skips the diagnostic step.

## Forbidden unless

All four hold:

1. The query-shape inventory has been completed and recorded as a separate artifact.
2. At least two existing substrates have been attempted (with thin adapters) and demonstrably fail to serve those queries.
3. The inventory proves the shape mismatch is structural, not just unfamiliar vocabulary.
4. The alternative cost (build new database) is provably lower than the alternative cost (force existing substrate to fit), with both costs estimated by something other than the model that wants to build the database.

Until all four hold, the answer is *"name the queries first."*

## Keeper line

> The correct lesson of Δbase is not "build a database"; it is "name the query shapes before substrate panic becomes architecture."
