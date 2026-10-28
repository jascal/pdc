# Grok review and next research direction

The central PDC paper/spec PR links five companion PRs. Review all six
as one research change. These changes are proposed, not merged.
No automatic Grok review has been invoked by this document.

- Central paper/spec PR: https://github.com/jascal/pdc/pull/1
- Runtime, chart/service code and small results: https://github.com/jascal/fieldrun/pull/147
- Archived Qwen follow-up: https://github.com/jascal/fieldrun/pull/148
- Normalization correction and replay engineering: https://github.com/jascal/fieldrun/pull/149
- Admission oracle and guarded learning: https://github.com/jascal/pil/pull/155
- Strict Isabelle proofs: https://github.com/jascal/i-orca/pull/37
- Paper PDF: https://github.com/jascal/pdc/blob/research/pdc-stopped-stage/paper/pdc_calculus.pdf
- Original goal: https://github.com/jascal/pdc/blob/research/pdc-stopped-stage/review/ORIGINAL_GOAL.md
- Evidence map: https://github.com/jascal/pdc/blob/research/pdc-stopped-stage/spec/EVIDENCE.md
- Full original code/results/paper snapshot: https://github.com/jascal/pdc/releases/tag/pdc-v0.10-evidence

Current review status and stack: [PR readiness](PR_READINESS.md). Fieldrun
#148 is based on #147; #149 is based on #148. PIL #155 and i-orca #37 have
independent bases. The latest Qwen evidence and next-direction prompt are in
[QWEN_NEXT_DIRECTION.md](QWEN_NEXT_DIRECTION.md). This review preparation does
not authorize an experiment or a merge.

The 596 MB archive contains complete captures and frames omitted from git;
per-repo PDC_ARTIFACTS.md files map archive paths to hashes. Model weights
and Python/Isabelle/TeX environments are external prerequisites. The archive
freezes the original audited snapshot; PR commits add remote publication
instructions and can have different file hashes. No scientific result was
retuned during publication.

## Prompt 1: critical review

Please review the central PDC paper/spec PR and its five linked companion
PRs as one research change. Give severity-ranked, actionable findings with
exact file/line or theorem references. Separate implementation bugs, proof
scope mismatches, experimental validity concerns and unsupported claims.
Do not treat zero coverage as passing agreement, finite-bank preservation
as generalization, a toy refusal as the intended Qwen negative result, or
an empirical plateau as impossibility.

Check in particular:
1. Whether the kernel translation really imports PIC, preserves absent atoms
   and ties, and proves only the stated one-body/finite-candidate fragment.
2. Whether singleton/body scores count bias once, preserve fixed writes/gates,
   include target and rivals in drift bounds, and separate candidate coverage
   from full-vocabulary host agreement and external-theory truth.
3. Whether R7's fixed outside maximum is valid for decisions, its outside
   logsumexp is loss-only, source-sum closure is explicit, clipping/restoration
   preserves the stated invariants, and the independent audit is adequate.
4. Whether optional native capture, subset scoring and residual replay alter
   default behavior, whether accounting counts actual dispatched work, and
   whether the reported independent model checks justify their narrow scopes.
5. Whether preregistrations, one-shot policies, consumed heldout data and
   negative closures are faithfully retained in code, results and paper.
6. Whether any claimed artifact is missing or cannot be reconstructed with
   the documented external prerequisites. Inspect actual artifacts rather
   than accepting the inventory or paper as correctness evidence.

Distinguish confirmed findings from hypotheses requiring a rerun. Do not
repeat one-shot experiments or select better thresholds to make them pass.
Finish with a merge recommendation and the smallest required corrections.

## Prompt 2: choose the next research direction

Read the paper/spec PR, linked companion PRs and original goal above. The
purpose is useful, checkable transformer reasoning charts, not publishing
for its own sake. Decide what experiment would most change our belief that
this approach can become useful.

Original GPT-2 stage evidence (the latest Qwen evidence is linked above):
- The one-body seam and admission guards are kernel checked. Those theorems
  preserve covered score decisions, not truth.
- R4's intended negative Qwen premise fails: 80/80 free-frame reducible;
  11/80 first saved frames pass the stronger admission guard. Toy rational
  refusal duals do not supply Qwen impossibility evidence.
- R5 hallucination among commitments is 7/8 Viterbi and 9/10 marginal on
  the frozen GPT-2/addition domain; the epistemic claim is retired there.
- R6 has 27 refused triples: rederive/crystallize 3/27, generated/tool
  append 9/27. There are no admitted cases, so admitted transfer and
  redundancy remain untested.
- R7 has two 200-proposal arms, both 0/75 admissions; all 183 protected
  full-host predictions remain unchanged. This is negative at that budget,
  not proof of impossibility or generalization.
- The fixed 1703-probe service saves real output-row work but abstains on
  all 75 development and all 25 final heldout contexts. Conditional
  agreement/hallucination rates are undefined. The heldout slice is consumed.

First assess whether the bottleneck is the scientific premise, model/task
choice, body construction, certificate conservatism, protected-margin
learning constraint, or a combination. Separate what existing evidence
actually identifies from what it cannot distinguish. Compare at most three
plausible next directions, including the option to retire this approach.

Recommend exactly ONE bounded next experiment. Provide:
- The precise hypothesis and why the current results leave it open.
- A baseline and control that could falsify the proposed mechanism.
- Model/task/data choices and a new heldout split; no tuning on the consumed
  25-context slice, no post-hoc body shopping and no goal redefinition.
- The readout, body generator, candidate coverage and externally graded claim.
- Fixed thresholds, sample size, budget, metrics, effect-size bar and stop rule
  to preregister before model outputs are inspected.
- How to measure useful nonzero coverage, full-host agreement, theory accuracy
  and actual compute costs separately; do not require a certificate to imply
  truth without an independent argument.
- A minimal implementation plan respecting ownership: pdc spec/paper only,
  i-orca proofs, fieldrun runtime/charts, pil learning, artifact interfaces
  across repositories and no local-path code imports.
- What a positive result would establish, what it would still leave open,
  and what a negative result would cause us to stop doing.

Prefer a decisive small test over a broad sweep, a new formalism or a vague
request for larger models. Do not propose reviving a retired result by
renaming its gate or selecting a convenient passing subset.
