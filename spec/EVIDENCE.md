# PDC v0.10 evidence map

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
| proved: fixed outside maximum | `decode_fixed_outside_max` | same theory; finite nonempty outside set, target inside and outside-disjoint |
| imported PIC learning side condition | `step_decode_preserved` | i-orca/examples/pic_learn/PIC_Learn.thy; per-step numerical premises remain empirical |
| empirical R1 | 1,280 finite one-body checks and two-body witness | fieldrun/experiments/pdc/R1_RESULTS.md; scripts/test_pdc_derive.py |
| empirical R2 | 108 named head/query instances; independent reference 48/48 | fieldrun/experiments/pdc/{R2_PREREG.md,R2_RESULTS.md,r2_results.json}; scripts/pdc_read_check.py |
| empirical R3 | 16 competing-copy tasks, 576 body annotations | fieldrun/experiments/pdc/{R3_PREREG.md,R3_RESULTS.md,r3_charts.json}; scripts/pdc_copy_chart.py |
| empirical R4 | positive 64/64; Qwen 80/80 reducible, first-frame stronger admission 11/80 | pil/docs/notes/pdc_r4_{prereg,outcome}.md; results/pdc_r4/{results,verification}.json; experiments/verify_pdc_r4.py |
| empirical R5, negative | 7/8 and 9/10 hallucinations among commitments; epistemic stop | fieldrun/experiments/pdc/{R5_PREREG.md,R5_RESULTS.md,r5_audit.json,r5_theory_results.json}; scripts/pdc_bundle_audit.py, pdc_theory_check.py |
| empirical R6, narrowed | 27 refused triples, four arms; 117 graph nodes, 108 provenance paths | fieldrun/experiments/pdc/{R6_PREREG.md,R6_RESULTS.md,r6_results.json,r6_chart_verification.json}; scripts/pdc_memory_audit.py, pdc_memory_bundle_check.py |
| empirical R7, negative | both 0/75 admissions after 200 proposals; 183 protected outputs | pil/docs/notes/pdc_r7_{prereg,outcome}.md; results/pdc_r7/{results,verification}.json; experiments/verify_pdc_r7.py |
| empirical R8-H, negative | actual row savings, zero coverage on 75 | fieldrun/experiments/pdc/{R8H_PREREG.md,R8H_RESULTS.md,r8h_results.json}; scripts/pdc_service_audit.py |
| empirical final heldout, negative | unchanged policy, zero coverage on reserved 25; NumPy 25/25 | fieldrun/experiments/pdc/{FINAL_AUDIT_PREREG.md,FINAL_AUDIT_RESULTS.md}; final_audit/{manifest,results,reference_verification}.json; scripts/pdc_final_audit_check.py |

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
