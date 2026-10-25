> Archived pre-publication record. Current remote links and review prompts are in [GROK_REVIEW.md](GROK_REVIEW.md). Statements below about unpublished status describe the original snapshot.

# Full PDC requirement audit — 2026-10-25

The original PDC_GOAL.md remains authoritative. This is an evidence audit,
not a replacement objective. No full-goal completion is claimed. Previous
turns completed concrete experiments and changed the next action; they
were progress, not status-only turns.

| Requirement | Authoritative evidence | Disposition |
|---|---|---|
| R0 singleton PIC seam, temperature invariance, two-body witness, one-body agreement | i-orca/examples/pdc/PDC_Derive.thy; strict PDC session (PIC_Core parent) builds; zero holes | proved for stated translations |
| R1 typed readout and finite evaluator | fieldrun/scripts/pdc_derive.py; experiments/pdc/R1_RESULTS.md; focused executor tests | measured on 1,280 one-body checks and witness |
| R2 native read identity, numerical error, argmax agreement | fieldrun/experiments/pdc/R2_PREREG.md, R2_RESULTS.md, r2_* | measured stated 108-head/query sample; reference 48/48 |
| R3 preregistered actual circuit body tables and fragility | fieldrun/experiments/pdc/R3_PREREG.md, R3_RESULTS.md, r3_charts.json | measured 16 tasks, 576 body annotations |
| R4 positive feasibility and admission | pil/results/pdc_r4/results.json, verification.json; docs/notes/pdc_r4_outcome.md | 64/64 positive |
| R4 intended negative Qwen domain, exact duals | same files and fieldrun r4_qwen_sources.jsonl | original expectation contradicted: 80/80 free-frame reducible, 11/80 first saved frames pass stronger admission; no intended Qwen impossibility evidence |
| R4 guard lemma | i-orca/examples/pdc/PDC_Admission.thy, named admission/crystallization lemmas | kernel checked; toy refusal duals do not replace Qwen requirement |
| R5 finite theory, all four counts, advance bar | fieldrun/experiments/pdc/R5_PREREG.md, R5_RESULTS.md, r5_theory_results.json | negative closure: 87.5%/90% hallucination; epistemic claim retired |
| R6 four arms, actual assembly and memory provenance | R6_PREREG.md, R6_RESULTS.md, r6_results.json, r6_chart_bundle.json, independent checks in fieldrun | observed refused stratum improves 3/27 to 9/27; admitted stratum empty, redundancy/admitted transfer untested |
| R7 fixed writes/gates, decode invariants, margin bounds, FP>=W, admission movement | pil/docs/notes/pdc_r7_prereg.md, pdc_r7_outcome.md; results/pdc_r7 | negative closure: both 0/75 after 200 proposals; protected 183/183, logged drift premises and independent endpoint audit pass |
| R8 live subset service, bundle or abstain, body/readout/margin/fragility/theory/provenance | fieldrun/scripts/pdc_service.py; R8H_RESULTS.md; FINAL_AUDIT_RESULTS.md and captures/bundles | implemented and audited; all abstain, memory none; no truth-soundness claim |
| R8 nonempty host agreement >=95%, original hallucination <10%, measured useful compute saving | same | unmet: zero coverage on 75 and final 25; rates undefined despite real row savings |
| R9 spec cites R0–R8, paper tags cite evidence | pdc/spec/PDC_SPEC.md v0.10; pdc/paper/pdc_calculus.tex and PDF | stopped-stage draft; publication unresolved; no full R0–R8 success |
| Criterion 9 criteria 1–8 together on one untouched heldout slice | fieldrun final_audit/manifest.json, results.json, reference_verification.json | not achieved; all 25 opened once after policy freeze, no commitments; heldout reservation consumed |
| No pdc code/proofs; no cross-repo code imports; PIC leaf unchanged | repo source placement and import inspection | maintained; data NPZ/JSON interfaces consumed across repos |
| Public artifact/reproducibility | local run artifacts and draft links | not published; pdc has no remote, all PDC changes remain local/uncommitted |

## Checked commands in current continuation

- `isabelle build -o timeout=40 -d i-orca/examples/pic_core -D i-orca/examples/pdc`: strict session passes (outside workspace cache needs approved escalation).
- PIL focused P3/admission tests: 11 pass; ruff passes.
- fieldrun four focused PDC test modules: 13 pass with pil's installed interpreter; system Python lacks pytest.
- `pdc_final_audit_check.py`: all 25 paired contexts and 127,725 body/probe annotations pass independent checks.
- Independent NumPy reference forward: final heldout full-vocabulary matches 25/25.
- Paper rebuilt after final corrections: six pages, build exit 0, no LaTeX warnings.

## Remaining original gaps

The intended negative-domain impossibility result is unestablished; admitted
memory-transfer and redundancy are untested; useful service coverage and
criterion 9 fail. R5 explicitly permits host-only continuation, which has
now also failed its coverage gate at the frozen parameters. R7 disallows
extension/sweeps after its fixed-budget negative result. A new model,
policy, objective or new confirmatory data would require an explicit new
preregistration and a revised scientific claim; it cannot retroactively
pass this program's failed gates. Preserve these outcomes in the stopped-
stage paper and reviewable artifacts. Public release needs a concrete
repository/artifact destination; no public stop has yet been published.

## R9 review inventory verified

The stopped-stage evidence map is pdc/spec/EVIDENCE.md. The inventory at
fieldrun/experiments/pdc/release_inventory.json lists 376 files totaling
1,203,617,774 bytes. Its streaming hash verifier checks all entries with
zero failures. All ten input/evaluator/model hashes frozen before the
final audit independently still match. This validates artifact identity,
not the scientific claims. Corrected stale present-tense statements about
unperformed R7 and untouched heldout data; historical version notes remain
historical. The six-page paper rebuilds cleanly after these corrections.

Publication discovery: PDC has no configured git remote and `gh repo view
jascal/pdc` reports that the repository cannot be resolved. A destination
question is pending; no remote repository has been created and no files
have been publicly published. This is the first publication-destination
blocker observation; meaningful local R9 review work was completed in this
turn. The original objective remains active and incomplete.
