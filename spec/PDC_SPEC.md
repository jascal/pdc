# PDC: Projective Derivation Calculus — Definition

**Status:** canonical specification (v0.12). This document defines PDC precisely enough that a later
proof in i-orca, or a later measurement in fieldrun or pil, has a statement to land on. It is a
formalism repo in the PIC family. It holds no code and no proofs.

> **v0.12 (2026-10-25)** — a user-authorized Qwen3.5-4B follow-up
> has 100/100 correct host answers and 50/50 correct heldout commitments
> for each readout. Every witness is the full source program. The independent
> reference matches 100/100; 678300 body/probe annotations and 200 commitments
> pass the independent audit. This is full-program coverage on a small
> instruction-template split, not compact circuits, memory transfer, learned
> admission, hallucination reduction over its already-perfect host, or compute
> savings. Model/architecture/tokenizer/chat format all differ from GPT-2.
> [Protocol and outcome](https://github.com/jascal/fieldrun/tree/research/pdc-qwen35-4b/experiments/pdc_qwen35_4b).
> Original GPT-2 negatives and the consumed-slice restriction remain intact.
>
> **v0.11 (2026-10-25)** — a separately frozen, saved-frame R7 diagnostic
> compares original singleton admission, half absolute floor, highest-source
> plus bias, and random-source plus bias procedures. Every arm remains 0/75
> at initialization and both saved endpoints; protected outputs are 183/183.
> Nine contexts have a matching singleton decision without the certificate;
> no singleton passes the centered-tail drift premise. The absolute floor
> alone cannot explain all refusals. Larger coalitions and causal effects of
> the optimizer constraint remain untested. This is not fresh confirmation.
> [Diagnostic outcome](https://github.com/jascal/pil/blob/research/pdc-stopped-stage/docs/notes/pdc_r7_diagnostic_outcome.md).
> The original v0.10 archive is unchanged; the diagnostic is in PIL PR #155.
>
> **v0.10 (2026-10-25)** — the final reserved 25-context diagnostic
> audit evaluates the unchanged R8-H policy once. Both readouts abstain on
> all 25 contexts; nonempty coverage fails. It checks 127,725 body/probe
> annotations with zero discrepancy and skips 1,213,850 native output-row
> calls. Host agreement and hallucination among commitments are undefined.
> [Final audit](https://github.com/jascal/fieldrun/blob/master/experiments/pdc/FINAL_AUDIT_RESULTS.md).
> The held-out reservation is consumed. R8 and criterion 9 remain unmet;
> this version documents a stopped stage, not the north star.
>
> **v0.9 (2026-10-25)** — R7 completes two preregistered 200-proposal
> learning arms. Both retain 0/75 admissions while preserving all 183 protected
> full-host decisions. The admission-rise gate fails; no budget extension is made.
> Independent endpoint reconstruction agrees within 5.41e-13.
> [R7 outcome](https://github.com/jascal/pil/blob/master/docs/notes/pdc_r7_outcome.md).
> Useful R8 coverage and the final held-out audit remain open; R5 stays retired.
>
> **v0.8 (2026-10-25)** — R6 measures 27 two-hop triples, all in the
> native-frame refused stratum. Re-derive and crystallize each score 3/27; generated
> and tool append each score 9/27. The 22.22-point generated-append gain supports
> the preregistered refused-slice comparison; the empty admitted stratum leaves
> redundancy and admitted replay untested. Native/NumPy agreement is 108/108.
> [R6 outcome](https://github.com/jascal/fieldrun/blob/master/experiments/pdc/R6_RESULTS.md).
> A two-hop graph retains 117 checked decode nodes and 108 provenance paths.
> R5 stays retired; R7, useful R8 coverage and the final held-out audit remain open.
>
> **v0.7 (2026-10-25)** — a preregistered host-only service continuation R8-H
> executes actual native subset scoring over 1,703 lexical probes. It saves 3,641,550
> native output-row dot calls across 75 contexts, but both readouts abstain on all
> 75, so the nonempty-coverage gate fails and host agreement is untested.
> [R8-H outcome](https://github.com/jascal/fieldrun/blob/master/experiments/pdc/R8H_RESULTS.md).
> The original R8 truth/host gate and the full north star remain unmet. R5 stays retired;
> R6/R7 and the reserved held-out audit remain unperformed.
>
> **v0.6 (2026-10-24)** — R5 triggers its preregistered epistemic stop restriction.
> On 75 fixed addition contexts, certified commitments hallucinate at 7/8 (Viterbi)
> and 9/10 (marginal), above the advance 10% bar and 25% wide-miss threshold.
> [R5 outcome](https://github.com/jascal/fieldrun/blob/master/experiments/pdc/R5_RESULTS.md).
> The claim is retired on this model/domain. Candidate-wise score preservation is
> **proved** by `PDC_Admission.pairwise_source_preserves_decision`; theory soundness
> does not follow. R6–R8 and the final held-out audit remain open. A stopped-stage
> paper draft is at `paper/pdc_calculus.tex`; it does not close the full R9 gate.
>
> **v0.5 (2026-10-24)** — R4 oracle experiment concluded: 64/64 positive admissions;
> exact singleton refusal duals on the explicit three-context control; 80/80 free-frame
> reducible Qwen positions, with 11/80 first-witness margin admissions.
> [R4 outcome](https://github.com/jascal/pil/blob/master/docs/notes/pdc_r4_outcome.md).
> The historical 0/40 was zero irreducibility certificates, not zero admissions. The
> expected negative-admission premise for that regime is retired; no universal refusal
> there is proved. R5–R9 remain open.
>
> **v0.4 (2026-10-24)** — R2 read identification on 108 frozen GPT-2
> head/query instances and R3 competing-copy body charts on 16 contexts are **empirical**;
> [R2_RESULTS](https://github.com/jascal/fieldrun/blob/master/experiments/pdc/R2_RESULTS.md),
> [R3_RESULTS](https://github.com/jascal/fieldrun/blob/master/experiments/pdc/R3_RESULTS.md).
> R4 source-admission packaging is **proved** in i-orca `PDC_Admission.thy`, strict
> session `PDC`; its numerical oracle measurements and R5–R9 remain open.
>
> **v0.3 (2026-10-24)** — R1 finite executor and instance checks in fieldrun,
> [`R1_RESULTS.md`](https://github.com/jascal/fieldrun/blob/master/experiments/pdc/R1_RESULTS.md).
> The checked witness and 1,280 one-body evaluations pass; these are arithmetic instances,
> not model measurements. R2–R9 remain open.
>
> **v0.2 (2026-10-24)** — R0 kernel-checked in i-orca, session `PDC`,
> [`PDC_Derive.thy`](https://github.com/jascal/i-orca/blob/master/examples/pdc/PDC_Derive.thy).
> Singleton full-coalition specialization, one-body agreement and temperature invariance,
> softmax order, and the two-body disagreement are **proved** over the domains below.
> All measurement rungs and source admission remain **open**.
>
> **v0.1 (2026-10-24)** — initial definition. Three strata (read, derive, decode), two readouts
> (Viterbi, marginal), proof fragility, crystallization, an external judgment `⊨`, and the
> specialization under which PDC is PIC. No claim in this version is kernel-checked. The finite
> disagreement of the two readouts is a **witness**. Everything else new is **open**.

| repo | role | PDC treats it as |
|------|------|------------------|
| [`pic`](https://github.com/jascal/pic) | the incidence calculus | the **leaf**. Decode, one body per atom, is PIC |
| [`pil`](https://github.com/jascal/pil) | frame learning | a later place a crystallization objective could live |
| [`fieldrun`](https://github.com/jascal/fieldrun) | frozen-model analysis | a later place read-incidences and fragility could be measured |
| [`i-orca`](https://github.com/jascal/i-orca) | kernel proofs | a later place PDC statements could be checked |

PIC's tag rule applies here. **proved** means machine-checked in i-orca. **empirical** means measured
by fieldrun or pil. **open** means a flagged hypothesis. **witness** means a finite score table
written out below, checked as arithmetic, not kernel-checked. Citing a PIC theorem names a side
condition. It does not prove a PDC statement.

---

## 0. One-paragraph summary

PDC is a stack of PIC's incidence arrow. **Read** scores positions against positions, one head at a
time. **Derive** gives an atom several bodies and combines those bodies with `⊕_T`, so the
temperature sits *inside* the atom. **Decode** scores vocabulary tokens from a residual and is PIC.
Inside the derive stratum the argmax need not be independent of `T`, so PDC keeps two readouts of
every atom: **Viterbi**, the best body, and **marginal**, the semiring sum of the bodies. They
disagree on a finite witness (§3.2). An atom becomes a source only by **crystallization**, whose
numeric hypothesis is PIC's margin certificate. A separate judgment `𝒯 ⊨ a` records truth in an
external theory. Host agreement stays `⊢`.

---

## 1. Specialization — when PDC is PIC

This is the seam. A PDC program is a **PIC program** when all four hold:

1. **One position.** The chart has a single span, and read-incidences are not evaluated. Sources are
   given (an extensional table of block incidences, or a gated encode), which is PIC's encode.
2. **At most one body per atom.** `deriv(a)` is empty or a singleton.
3. **Vocabulary atoms.** Every atom is a token `v ∈ V`, with frame vector `U_v` in the residual
   space `ℋ = ℝ^d`.
4. **No external theory.** `⊨` is not interpreted. The only decision judgment is `⊢`.

Under (2) and (3) the derive-stratum annotation collapses by definition:

> `α_T(v) = ⟦P⟧(v) ⊗ b_v = L(v)` when `deriv(v) = {P}`, and the body `P` is the full source coalition.

`T` then appears only in the cross-atom aggregate, which is PIC's decode polynomial `Z_T`. PIC's
decode temperature-invariance (`pic/spec/PIC_SPEC.md` §3.1) says `argmax_v L(v)` does not depend on
`T`. **Proved for the single-position full-coalition translation:** i-orca
`PDC_Derive.thy`, `pic.specialization_alpha_eq_logit`,
`pic.specialization_alpha_eq_residual`, `pic.specialization_softmax_order`, and
`pic.specialization_softmax_argmax` (strict session `PDC`). The bias enters each complete
body once. Absent atoms have negative-infinity scores and are not identified with finite logits;
the equality to `L` applies to the displayed singleton case. As prose, the inheritance is the point of the
four restrictions: they were chosen because they are exactly the hypotheses PIC already states.

Drop (2) and the inheritance stops. That is §3.2.

---

## 2. Native notation

PDC borrows PIC's carriers and PIC's three natives: the incidence arrow `j ▷ a`, the coalition
bracket `⟦P⟧(a)`, and the strict turnstile `P ⊢_γ a`. Definitions and the bias convention are
`pic/spec/PIC_SPEC.md` §2.5. The semiring family `R_T` is PIC §2: `⊗ = +`, `⊕_T` is logsumexp at
temperature `T`, and `⊕_0 = max`.

Six names are new.

**(N1) Head-indexed incidence.** For a read head `h`, positions `i` and `j`,

> `i ▷_h j  :=  ⟨q_i^{(h)}, k_j^{(h)}⟩`.

Same arrow as PIC, different frame. The frame is that head's query and key vectors, not the
unembedding `{U_v}`.

**(N2) Body annotation.** Let `deriv(a)` be the set of bodies of atom `a`. Each body `P` has a
`T`-free bracket `⟦P⟧(a)`. The annotation sums bodies, not atoms:

> `α_T(a)  :=  ⊕_{T, P ∈ deriv(a)} ⟦P⟧(a)`.

When `deriv(a)` is a singleton this is that body's bracket (up to bias, §1). When it is larger,
`⊕_T` has moved inside the atom, which is the case PIC §3.1 excludes.

**(N3) The two readouts.**

> `Vit(a)     :=  ⊕_{0, P ∈ deriv(a)} ⟦P⟧(a)  =  max_P ⟦P⟧(a)`
> `Mar_T(a)   :=  α_T(a)`

Viterbi is the best body. Marginal is the temperature-`T` sum of the bodies. Competing atoms are
then aggregated again by `⊕_T` or by `⊕_0`, as the query says. A query names its readout. PDC has
no bare "the answer."

**(N4) Proof fragility.** For a finite set `A` of competing atoms,

> `fragile_T(A)  :⟺  argmax_{a ∈ A} Vit(a)  ≠  argmax_{a ∈ A} Mar_T(a)`.

Ties are non-answers, as in PIC: a tie decides nothing. If either argmax is multi-valued, the
readouts are fragile when the sets differ.

**(N5) Crystallization.** An admitted atom is a source.

> `a ↷ s` means atom `a` has been admitted as source `s`, under the rule in §5.

**(N6) External judgment.**

> `𝒯 ⊨ a` means a named external theory `𝒯` affirms atom `a`.

`⊨` is not a semiring value and not a margin. It is not `⊢`.

---

## 3. The derive stratum

### 3.1 Bodies

A **body** of an atom `a` is a coalition `P`: a finite set of sources, each contributing an
incidence, combined by `⊗`. Alternative bodies of the *same* atom are what `α_T` sums. Alternative
*atoms* are a separate aggregate, the query, as in PIC's decode polynomial.

Executable body tables store the complete bracket with the atom bias included once per
body. The bias is common to the bodies of an atom, so it factors out of the logsumexp
as a single additive bias. The source-only PIC `Lc` remains separate from that complete
bracket. This convention matches the singleton equality in §1.

Shared subbodies are shared structure. Summing body scores counts a shared subbody once per parent.
That is a semiring sum, not a possible-world probability. PDC does not claim ProbLog semantics, for
the reason PIC §6.5 already records: overlapping explanations double-count unless a further
compilation step disjointifies them. PDC does not supply that step.

### 3.2 Witness — the readouts disagree

**Witness (now kernel-checked):** i-orca `PDC_Derive.thy`,
`witness_viterbi`, `witness_marginal`, and `witness_fragile`. Atom `A` has two bodies of score 0. Atom `B` has one
body of score `1/2`. At `T = 1`,

> `Mar_1(A) = log(e^0 + e^0) = log 2 ≈ 0.693 > 1/2 = Mar_1(B)`,

so the marginal readout picks `A`. The Viterbi readout has `Vit(A) = max(0,0) = 0 < 1/2 = Vit(B)`,
so it picks `B`. Therefore `fragile_1({A,B})` holds.

This is the example in `pic/spec/PIC_SPEC.md` §3.1, read as a pair of atoms with bodies rather than
as a counterexample sitting outside the calculus. In PDC the example is in scope. Temperature
invariance is a property of the fragment §1, not of the derive stratum.

### 3.3 What a query must say

A derive-stratum query is a pair `(readout, T)`:

| query | selector |
|-------|----------|
| Viterbi | `argmax_a Vit(a)`, equivalently `T → 0` inside every atom and then across atoms |
| marginal at `T` | `argmax_a Mar_T(a)` |
| distribution at `T` | `p(a) ∝ exp(Mar_T(a) / T)`, after the cross-atom `⊕_T` |

Sampling draws from the third. A beam keeps a bounded set of bodies instead of summing them. A beam
is an algorithm over bodies. It is not an element of `R_T`, and PDC does not pretend it is a semiring
operation.

**Lemma (proved, one-body direction).** If every atom has at most one body and every bracket is `T`-free, then
`Vit(a) = Mar_T(a)` for every `T > 0`, and `argmax_a Mar_T(a)` is independent of `T`. If some atom
has two or more bodies, there exist brackets such that `fragile_T` holds for some `T > 0`.

The first sentence is checked by `one_body_agreement` and
`one_body_temperature_invariance` in i-orca `PDC_Derive.thy`. Empty body sets are represented
by negative infinity; winner sets exclude absent atoms and preserve ties. The second sentence
has the checked existential witness §3.2; arbitrary fixed vocabularies without a rival atom
are outside that witness.

---

## 4. The read stratum

### 4.1 Positions and heads

A **context** is a finite sequence of positions. A **head** `h` carries query vectors `q_i^{(h)}` and
key vectors `k_j^{(h)}` in a head space, and value vectors `v_j^{(h)}` in the residual space. The
read incidence is `i ▷_h j` (§2 N1).

The head's mix over keys, at a query position `i`, is the PIC decode polynomial with positions in
place of vocabulary tokens:

> `Z_T^{(h)}(i) = ⊕_{T, j} (i ▷_h j)`,
> `p_T^{(h)}(j | i) = exp( ((i ▷_h j) − Z_T^{(h)}(i)) / T )` for `T > 0`.

At `T → 0` the head selects `argmax_j (i ▷_h j)`. The value write at `i` is the corresponding
mixture `Σ_j p_T^{(h)}(j | i) · v_j^{(h)}`, or the single winning value at `T → 0`. That write is a
source for the decode stratum. From the write onward, the calculus is PIC's encode: a gated sum of
directions. The gate is this mixture. It is no longer an uninterpreted scalar *if* the head vectors
are part of the program. Where a block's nonlinearity is not a value mixture, the gate stays
uninterpreted, which is PIC's forge tax, now local to that nonlinearity.

**Empirical on the R2 finite set:** fieldrun `experiments/pdc/R2_RESULTS.md` records
108 head/query instances on the preregistered GPT-2 bundle and 12 named heads. Under scaled-query,
causal-key, pre-output-projection conventions, the mixture is the host assignment; maximum
f64-recomputed head-write error is 6.683e-7, and key-argmax-set agreement is 108/108. Independent
NumPy vocabulary predictions agree 48/48. These are separate claims, and no other architecture or
prompt distribution inherits them. Identification outside that set remains **open**. Norm folding, candidate sets, and decision-versus-logit agreement stay PIC's interface
(`pic/spec/PIC_SPEC.md` §3). A read-stratum "reconstruction" would have to separate those three
claims the same way.

### 4.2 Charts

Atoms may carry spans. A binary rule compiles to a position-indexed clause, the shape already
sketched for PIC-LP (`pic/spec/PIC_LP.md` §7.5):

> `A(i,k)  ⟸  B(i,j) ⊗ C(j,k)`.

The body is the `⊗` of the children. The split point `j` and the choice of rule are further bodies,
summed by `⊕_T` inside `α_T(A(i,k))`. A chart cell therefore has a Viterbi score and a marginal
score. A **derivation** is a chosen body tree. A **generated sequence** is a path of adjacent
tokens, each step a decode-stratum query whose context is the preceding path.

Two depths are different axes:

- **Layer depth** — the residual trajectory. PIC already models this as the least fixpoint of an
  abstract step (`PIC_Forward.thy`, `lfp_is_trajectory`). The step function stays abstract.
- **Chart depth** — how many span clauses fire, including tokens the model appends (§6).

PDC does not define a function class for either axis. Which functions need chart depth rather than
layer depth is **open**.

A chart cell is stable under a `δ`-perturbation of its child scores when the cell's margin exceeds
`2δ`, by the same numeric hypothesis as PIC's margin certificate (`decode_margin_certified`).
Stating the chart-cell form as its own kernel lemma is **open**. The Boolean demand-closure theorem
does not apply to these aggregates (PIC §6.5); weighted-aggregate demand closure stays open there,
and PDC inherits the gap.

---

## 5. Crystallization

Derivations are chart objects. Sources are residual objects. The passage from one to the other is
admission.

**Rule (definition).** Fix a margin `γ > 0`, a perturbation `δ ≥ 0`, and a common offset `κ`. From

> `P ⊢_γ a` and `|⟦S \ P⟧(v) − κ| ≤ δ` for the target and every rival `v` in the covered candidate set, with `γ > 2δ`,

admit `a ↷ s`: the atom may be used as a source `s` whose write, on this position, stands in for
the coalition `P`. The side condition is the hypothesis of PIC's margin certificate
(`pic/spec/PIC_SPEC.md` §5.5, `decode_margin_certified`, *proved in i-orca for the token-logit
statement*). The source-admission packaging is now **proved** in i-orca
[`PDC_Admission.thy`](https://github.com/jascal/i-orca/blob/master/examples/pdc/PDC_Admission.thy):
`admitted_source_preserves_decision` handles an offset-centered approximation,
`pic.crystallization_admitted_write` instantiates it for a residual source, and
`pic.crystallization_complement_certified` proves the displayed omitted-coalition form.
All require the same covered candidate set, a strict coalition margin, and a bound that includes
the target. No source-admission measurement follows from these lemmas alone.

What the rule is for: a later hop may retrieve `s` instead of re-deriving `P`. Retrieval and
composition keep PIC's meanings (`{s} ⊢ a` versus a coalition with no deciding singleton).
Admission does not raise the host margin. It spends the margin the certificate already required.

**Refusal.** If no faithful decoder frame admits any coalition of size `≤ k` on a measured
activation pattern, the atom is **k-irreducible relative to those activations**, in the sense of
`pic/spec/forge_tax_certificate.md`. That linear program is an oracle for "crystallization is
blocked." Its existence as a decision procedure is part of that note. Whether it certifies real
positions is **empirical and so far negative on its sample** (0/40 held-out positions, recorded in
PIC §7). The preregistered R4 rerun is **empirical**: pil `docs/notes/pdc_r4_outcome.md`,
80/80 positions free-frame reducible (still zero irreducibility certificates), but only
11/80 first saved witness frames pass the separate centered-tail admission guard. The other
69 witnesses are not proofs of impossibility over all frames. A 64-position positive control
admits throughout, and the explicit three-context refusal control has exact rational Farkas
checks for both singleton sources. The proposed negative-admission interpretation of 0/40 is
retired. A blocked atom stays a derivation.

**Packing.** Crystallized atoms that are themselves `γ`-decodable occupy frame slots. PIC's
separation theorem applies to them once they have frame vectors: two `γ`-decodable admitted atoms
are at least `γ` apart in the frame (`margin_pair_separation`). The optimal margin of an admitted
atom, bias-free, is its hull distance (`optimal_margin_hull`). Those citations are PIC theorems
about frame vectors. That a chart of intermediate atoms *should* be packed this way is **open**.
The volume-packing cardinality bound stays what PIC says it is: classical, not kernel-checked, and
loose at realistic `d`.

---

## 6. Appending a position

Crystallization writes into the residual frame. **Append** writes into the context.

> If `a` is the atom a query selects, appending commits a token that denotes `a` as a new position.
> Later read heads may take incidences against it.

Two tags ride with the new position. They are provenance labels, not scores:

| tag | the position was |
|-----|------------------|
| `generated` | selected by a host query (a scratchpad token, a continuation token) |
| `tool` | returned by an external procedure |

`⊢` does not distinguish the tags. `⊨` may: a tool can be defined to append only atoms with
`𝒯 ⊨ a`, and a generated token carries no such guarantee. Both are conventions on the tag, to be
fixed when a concrete `𝒯` is named.

**Chain-of-thought, as a hypothesis (open).** When crystallization is refused, append is the
remaining way to make `a` a source for later reads: the token is a position, and a read head can
attend to it. Serial scratchpads are appends under that refusal. This is a reading of the two
operations. It is not a claim about trained models.

**Empirical, R6 (narrowed):** the frozen four-arm comparison now covers all 27
triples `(a,b,c) ∈ {0,1,2}³` for `(a+b)+c`. Nine first-hop captures are explicitly
reused from R5. Each of their 25 native singleton sources fails the recorded
centered-tail admission procedure, so all 27 triples are in its refused stratum.
Re-derive and crystallize both score 3/27 on full-vocabulary theory agreement;
generated append and tool append both score 9/27. Generated append gains six
cases without losing the three baseline-correct cases, above the preregistered
five-percentage-point bar. The admitted stratum is empty, so its redundancy
claim is untested. Refusal is relative to the stored native frame and procedure;
it is not a proof over all faithful frames.

Native and NumPy final-position predictions agree 108/108. Refused crystallize
cases are bit-identical to re-derive, with no memory injected. A separate fixed
nonzero replay engineering probe matches the NumPy-induced change within
6.390e-5; absolute baseline hidden errors are retained separately. The graph
`r6_chart_bundle.json` and its independent check retain 117 affine decode nodes,
27 generated edges, 27 theory-affirmed tool edges and 54 no-memory edges. Finite
covered-candidate margins are distinguished from the native global token and
from the separate multibody derive chart. See fieldrun `experiments/pdc/R6_PREREG.md`,
`R6_RESULTS.md`, `r6_results.json` and `r6_chart_verification.json`. This supports
the operational refused-slice comparison only, not a general semantic-memory
claim, admitted-source benefit, or theory soundness.

An **unfaithful scratchpad** is an append of `a` whose chart cell does not satisfy `P ⊢ a` for the
body the readout selected. The definition needs a recorded body. A decode that stores only the token
does not, by itself, supply one.

---

## 7. The external judgment

`P ⊢_γ a` means a coalition's scores pick `a`. `𝒯 ⊨ a` means theory `𝒯` affirms `a`. The four
combinations are the vocabulary for errors:

| | `𝒯 ⊨ a` | `𝒯 ⊭ a` |
|--|---------|---------|
| some recorded `P ⊢ a` | host-affirmed and theory-affirmed | **hallucination** — the host decides `a`, the theory does not |
| no such `P` | **miss** — the theory affirms `a`, the host's recorded bodies do not decide it | both decline |

**Fragile truth (definition).** `𝒯 ⊨ a`, the marginal query selects `a`, and the Viterbi query does
not. The theory's atom wins by counting bodies and loses on its best body.

**Empirical, R5:** bounded integer addition, operands 0–4 and answers 0–8, now supplies
a finite decidable `𝒯`. Before host capture, 75 contexts, nine answer tokens, three
fixed coalitions per atom, `γ = 0.5`, a hallucination bar strictly below 10%, and a
25% wide-miss threshold were frozen. Twenty-five further contexts were reserved until the final diagnostic audit
reported in v0.10; that reservation is now consumed. See fieldrun `experiments/pdc/R5_PREREG.md` and
`R5_RESULTS.md`, plus `r5_bundle.json`, `r5_audit.json`, and `r5_theory_results.json`.

| R5 judgment | Viterbi | marginal, T=1 |
|---|---:|---:|
| committed / abstained | 8 / 67 | 10 / 65 |
| affirmed / hallucination | 1 / 7 | 1 / 9 |
| hallucination rate among commitments | 87.5% | 90% |
| raw readout/theory agreement | 16% | 20% |
| committed/full-host agreement | 62.5% | 60% |
| committed/covered-candidate host agreement | 100% | 100% |

There are 47 misses, three fragile contexts, and three fragile truths. Misses use
all recorded body decisions, independently of readout choice or abstention. The
independent NumPy forward matches all 75 native final-position predictions; an
independent auditor checks all 2,025 annotations and every commitment guard.

The candidate-wise guard is **proved**, i-orca `PDC_Admission.thy`,
`pairwise_source_preserves_decision`: each body gap exceeds the absolute drift of
that pair's gap between coalition and source/host scores. It uses the same target
and covered rival, without pooling the vocabulary into one perturbation radius.
The numerical bundle audit checks those finite premises; the lemma does not
mention `⊨`. The certificate covers exactly nine tokens, not an unrestricted
vocabulary argmax.

**Stop rule activated:** both advance epistemic claims are retired for this frozen
model, domain, prompts, body program and threshold. High margin is not an epistemic
instrument there. A later service arm may advertise measured host agreement only;
it may not advertise theory soundness from this certificate. This is a scoped
negative result, not a theorem about every model or certificate. Completeness and
the full held-out north star remain **open**. No threshold was retuned after the miss.

Student certificates in the PIC record (PIC §5.8) are sound for a student and can be false of the
host. PDC's `⊨` is a third target, beside host agreement and student agreement. A certificate names
which of the three it speaks for.

---

## 8. The decode stratum

The decode stratum is PIC. Residual `r = Σ_j d_j`, logit `L(v) = ⟨r, U_v⟩ + b_v`, decision by
`argmax` or by softmax. Frame quantities, participation ratio, multiplicity, the hull, routing rank,
Welch, head/tail, and the certificate tower are PIC's. PDC adds no decode-side quantity.

Sources may include crystallized atoms (§5) and value writes from the read stratum (§4). On a
position where neither has been admitted, the source table is the extensional block table PIC
already reads, and decode is unchanged.

---

## 9. What would make a later version

In the order a formalization could actually proceed.

1. **Translation of §1.** Four restrictions, a statement that `α_T` equals PIC's `L`, and an import
   of decode temperature-invariance. **Closed for R0:** `PDC_Derive.thy`, the four
   `pic.specialization_*` lemmas cited in §1. No claim about read heads or chart recursion follows.
2. **Closed for R0:** the witness §3.2 and one-body direction §3.3 are kernel-checked
   in `PDC_Derive.thy` by the lemmas cited there.
3. **Crystallization as a lemma** that the admitted source reproduces `P`'s decision inside the
   `δ` ball the margin certificate allows. The numeric content is PIC's; the source-admission
   packaging is **proved** by `PDC_Admission.thy` and the named lemmas in §5.
   The R4 oracle experiment is **empirical**, with its corrected negative-domain premise
   and scoped outcomes recorded in §5. The expected universal refusal on the Qwen sample
   is not achieved; no later rung may assume that split.
4. **A read-stratum reconstruction claim**, split the way PIC §3 splits the decode claim: algebraic
   identity, numerical error, decision agreement. **Empirical** for the finite R2 set in §4.1;
   **open** beyond it.
5. **Fragility on real positions (empirical, finite set).** R3 reports 2/16 fragile contexts,
   8/16 Viterbi/full-host agreement and 6/16 marginal/full-host agreement, with 576 fixed copy-route
   bodies. Independent NumPy validation is 256/256. See fieldrun `experiments/pdc/R3_RESULTS.md`.
   Those routes do not explain the full decode and no causal sufficiency is claimed.
   No functional form is conjectured here.
6. **Any expressivity claim** relating chart depth to layer depth. Open. Not conjectured in a
   specific form in v0.1, because PIC's step function is abstract and a sharp conjecture would pretend
   otherwise.

7. **Online service (empirical diagnostic, positive gate open).** R8-H is the
   host-only continuation permitted after R5's stop. A live native CLI computes
   fresh sources and scores only 1,703 fixed lexical probe rows; every response
   retains the body/readout artifact or an explicit abstention. Against a full
   baseline over the same 75 R5 contexts, all probe scores and source writes agree
   exactly. Native output-row calls fall from 3,769,275 to 127,725; three additional
   body/probe score tables cost 383,175 dots in each arm. No context position or
   transformer layer is skipped. Both readouts abstain on all 75 contexts, so
   answer coverage is zero and neither host agreement nor hallucination rate
   among commitments has a defined denominator. This does not pass R8 or revive
   R5. See fieldrun `experiments/pdc/R8H_PREREG.md`, its timing addendum,
   `R8H_RESULTS.md`, and `r8h_results.json`. The final diagnostic audit
   subsequently consumed the 25 reserved contexts with zero commitments; see
   `FINAL_AUDIT_RESULTS.md`. R6's subsequently measured refused-slice outcome is recorded in §6; its admitted
   comparison remains untested.

---

## 10. Notation

| symbol | meaning |
|--------|---------|
| `a`, `A` | an atom; a finite set of competing atoms |
| `P`, `deriv(a)` | a body (coalition); the bodies of `a` |
| `i ▷_h j` | read incidence of head `h` from position `i` onto position `j` |
| `α_T(a)` | `⊕_T` over the bodies of `a` |
| `Vit(a)`, `Mar_T(a)` | best body; temperature-`T` sum of bodies |
| `fragile_T(A)` | the two readouts select different atoms of `A` |
| `a ↷ s` | `a` admitted as source `s` |
| `𝒯 ⊨ a` | external theory `𝒯` affirms `a` |
| `generated`, `tool` | provenance tags on an appended position |
| PIC's `▷`, `⟦·⟧`, `⊢_γ`, `L`, `⊕_T`, `⊗` | as in `pic/spec/PIC_SPEC.md` §8 |

---

## Appendix A. Illustration

**Not a measurement.** A walk-through of the notation on a single question. No model was run.

Question tokens occupy positions. A read head has large `i ▷_h j` on the span "Eiffel Tower" and the
value write is recorded as a source `landmark`. Three bodies offer the atom `country = France`:

| body | bracket |
|------|---------|
| `P_landmark` | 2 |
| `P_paris-nearby` | 0 |
| `P_ngram` | 0 |

A rival atom `country = Italy` has one body of bracket `1/2`.

- `Vit(France) = 2`, `Vit(Italy) = 1/2`. Viterbi selects France. Not fragile on this pair.
- Replace `P_landmark`'s bracket by 0. Then `Vit` selects Italy (`1/2 > 0`) and `Mar_1` selects
  France (`log 3 > 1/2`). The pair is `fragile_1`. There are three zero-score
  bodies here, whereas §3.2 has two.

A chart clause `capital(i,k) ⟸ country(i,j) ⊗ capital_of(j,k)` is a body of `capital = Paris` once
`country = France` is selected and a further body supplies `capital_of`. An external table with
`𝒯 ⊨ capital(France) = Paris` affirms that atom. Selecting `France` as the capital would be
`⊢` without `⊨`: hallucination, in the sense of §7.

If a coalition `P ⊢_γ Paris` with the complement inside `δ` and `γ > 2δ`, the rule of §5 allows
`Paris ↷ s`. A later hop may retrieve `s`. If the forge-tax linear program refuses every small
coalition, `Paris` stays a derivation, and §6 allows appending a token for it so a later head can
read the new position. That last sentence is the open hypothesis, applied to the illustration.

---

*This spec is versioned on its own. A PIC theorem cited here keeps PIC's tag and PIC's citation.
When a PDC statement becomes a theorem in i-orca, or a measurement in fieldrun or pil, update the
section and bump the version. Do not bump PIC for a PDC change.*
