# Grok review and next-direction prompt after Qwen v0.17

Review PDC PR #1, fieldrun PR #148 (stacked on #147), PIL PR #155 and
i-orca PR #37 as one research change. Start from the v0.17 paper, evidence
map, Qwen memory PREREG/RESULTS, PIL Qwen learning protocol/outcome, and
independent endpoint and chart audits. The supplemental
`pdc-qwen35-memory-learning-v1` release contains raw data and frames and
depends on `pdc-qwen35-4b-v1`.

Established observations: Qwen one-hop host 100/100 correct; full-program
certificates succeed, but singleton guards admit 0/100. All 27 two-hop
triples are singleton-refused. Rederive/crystallize host accuracy is 12/27;
generated/tool accuracy is 27/27. The latter also replaces an empty assistant
turn with a nonempty one, so semantic memory and history formatting are
confounded. Baseline charts still commit 14 hallucinations among 25 answers.
Both 200-proposal learning arms retain 0/100 admissions and all 208 protected
host decisions, including 30 wrong second-hop decisions. Endpoints were
independently reconstructed; intermediate trajectories were not saved.
A separately preregistered development control now finds period 9/27 correct and wrong-digit 0/27 correct, with 27/27 following the wrong supplied intermediate; independent reference 54/54 and input/count/hash audit pass. This supports supplied-digit sensitivity, without an exclusive internal-mechanism or fresh-confirmation claim. No actual admitted residual replay occurred. Original R5 claims remain
retired; the original final 25-context slice is consumed, and all 100 Qwen
first-hop cases are now development data.

First identify severity-ranked correctness, scope and reconstruction defects
in these claims. Then recommend exactly one bounded next experiment, or
recommend stopping. Explain what uncertainty it resolves beyond these
results. If proposing an experiment, specify frozen data generation, fresh
held-out allocation where relevant, model/chat format, candidate scope,
body construction, controls, numerical guard, compute budget, independent
external grade, effect-size bar, stop rule and artifact interface. Separate
raw host correctness, covered score agreement, oracle admission, actual
residual replay, useful coverage and compute savings. Do not assume prompt
construction guarantees host correctness, invent a uniform delta, revive
certificate-to-truth claims, treat frozen-budget failure as impossibility,
retune these completed runs, or substitute another constructed positive
control for a real-model memory result. Explain why the proposed result,
positive or negative, would change the next decision.


Latest fixed-coalition diagnosis (v0.16): 2091 predeclared bodies on 100 known
development frames, no model calls or learning. All 2080 pairs fail. Last 8
contributions pass exact 5/100 and centered 0/100: compact gate inconclusive
against 20/100 bar. Last 16 pass 77/100 exact and 29/100 centered; last 32 pass
100/100 and 99/100. All 209100 verdicts independently reconstructed within
3.49e-13 and 17 frozen hashes verified. Larger-group passage is not backbone
pruning, global minimum coalition size or actual memory transfer. Do not
base the next recommendation on the now-false premise that all native
groups refuse; distinguish larger fixed groups from compact <= 8 bodies.


Latest engineering prerequisite:

**Empirical, engineering correction (2026-10-26).**
[Fieldrun PR#149](https://github.com/jascal/fieldrun/pull/149) corrects
DeltaNet normalization from sqrt(sum(q*q))+epsilon to the installed
Transformers reference's sqrt(sum(q*q)+epsilon). A low-norm official-kernel
golden fails before correction (error 0.08847). The original tiny hidden
engineering gate fails even without replay and remains recorded. SAME
inputs/reference and unchanged 1e-4 threshold pass after correction (maximum
hidden error 7.153e-7), with tiny 9/9, ordinary 60/60 and real 5/5 global reference
agreement and 194 native tests. Zero replay is bit-identical. Real float16
reference hidden differences up to 0.03407 remain descriptive. This is an
intentional default-kernel correction and an opt-in final-query embedding
replay hook, not admitted semantic transfer. The original native binary
SHA 90cd5c8dda5b1f5c16888387baa92b78205c82a99b0eb04a98679ca324c1928d and
old archives/results remain unchanged. Old coalition/admission counts do
not establish counts on the corrected computation; future studies must
capture and certify their own actual carriers. No fresh transfer prompts
have run. [Failures, protocol, correction and verification](https://github.com/jascal/fieldrun/tree/research/pdc-qwen35-replay/experiments/pdc_qwen35_replay_engineering).

This documentation pass does not authorize an experiment: a later study must
freeze the corrected runtime, capture and certify its own carriers, and use
fresh prompts; it must not pool archived coalition or admission counts into
that study.
