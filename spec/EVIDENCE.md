# PDC v0.13 evidence map

This is a **stopped-stage review**, not a passing north-star claim.
The original evidence snapshot is hosted in the [GitHub prerelease](https://github.com/jascal/pdc/releases/tag/pdc-v0.10-evidence). Paths below are relative to the shared workspace root.
`fieldrun/experiments/pdc/release_inventory.json` records SHA-256 and size
for the frozen proof, source, paper and run artifacts. Its inventory checker
lives in fieldrun; no code or proof is placed in pdc. A hash proves artifact
identity, not correctness. Use the named independent checks for correctness.

## Scope of every kernel claim

The kernel results concern finite score identities, readout comparisons and
preservation of **covered score decisions** under explicit premises. They do
not establish external-theory truth, useful reasoning, or full-vocabulary
host agreement beyond the covered candidate set. Nonzero admission alone
would not establish these stronger claims. Full-host agreement and theory
judgments require independent evidence; protected-bank preservation is not
generalization. R7's fixed-budget negative neither proves unlearnability
nor identifies the protected-margin constraint as the sole bottleneck.

The final 25-context slice is **consumed**. It must not be used for any
future threshold, body-generator or checkpoint selection. Any new
confirmatory experiment requires fresh held-out data.

| Tag / scope | Statement or run | Evidence / checker |
|---|---|---|
| proved: one-body PIC seam | `mar_singleton`, `one_body_agreement`, `one_body_temperature_invariance`, four `pic.specialization_*` lemmas | i-orca/examples/pdc/PDC_Derive.thy; strict PDC session |
| witness, proved: two versus one body | `witness_viterbi`, `witness_marginal`, `witness_fragile` | same theory; distinct equal-score body IDs retained |
| proved: admission / complement | `admitted_source_preserves_decision`, `pic.crystallization_admitted_write`, `pic.crystallization_complement_certified` | i-orca/examples/pdc/PDC_Admission.thy |
| proved: pairwise fidelity | `pairwise_source_preserves_decision` | same theory; covered candidate set only, no truth conclusion |
| proved: pairwise relative-gap condition | `pairwise_gap_guard_iff`: abs(h-p)<p iff 0<h<2p | i-orca/examples/pdc/PDC_Admission.thy; no causal sufficiency claim |
| proved: fixed outside maximum | `decode_fixed_outside_max` | same theory; finite nonempty outside set, target inside and outside-disjoint |
| imported PIC learning side condition | `step_decode_preserved` | i-orca/examples/pic_learn/PIC_Learn.thy; per-step numerical premises remain empirical |
| empirical R1 | 1,280 finite one-body checks and two-body witness | fieldrun/experiments/pdc/R1_RESULTS.md; scripts/test_pdc_derive.py |
| empirical R2 | 108 named head/query instances; independent reference 48/48 | fieldrun/experiments/pdc/{R2_PREREG.md,R2_RESULTS.md,r2_results.json}; scripts/pdc_read_check.py |
| empirical R3 | 16 competing-copy tasks, 576 body annotations | fieldrun/experiments/pdc/{R3_PREREG.md,R3_RESULTS.md,r3_charts.json}; scripts/pdc_copy_chart.py |
| empirical R4 | positive 64/64; Qwen 80/80 reducible, first-frame stronger admission 11/80 | pil/docs/notes/pdc_r4_{prereg,outcome}.md; results/pdc_r4/{results,verification}.json; experiments/verify_pdc_r4.py |
| empirical R5, negative | 7/8 and 9/10 hallucinations among commitments; epistemic stop | fieldrun/experiments/pdc/{R5_PREREG.md,R5_RESULTS.md,r5_audit.json,r5_theory_results.json}; scripts/pdc_bundle_audit.py, pdc_theory_check.py |
| empirical R6, narrowed | 27 refused triples, four arms; 117 graph nodes, 108 provenance paths | fieldrun/experiments/pdc/{R6_PREREG.md,R6_RESULTS.md,r6_results.json,r6_chart_verification.json}; scripts/pdc_memory_audit.py, pdc_memory_bundle_check.py |
| empirical R7, negative | both 0/75 admissions after 200 proposals; 183 protected outputs | pil/docs/notes/pdc_r7_{prereg,outcome}.md; results/pdc_r7/{results,verification}.json; experiments/verify_pdc_r7.py |
| empirical saved-frame diagnostic, negative | four arms each 0/75 at three endpoints; nine matching singleton decisions, zero strict drift passes | pil/docs/notes/pdc_r7_diagnostic_{prereg,outcome}.md; results/pdc_r7_diagnostic/{results,verification}.json; experiments/verify_pdc_r7_diagnostic.py; follow-up to original archive |
| empirical R8-H, negative | actual row savings, zero coverage on 75 | fieldrun/experiments/pdc/{R8H_PREREG.md,R8H_RESULTS.md,r8h_results.json}; scripts/pdc_service_audit.py |
| empirical final heldout, negative | unchanged policy, zero coverage on reserved 25; NumPy 25/25 | fieldrun/experiments/pdc/{FINAL_AUDIT_PREREG.md,FINAL_AUDIT_RESULTS.md}; final_audit/{manifest,results,reference_verification}.json; scripts/pdc_final_audit_check.py |
| empirical Qwen3.5-4B follow-up, full-program positive | host 100/100; each readout 50/50 correct heldout commitments; all witnesses full; independent reference 100/100 | fieldrun/experiments/pdc_qwen35_4b/{PREREG,RESULTS}.md; results.json, verification.json; scripts/pdc_qwen35_bundle_check.py; supplemental release pdc-qwen35-4b-v1 |
| empirical Qwen singleton diagnostic, negative |100/100 matching covered singleton decisions, 97 floor passes, 0 exact/centered admissions; 6500 verified sources | fieldrun/experiments/pdc_qwen35_singletons/{PREREG,RESULTS}.md, results.json, verification.json; scripts/pdc_qwen35_singletons_check.py; not fresh confirmation |

Build the strict proof session from the workspace root:

```
isabelle build -o timeout=40 -d i-orca/examples/pic_core -D i-orca/examples/pdc
```

Build the paper from pdc/paper:

```
latexmk -pdf -interaction=nonstopmode -halt-on-error pdc_calculus.tex
```

Do not rerun one-shot native experiments to validate artifact identity.
Run the saved-artifact auditors instead. The 25-context reservation has
been consumed; it is no longer a fresh confirmation set. Missing original
gates remain missing: intended R4 negative-domain impossibility, R6 admitted
transfer, useful R8 coverage and criterion 9. R7 is a fixed-budget negative,
not an impossibility theorem. Appendix A is an illustration. The companion review branches and complete archived snapshot are linked from
`review/GROK_REVIEW.md`. Default-branch paths in historical notes describe
intended merged locations; use the PR branches while review is open.


## v0.14: Qwen two-hop and guarded-learning extension (empirical)

- [Frozen memory protocol and results](https://github.com/jascal/fieldrun/tree/de7e399/experiments/pdc_qwen35_memory): 27 refused triples, 54 unique second-hop inputs; full-host accuracy 12/27 rederive/crystallize and 27/27 generated/tool. Independent reference 54/54 and body audit pass. Empty/nonempty assistant-history confound remains; no admitted replay or admitted-stratum redundancy. Baseline readouts each have 14 hallucinations among 25 commitments.
- [Frozen learning protocol and outcome](https://github.com/jascal/pil/tree/dd8a268/docs/notes): both arms complete 200 proposals, admissions 0/100 throughout. Independent endpoint reconstruction confirms all 208 protected decisions and full-vocabulary FP/W. Intermediate evidence is runtime logs, not independently reconstructed frames.
- [Learned-frame chart audit](https://github.com/jascal/fieldrun/blob/de7e399/experiments/pdc_qwen35_memory/learning_chart_audit.json): chart-quality gate passes; joint admission advance gate fails. No fresh confirmation, actual admitted replay, epistemic revival or useful-service claim.

The original final 25-context slice remains consumed and prohibited for future
threshold/body selection. Former Qwen held-out wordings are now development
data because learning uses all 100 cases. Existing releases remain immutable.

[Full Qwen memory/learning evidence](https://github.com/jascal/pdc/releases/tag/pdc-qwen35-memory-learning-v1): 143 verified payload files,
561684314 bytes; SHA-256 `633fa531742d5fbda36d239e2b7cf532d8b4e84ebfc8f28caf4b5acf99ef463b`.
Depends on the original Qwen release; weights/environments remain external.


## v0.15 memory-content controls (empirical, development only)

[Protocol, results and independent verification](https://github.com/jascal/fieldrun/tree/research/pdc-qwen35-4b/experiments/pdc_qwen35_memory_controls): published preregistration efa57e0 before inference;54 unique new inputs on27 known triples. Period9/27 correct; wrong digit0/27 correct and27/27 following-wrong. Reused empty/correct-digit baselines12/27 and27/27. Independent reference54/54 and23 frozen hashes pass. Predeclared content-sensitivity bar passes, neutral-improvement bar fails. No exclusive internal mechanism, admitted replay, fresh confirmation, body search, service saving or epistemic revival.

[Control raw evidence](https://github.com/jascal/pdc/releases/tag/pdc-qwen35-memory-controls-v1):39 verified payload files,93344761 bytes;
SHA-256 `b4196b098f5d673f4418ed5f2b9dd0bc78d762f8f75b9bbb61db29c0ff5d10ad`. Previous releases are unchanged.


## v0.16 fixed native coalitions (empirical, saved development data)

[Protocol/results/checks](https://github.com/jascal/fieldrun/tree/research/pdc-qwen35-4b/experiments/pdc_qwen35_coalitions): prereg d4a6d6f,2091 fixed bodies including all2080 pairs,209100 verdicts. No pair passes. Last8 exact5/100 and centered0/100: compact gate inconclusive against20/100 bar. Last16 exact77/100 and centered29/100; last32 exact100/100 and centered99/100. All five compact cases are sum-one facts across known wordings. Independent raw-vector reconstruction passes all metrics within3.49e-13 and17 frozen hashes. Covered-score passage only; no causal replay, backbone pruning, global minimality, fresh confirmation or new model call.

[Full coalition metrics](https://github.com/jascal/pdc/releases/tag/pdc-qwen35-coalitions-v1):16 verified payload files,4942886 bytes;
SHA-256 `4ec2b1e5faa6b559145c3dddad602572a98fb600e5027d57312cdd66270b5ada`. Original Qwen and memory-learning releases supply inputs;
converted model frame/weights and environments remain external.


## v0.17 normalization correction and replay engineering

**Empirical, engineering correction (2026-10-26).**
[Fieldrun PR#149](https://github.com/jascal/fieldrun/pull/149) corrects
DeltaNet normalization from sqrt(sum(q*q))+epsilon to the installed
Transformers reference's sqrt(sum(q*q)+epsilon). A low-norm official-kernel
golden fails before correction (error0.08847). The original tiny hidden
engineering gate fails even without replay and remains recorded. SAME
inputs/reference and unchanged1e-4 threshold pass after correction (maximum
hidden error7.153e-7), with tiny9/9, ordinary60/60 and real5/5 global reference
agreement and194 native tests. Zero replay is bit-identical. Real float16
reference hidden differences up to0.03407 remain descriptive. This is an
intentional default-kernel correction and an opt-in final-query embedding
replay hook, not admitted semantic transfer. The original native binary
SHA90cd5c8dda5b1f5c16888387baa92b78205c82a99b0eb04a98679ca324c1928d and
old archives/results remain unchanged. Old coalition/admission counts do
not establish counts on the corrected computation; future studies must
capture and certify their own actual carriers. No fresh transfer prompts
have run. [Failures, protocol, correction and verification](https://github.com/jascal/fieldrun/tree/research/pdc-qwen35-replay/experiments/pdc_qwen35_replay_engineering).

[Engineering raw evidence](https://github.com/jascal/pdc/releases/tag/pdc-qwen35-replay-engineering-v1):78 verified payload files,21665828 bytes,
SHA-256 `42233206bee1cf7cdd6eb745558c9e02d2b68364d3d00993d6f47abdee9e0a1e`. Includes failed/corrected captures, source and both experimental executables; real weights/environments remain external.
