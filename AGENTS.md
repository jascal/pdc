# AGENTS.md — orientation for `pdc`

`pdc` is the **reasoning formalism** in the PIC family: Projective Derivation Calculus. It holds
**no executable code and no proof sources** — the spec and paper draft. The leaf it specializes to is [`pic`](../pic). Proofs,
when any exist, belong in [`i-orca`](../i-orca). Measurements belong in [`fieldrun`](../fieldrun)
or [`pil`](../pil). Read [`README.md`](./README.md) first, then `spec/PDC_SPEC.md`.

## What this repo is for

To write down, once, the stratified incidence complex suggested by PIC's own scope limits: several
bodies per atom, a chart across positions, two readouts where temperature invariance fails, and a
crystallization rule that turns a certified atom into a source. PIC remains the decode stratum.
PDC does not replace it and does not edit it.

## Files

- `spec/PDC_SPEC.md` — **the single source of truth.** Strata, native notation, the specialization
  lemma (now proved in the cited R0 scope), crystallization, the external judgment, the open list.
- `paper/pdc_calculus.tex` — a draft recording the R0–R8 stop and the later Qwen follow-up
  through the engineering correction. It does not close R9.

## The discipline that must not slip

**Every claim is tagged `proved` / `empirical` / `open`, plus `witness` for a finite example.**

- Tag a PDC statement `proved` only with a checked named i-orca lemma. R0 lives in
  `i-orca/examples/pdc/PDC_Derive.thy`, strict session `PDC`; see spec v0.10.
- A PIC theorem may be cited as the side condition of a PDC definition. The citation is not a PDC proof.
- The temperature-invariance lemma of PIC applies only in the one-derivation fragment. Do not extend it
  to the derive stratum. The counterexample is a witness already in PIC and is now kernel-checked by R0;
  cite the exact witness lemmas without extending temperature invariance.
- Crystallization is a definition whose numeric hypothesis is PIC's margin certificate. It is not
  evidence that models crystallize.
- Chain-of-thought as context-frame fallback is **open**.
- Proof fragility is a defined diagnostic. R3 and R5 measure finite rates; cite their
  exact runs without inferring a functional form.
- R5's epistemic stop rule has fired. Do not advertise theory soundness from its
  failed margin instrument or count the full R6–R9 stack as complete. R8-H measures row skips
  but abstains everywhere; do not turn zero commitments into a passing rate.
- R6 supports append only on its observed refused slice; there are no admitted
  cases. Do not claim the full memory split or a benefit of actual crystallization. The final diagnostic audit consumed the 25 reserved contexts and abstained on all; do not describe them as untouched.
- Do not claim ProbLog semantics. The marginal readout is a semiring sum over bodies, which
  double-counts shared subderivations.

## When you change this repo

- A theorem lands in i-orca about a statement in the spec → cite the `.thy` file and lemma, tag it
  `proved`, bump the spec version.
- A measurement lands in fieldrun or pil → cite the experiment, tag it `empirical`, bump the version.
- Keep the specialization to PIC exact: one position, at most one body per atom, vocabulary atoms,
  no external theory. If that fragment drifts from `pic/spec/PIC_SPEC.md`, fix the citation, not PIC.

## What NOT to do

- Do **not** add code, tests, or Isabelle theories here.
- Do **not** edit `pic`, `pil`, `fieldrun`, or `i-orca` from a PDC change unless the task says so.
- Do **not** introduce native notation beyond `spec/PDC_SPEC.md` §2. The borrow list is PIC's `▷`,
  `⟦·⟧`, `⊢_γ`, and `⊕_T`. The new names are `▷_h`, `α_T`, `Vit`, `Mar_T`, `↷`, and `⊨`.
- Do **not** treat the Eiffel-tower appendix as data. It is an illustration.
