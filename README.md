# pdc — Projective Derivation Calculus

The **reasoning formalism** in the PIC family. PDC defines a stratified incidence complex whose
leaf is [Projective Incidence Calculus](https://github.com/jascal/pic). One position, one derivation
per atom, vocabulary atoms only: that fragment **is** PIC. Everything above it — alternative proofs
of one atom, a chart across positions, and the step that turns a certified atom into a source — is
PDC, and its model interpretation is **open**. The one-body seam is kernel-checked in v0.2.

PDC is descriptive in the same sense as PIC. It names an algebra the other repos can measure and,
later, prove. It does not claim that a trained transformer implements the chart.

## The one-paragraph idea

Reasoning is the same incidence arrow aimed at more than the vocabulary. A **read** stratum scores
positions against positions (attention is PIC over keys). A **derive** stratum gives an atom several
bodies and aggregates them with the same temperature family PIC uses across tokens; inside an atom
that aggregate is no longer temperature-invariant, so PDC keeps two readouts, **Viterbi** (best
body) and **marginal** (semiring sum of bodies). Their disagreement is **proof fragility**. A
**decode** stratum is PIC. A derived atom becomes a residual source only by **crystallization**,
whose side condition is PIC's margin certificate. When the residual frame refuses the lemma, the
model can write the atom out as a token and read it back: that fallback is chain-of-thought.

## Where it sits

| repo | role | PDC uses it as |
|------|------|----------------|
| [`pic`](https://github.com/jascal/pic) | incidence calculus, the leaf | the specialization of the decode stratum, and the certificate PDC cites |
| [`pil`](https://github.com/jascal/pil) | frame learning | a possible later home for a crystallization objective; not a dependency of this spec |
| [`fieldrun`](https://github.com/jascal/fieldrun) | frozen-model analysis | R2 read incidences and R3 competing-copy charts in `experiments/pdc` |
| [`i-orca`](https://github.com/jascal/i-orca) | kernel proofs | R0 theorems in `examples/pdc/PDC_Derive.thy` |

## What's here

```
spec/PDC_SPEC.md    the canonical specification — strata, the two readouts, crystallization,
                    the external judgment, and the specialization back to PIC
```

The spec is the source of truth. A stopped-stage paper draft is at
[`paper/pdc_calculus.tex`](paper/pdc_calculus.tex), with a compiled PDF alongside it.
It records R0–R5 and the epistemic stop, without claiming completion of R6–R9.
This repo holds **no executable code and no proof sources**.

## Proof-status discipline

Every claim is tagged. **proved** means machine-checked in i-orca. Version 0.2 cites the strict `PDC` session
for the one-body PIC translation, readout agreement, temperature invariance, and disagreement witness. **empirical** means measured by fieldrun or pil. **open** means a
flagged hypothesis. **witness** means a finite arithmetic example written out in the spec, not a
kernel proof. v0.6 records the R5 negative result: high-margin commitments hallucinate
at 87.5% and 90% on the frozen addition domain. Those epistemic claims are retired.
R4 also corrects the negative-domain premise: zero irreducibility certificates does not
mean zero admissions. v0.7 adds a live subset-service diagnostic with measured row
skips but zero answer coverage; it does not pass R8. v0.8 records R6: generated
append improves the refused slice from 3/27 to 9/27, with no admitted cases to test
redundancy. v0.9 records negative admission learning; v0.10 records zero
coverage in the final held-out audit. Useful service and admitted-memory
transfer remain unestablished.

## License

Apache License 2.0 — see [`LICENSE`](./LICENSE).


Current evidence version: **v0.13**. R5 retired the epistemic claim;
R7 did not increase admission; the final 25-context diagnostic audit has
zero service coverage. The full north star is not achieved. The spec and
paper preserve these negative outcomes. The paper/spec are proposed in the central review PR; companion code/proof PRs
and the [full evidence release](https://github.com/jascal/pdc/releases/tag/pdc-v0.10-evidence)
are linked from `review/GROK_REVIEW.md`. PR branch links identify reviewable
changes; default-branch links become current only after merging.


## Review and evidence

- [Grok review and next-direction prompts](review/GROK_REVIEW.md)
- [Claim-to-evidence map](spec/EVIDENCE.md)
- [Original goal](review/ORIGINAL_GOAL.md) and [requirements audit](review/REQUIREMENTS_AUDIT.md)
- [Full code/results/paper archive](https://github.com/jascal/pdc/releases/tag/pdc-v0.10-evidence)
- Companion PRs: [fieldrun #147](https://github.com/jascal/fieldrun/pull/147),
  [pil #155](https://github.com/jascal/pil/pull/155),
  [i-orca #37](https://github.com/jascal/i-orca/pull/37).


v0.11 adds the [saved-frame R7 diagnostic](https://github.com/jascal/pil/blob/research/pdc-stopped-stage/docs/notes/pdc_r7_diagnostic_outcome.md):
all four procedures retain 0/75 admissions at three endpoints. Nine contexts
have matching singleton decisions without the stronger certificate; none
passes its centered-tail drift premise. This is not fresh confirmation or
a claim that larger coalitions cannot work. The v0.10 archive is unchanged.


The [Qwen3.5-4B follow-up](https://github.com/jascal/fieldrun/tree/research/pdc-qwen35-4b/experiments/pdc_qwen35_4b)
has 100/100 correct host answers and 50/50 correct heldout commitments for
both readouts. All witnesses use the full source program. This is a local
positive with no compact-circuit, learned-admission, compute-saving or
hallucination-reduction claim. It does not erase the GPT-2 negative results.
Supplemental evidence: [Qwen release](https://github.com/jascal/pdc/releases/tag/pdc-qwen35-4b-v1).

Qwen follow-up implementation/review: [fieldrun #148](https://github.com/jascal/fieldrun/pull/148).


The [saved-source singleton diagnostic](https://github.com/jascal/fieldrun/tree/research/pdc-qwen35-4b/experiments/pdc_qwen35_singletons)
finds matching singleton decisions in 100/100 cases but 0 admissions under
both sufficient guards. This separates source alignment from the stronger
certificate; it does not test larger coalitions or causal replay.
