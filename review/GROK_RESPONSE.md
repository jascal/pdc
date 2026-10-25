# Response to the user-supplied Grok review

The review was supplied by the user in this session. It was not an automated
GitHub review or a fresh independent execution of the saved artifacts.

## Requested corrections: implemented

1. The paper's admission section and spec/EVIDENCE.md now contain an explicit
   paragraph limiting kernel claims to finite scored semantics and covered
   score decisions. Neither admission nor kernel checking alone establishes
   external truth, useful reasoning or agreement outside the covered set.
   R7 neither proves unlearnability nor identifies a unique bottleneck.
2. The paper's final-audit section and spec/EVIDENCE.md explicitly prohibit
   using the consumed 25-context slice for future threshold, body-generator
   or checkpoint selection. New confirmation needs fresh held-out data.

The revised PDF compiles to six pages without LaTeX warnings. No experiment,
threshold, body generator, numerical result, kernel statement or original
archive has changed. Existing artifact hashes still identify the original
snapshot. The PR contains the subsequent clarification.

## Next-experiment proposal: not executable as written

The proposed synthetic two-body test is a useful direction to examine, but
these choices must be resolved before claiming it is preregistered:

| Issue | Required correction and implication |
|---|---|
| gamma = 2 delta | The margin theorem requires m > gamma > 2 delta; equality is invalid. The existing exact pairwise guard is a different formulation. Choose one guard and freeze its strict inequalities. |
| A fixed delta allegedly inherited from R4/R7 | Their actual tail/step drifts depend on source, context and frame; there is no single inherited fixed delta satisfying the proposed new experiment. Define how it is computed, or prove a valid uniform bound before use. |
| Frozen GPT-2 is 100% correct by construction on synthetic prompts | Generating arithmetic prompts does not construct the model's decoder or its native source coalitions. Keep a real model's accuracy as a measured baseline; a constructed arithmetic host is a separate control. No filtering to correct-host prompts after observing outputs. |
| Two pre-specified source coalitions implement addition | An attention/MLP grouping or prompt operand position is not automatically a sufficient causal coalition. Name native source indices and their fixed generator before outputs, and treat their adequacy as the hypothesis. |
| 200 prompts versus 50 development + 50 heldout | Resolve the allocation of the remaining 100 before generating or running the data; freeze unique cases, IDs, seed and split. |
| Candidate coverage means positions scored | That measures evaluation work. Primary useful coverage must count all heldout prompts and require an actual non-abstaining, independently affirmed commitment. Report scored, committed, host-agreeing and theory-affirmed denominators separately. |
| Random bodies expected to have low conditional truth accuracy | If host accuracy is 100% and a valid certificate preserves its decision over the same exhaustive candidates, admitted control bodies must also be correct. Random-body coverage may be lower; conditional truth accuracy need not be. |
| One forward for two autoregressive hops | Specify two forwards, a teacher-forced construction, or a single-position task. Teacher forcing the correct intermediate cannot be called generated two-hop reasoning. Count all forwards and reference scoring separately. |
| Empty coalition | It is not an absent body. With affine scoring it can score the bias. State which one is intended and preserve the existing absent-atom semantics. |
| at most four body evaluations | A Viterbi witness is a body; a marginal query uses all its recorded alternatives. Specify per-hop/per-atom versus total counts and include every rival projection. |
| Positive/negative thresholds leave an intermediate zone | State that e.g. 10–30% useful coverage is inconclusive if it meets neither the positive nor the retirement criterion. Do not choose the interpretation after observing results. |

## What the proposed control could establish

A constructed arithmetic host can have known sufficient coalitions and an
exhaustively correct decoder. A successful chart there is an engineering
positive control. R1's finite programs and R4's 64/64 positive controls
already supply related evidence. Another such result would not isolate
why native GPT-2 coverage fails and cannot establish real-model usefulness.
Its incremental question and falsifying control must therefore be named.
Conversely, a negative toy result first triggers an implementation or guard
premise audit; it does not by itself retire all real-model chart approaches.

A real-model known-body adequacy test is more informative about coverage,
but it cannot inherit the toy host's truth or coalition guarantees. These
are different experiments and must not be combined under one success claim.
No fresh data have been generated and no new model outputs inspected for
this proposal. This document is a protocol critique, not a preregistration.

## Suggested follow-up to Grok

Please revise your ONE recommended experiment after addressing the table
above. Choose explicitly between a constructed-host engineering control
and an unfiltered frozen-transformer experiment. Explain the information
gain over the existing R1/R4 positive controls. If using GPT-2, specify
exact native source-coalition generators and measure host correctness
rather than guaranteeing it by prompt construction. Resolve the sample
allocation, valid strict guard, hop protocol and all denominators. Keep
marginal multiplicity and empty-body/absent-body semantics explicit.

Give a full frozen configuration, comparison arm, numerical tolerances,
primary useful-coverage metric, all projected work, positive/negative/
inconclusive regions and a stop rule before any fresh model execution.
Distinguish failure of a premise, failure of the implementation and failure
of the scientific hypothesis. Do not reuse the consumed final 25 cases or
revive the retired certificate-to-truth claim. If neither option offers a
decisive new test, say so rather than manufacture another passing toy.


## Subsequent user-supplied revision: saved-frame diagnostic

The user supplied Grok's revised proposal for a four-arm diagnostic using
only existing R7 development artifacts. A separate protocol freezes the
actual R7 floor semantics, target-score ranking and cardinality-matched
random singleton-plus-bias control. No new training or model calls occur.
All four arms have zero admissions at all three saved endpoints; nine
contexts have a matching singleton without the stronger certificate, and
none passes its centered-tail drift condition. This is local diagnostic
evidence, not a unique causal bottleneck or a claim about larger coalitions.
See PIL PR #155's `pdc_r7_diagnostic_outcome.md` and independent verification.
The original v0.10 release and the consumed final-25 prohibition are unchanged.
