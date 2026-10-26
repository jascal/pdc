# Grok review and next-direction prompt after Qwen v0.14

Review PDC PR #1, fieldrun PR #148 (stacked on #147), PIL PR #155 and
i-orca PR #37 as one research change. Start from the v0.14 paper, evidence
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
No actual admitted residual replay occurred. Original R5 claims remain
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
