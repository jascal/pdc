# PDC — build the derivation complex

**Goal document, 2026-10-24.** Lives at the workspace root by convention (plan docs stay out of
project repos). Companion to [`pdc/spec/PDC_SPEC.md`](pdc/spec/PDC_SPEC.md) v0.1. Tags follow
program discipline: everything below is **open** until an artifact says otherwise. A finite
arithmetic example is a **witness**. A PIC theorem cited as a side condition stays a PIC theorem.

## North star

**Make a transformer's multi-step reasoning a PDC chart that can be checked.** For every atom the
system commits, the artifact names the readout (Viterbi or marginal), the winning body, the margin,
whether the two readouts disagree, whether the atom was crystallized into the residual or appended
as a token, and — once an external theory is loaded — whether that theory affirms it. Abstain when
the certificate does not apply. The one-body, one-position, vocabulary-only fragment is
kernel-checked to be PIC.

The product is a **DerivationBundle**: the reasoning-shaped successor of fieldrun's incidence dump.
Analyze exports it, i-orca proves the fragment and the admission rule, pil learns frames that admit
more atoms, and a decidable theory grades the bundle. PIC remains the decode stratum. PDC does not
replace it.

## Why this is the program, not a feature

PIC already says what one next-token readout is: incidences, one monomial per token, a temperature
that does not change the greedy choice, certificates that are exact linear predicates. The scope
notes in `pic/spec/PIC_SPEC.md` §3.1 and §6.5 are the construction site. They mark, as outside the
leaf, the objects a reasoning calculus has to own:

- several bodies of one atom, where `⊕_T` sits inside the answer and greedy decoding parts company
  from the marginal;
- the position-indexed program whose least fixpoint would be a generated sequence;
- a judgment other than host agreement.

PDC v0.1 names those objects and stops. Building it out means each name acquires an artifact in the
repo that already owns that kind of work. The spec repo stays a spec.

The bet, in one line: **attention is PIC over positions, a derivation is a chart of bodies, memory
is either crystallization or an appended token, and truth is a third judgment beside the host.**

## The finished stack

```
𝒯  external theory          ⊨  /  hallucination  /  miss
        │
chart (derive)              Vit(a) , Mar_T(a) , fragile_T
        │
memory                      a ↷ s     or     append(generated | tool)
        │
read                        i ▷_h j    →  value write, a source
        │
decode                      PIC        L(v), ⊢_γ, margin certificate
```

A committed answer is a path through this stack with every edge recorded. A bare token is an
incomplete bundle.

## Where the work lives

| repo | owns | does not own |
|------|------|----------------|
| `pdc` | `spec/PDC_SPEC.md`. Version bumps when a tag changes | code, proofs, experiments |
| `i-orca` | kernel statements named in the rungs below | measurements, the external theory |
| `fieldrun` | read-incidence dump, chart export, the DerivationBundle on frozen models | frame learning |
| `pil` | a crystallization objective and its soundness invariants | the definition of `⊢` or `⊨` |
| a finite checker (Soufflé program, or a small theory file the bundle is graded against) | `𝒯` for one decidable domain | a general world model |

No local-path imports across repos. fieldrun emits a documented bundle; pil and the checker consume
that format. `pdc` cites the artifact and bumps the spec.

## Rungs

Each rung names the gate that decides it. A pre-registered negative result closes the rung. A
plateau does not become a necessity claim.

### R0 — The seam is a theorem

Formalize PDC §1 in i-orca. Four restrictions (one position, at most one body, vocabulary atoms, no
`⊨`). Prove that `α_T` equals PIC's `L` under those restrictions, and import decode
temperature-invariance. Prove the witness of PDC §3.2: two bodies at score 0 against one body at
score 1/2, marginal picks the first at `T = 1`, Viterbi picks the second. Prove the one-body
direction of the intended lemma (PDC §3.3).

**Gate.** Lemmas in a named `.thy`, zero `sorry`, cited from `pdc` at a version bump. The spec's
"specializes to PIC" line may then be tagged **proved** for exactly those statements.

### R1 — An evaluator that refuses a bare answer

A small executor, living in fieldrun (or a Soufflé program it emits), takes a finite body table and
returns `Vit`, `Mar_T`, and `fragile_T`. It has no code path that returns an atom without a readout
name.

**Gate.** On the §3.2 witness, fragility is true and the two winners are the ones written in the
spec. On a generated family of one-body programs, the selected atom is independent of `T` and matches
a PIC argmax on the same scores. The executor's output is the kernel statement of R0 on those
instances, not a second semantics.

### R2 — Read-PIC on a frozen model

fieldrun emits `i ▷_h j` for named heads, and the value mixture those incidences define. Keep PIC's
three-way split: algebraic identity of the mixture with the head's value write, numerical error, and
decision agreement of the `T → 0` head with the head's actual argmax key. Report all three. "The
head is PIC" is reserved for the case where the first is an identity under a stated convention and
the third is measured.

**Gate.** One architecture, a pre-registered set of heads and positions. Publish the three numbers.
If decision agreement is not 1.00 on that set, the read-stratum identification is restricted to the
heads where it holds, and the others stay inside the forge tax. That restriction is a successful
rung.

### R3 — Real circuits as bodies

On a task with a known circuit (copy, induction, a fixed n-gram), record each firing explanation as
a body with a bracket. The bundle stores the body set, not only the winning token. Fragility is
computed on the rival atoms the task cares about.

**Gate.** Pre-register the task, the body generators, and the rival set. Report the rate at which
Viterbi's atom equals the model's token, the rate at which the marginal's atom equals it, and the
fragility rate. A fragility rate of zero is a result. Inventing bodies after seeing the token is not
a gate.

### R4 — Crystallization is an oracle with two expected answers

Wire `pic/spec/forge_tax_certificate.md` as the admission rule `a ↷ s`. Run it in both directions
under a pre-registration:

- a **positive** domain, constructed so a small coalition suffices and a faithful frame exists (the
  explicit feasible instance already sketched in the forge-tax note, scaled to a finite synthetic
  corpus);
- a **negative** domain, the held-out regime where the first sample certified 0/40, re-run at a size
  fixed in advance.

**Gate.** The positive domain admits, with a stored feasible frame. The negative domain returns
Farkas duals or a recorded "still empty at this N." Admission on the positive side and refusal on
the negative side are the rung. A learner that "crystallizes" without this oracle is a different
project.

The kernel packaging — an admitted source reproduces the coalition's decision inside the `δ` the
margin certificate allows — is an i-orca lemma (PDC spec §9.3). Its numeric content is
`decode_margin_certified`. The new statement is the packaging. **Gate:** the lemma exists, and the
R4 oracle checks the same inequality the lemma assumes.

### R5 — One theory, one finite domain

Pick a decidable `𝒯` before looking at host tokens. Candidates, in increasing reach: a lookup table
on a template (capital-of, SVO roles), a small arithmetic checker, a type judgment. Grade every
committed atom on the domain:

| verdict | condition |
|---------|-----------|
| affirmed | recorded `P ⊢ a` and `𝒯 ⊨ a` |
| hallucination | recorded `P ⊢ a` and `𝒯` does not affirm `a` |
| miss | `𝒯 ⊨ a` and no recorded body decides `a` |
| fragile truth | `𝒯 ⊨ a`, marginal selects `a`, Viterbi does not |
| abstain | margin `≤ 2δ`, or the rival set was not the one the certificate covers |

**Gate.** A frozen table of counts on a domain whose size is fixed in the pre-registration. The
soundness claim under test is: among non-abstaining commitments with margin `> γ`, the
hallucination rate is below a bar set in advance. Missing the bar retires the claim for that
`γ` and that domain. Completeness (no misses) is reported and is not required to pass.

### R6 — Two memories, one two-hop task

A task of two hops. Hop 1 produces an intermediate atom. Hop 2 needs it. Three arms, same host,
same contexts:

1. **re-derive** — hop 2 sees only the original context;
2. **crystallize** — hop 2 may use `s` only if R4 admitted it;
3. **append** — hop 1's atom is written as a `generated` position and hop 2's read heads may attend
   to it.

**Gate, pre-registered.** The open hypothesis in PDC §6 says append helps where crystallization is
refused, and is redundant where admission succeeds. Score hop-2 agreement with `𝒯`, conditional on
the R4 verdict. Confirm, narrow, or retire the hypothesis on that split. A tool arm, tagged `tool`,
appends only atoms with `𝒯 ⊨ a` and is the upper bound the generated arm is measured against.

### R7 — Learn admission

pil objective, on top of the existing decode loss: increase the number of atoms that pass the R4
rule, subject to PIC's learning invariants (decode soundness, the proved per-step margin guard, and
`FP ≥ W`). The frame moves. The gates of the measured host stay fixed on any arm that claims to be
about a frozen computation. An arm that also trains gates is encode-side work and is labeled as such.

**Gate.** On the R5 domain, admission rate rises by a margin fixed in the pre-registration, hop-2
agreement does not fall, and the certified-margin mass does not fall below the `2δ` guard. A frame
regularizer that moves `FP/W` and not admission is a negative result, in the family of pil's
existing negative knobs, and counts as closing the arm.

### R8 — Serve the bundle

One end-to-end artifact on the R5 domain:

```
in certificate  → atom, readout name, body, margin, fragile bit,
                  memory tag (residual | appended | none),
                  theory bit (affirmed | hallucination | miss | fragile-truth)
out of certificate → abstain
```

**Gate.** Against the full host decode on the same domain: agreement of non-abstaining answers with
the host above a pre-registered bar, hallucination rate among those answers below the R5 bar, and a
measured skip (positions or vocabulary rows not scored) that the abstention actually buys. The
certificate is the bundle. A token without the bundle is not a served answer.

### R9 — The write-up

`pdc` spec at the version that cites R0–R8. A paper that expands the spec, the way
`pic/paper/pic_calculus.tex` expands PIC, with the same tags. No functional form for fragility, for
admission rate, or for chart depth versus layer depth, unless a pre-registered measurement supports
one. PDC spec §9.6 stays open unless that measurement exists.

**Gate.** A reader can check every `proved` tag against a `.thy` lemma and every `empirical` tag
against a named run. The Eiffel-tower appendix remains an illustration.

## Success criteria

Ascending. Later criteria are meaningless if an earlier stop-rule has fired.

1. **Seam.** R0 and R1. PDC's one-body fragment is PIC, in the kernel and in the executor.
2. **Read.** R2. At least one head family on one architecture meets the algebraic identity and a
   reported decision-agreement rate. Heads that fail are named and left in the forge tax.
3. **Bodies.** R3. A real circuit has a body table. Fragility has a rate, including zero.
4. **Memory oracle.** R4. Admission is feasible on the positive domain and certified-impossible on
   the negative sample's domain, at the pre-registered size.
5. **Truth.** R5. On one finite `𝒯`, hallucination among non-abstaining high-margin commitments is
   below the pre-registered bar, or the bar is missed and the claim is retired in public.
6. **Two hops.** R6. The crystallize-versus-append split matches the hypothesis, or the hypothesis
   is revised to the split that was measured.
7. **Learning.** R7. Admission rate moves under the decode invariants, or the arm joins pil's list
   of knobs that do not beat plain training.
8. **Service.** R8. A bundle that abstains, cites a body, and beats an uncertified token on
   hallucination at a measured compute saving.
9. **North star.** Criteria 1–8 together, on one held-out slice of the R5 domain that no rung used
   for threshold selection. Every non-abstaining answer carries readout, body, margin, memory tag,
   and theory bit. The one-body fragment still cites R0.

## Known traps, named in advance

- **Temperature laundering.** Reporting a single winner on a multi-body atom. The executor's type
  has a readout. Reviews reject bundles that lack one.
- **ProbLog by nickname.** `Mar_T` double-counts shared subbodies. Disjointification is a separate
  rung if it is ever built, and it is not implied by R1.
- **Body shopping.** Explanations written down after the token is known. R3 freezes the body
  generators first.
- **Reconstruction slang.** "Recon = 1.00" stays decision agreement on a stated candidate set.
  Algebraic identity and numerical logit error are separate lines in every R2 table.
- **Forge-tax vacuity.** Freeing the gates makes behavioral irreducibility collapse, which is why
  R4 freezes measured writes. An arm that trains gates does not get to use the word crystallized.
- **Certificate topology.** Balls, interval bounds, and uniform `δ` over a whole vocabulary are
  already known to go vacuous on GPT-2 (PIC §5.8). R5 and R8 use the exact linear predicates
  (pairwise margin, half-space slack). A new uniform bound needs a new argument.
- **Plateau as proof.** A failed admission sweep, a flat fragility rate, or a learner that does not
  move admission is a measurement. It is not "models must compose" and it is not "chain-of-thought
  is required."
- **Spec drift.** `pdc` cites `pic` by section. If PIC's margin certificate or temperature lemma
  changes statement, R0 and R4 re-state against the new text before any tag is kept.
- **Illustration as data.** Appendix A of the PDC spec is not a pilot result.

## Stop rules

- R0 cannot state the degeneration. The seam is the wrong specialization. Stop and rewrite §1 before
  any measurement rung.
- R2 finds no head whose value write is the incidence mixture, on the pre-registered set. Read-PIC
  is retired. Later rungs treat attention as PIC's uninterpreted gate.
- R4's positive domain is infeasible. The admission rule is not the linear program described. Fix
  the rule before R6.
- R5's hallucination bar is missed by a wide margin on a domain the theory decides completely.
  High margin is not an epistemic instrument there. R8 may still serve host agreement; it may not
  advertise `⊨`.
- R6 shows append and crystallization indistinguishable on the pre-registered split. The memory
  hypothesis is retired. The chart and the two readouts stand on R0–R5 alone.

## What this program does not build

- A general world model. `𝒯` is a finite decidable theory chosen per domain.
- A claim that trained transformers implement systematic tensor-product binding. PIC already
  measured the opposite on GPT-2. PDC may *target* a binding code; the host measurement is separate.
- An expressivity theorem relating chart depth to layer depth (PDC §9.6), until the step function
  is less abstract than PIC's.
- Code, proofs, or experiments inside the `pdc` repo.
- Edits to `pic/spec/PIC_SPEC.md` except a citation, and only when a PDC theorem has to point back.
  PIC's leaf stays the leaf.

## Milestones

- **M0 — now.** Spec v0.1 at `pdc/spec/PDC_SPEC.md`. This goal. No theorem, no measurement.
- **M1 —** R0 landed in i-orca, spec bumped, the one-body fragment tagged proved for the translated
  statements only.
- **M2 —** R1 executor and R2 read dump. The three-way reconstruction table exists for one model.
- **M3 —** R3 body rates and R4 oracle, positive and negative domains both reported.
- **M4 —** R5 theory table. First number for hallucination at a stated margin.
- **M5 —** R6 two-hop split. The memory hypothesis confirmed or retired.
- **M6 —** R7 learning arm and R8 served bundle.
- **M7 —** R9 paper. Criterion 9 on a held-out slice, or a public stop at the rung that fired.

**The bet, in one line:** the decode is already a calculus; reasoning is that calculus pointed at
positions, at alternative bodies, and at a theory the model does not own — and each of those
pointings can be made to pass or fail in public.
