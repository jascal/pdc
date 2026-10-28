# CLAUDE.md

See [`AGENTS.md`](./AGENTS.md) for the canonical orientation. In brief: `pdc` is the **reasoning
formalism** in the PIC family (spec only, no code and no proofs). Projective Derivation Calculus
stacks read, derive, and decode strata on PIC's incidence arrow. The decode stratum, restricted to
one derivation per atom, **is** PIC. `spec/PDC_SPEC.md` is the single source of truth.

**The one rule that governs everything here:** every claim is tagged `proved` / `empirical` / `open`,
or `witness` for a finite arithmetic example. Nothing in this repo is `proved` until an i-orca
artifact exists. Do not extend PIC's temperature invariance past the one-derivation fragment.
Do not edit `pic/spec/PIC_SPEC.md` or `pil` from here.
