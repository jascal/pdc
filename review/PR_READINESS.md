# PDC v0.17 PR readiness

Review preparation, 27 October 2026. This is a documentation and CI-readiness
record, not a new measurement or a passing scientific gate. No PR is merged
or set to auto-merge, and this pass does not authorize an experiment.

All six existing PRs are open, non-draft and conflict-free. There are no
submitted reviews or unresolved inline review threads at this snapshot.
Human review is still required; these facts are not reviewer approval.

| Role | PR | Base | Check status |
|---|---|---|---|
| Specification, paper and evidence | [pdc #1](https://github.com/jascal/pdc/pull/1) | main | No hosted checks reported; PDF build and documentation checks pass |
| Original runtime/charts/service | [fieldrun #147](https://github.com/jascal/fieldrun/pull/147) | master | [CI passed](https://github.com/jascal/fieldrun/actions/runs/40225486554) |
| Archived Qwen follow-up | [fieldrun #148](https://github.com/jascal/fieldrun/pull/148) | research/pdc-stopped-stage (#147) | [CI passed](https://github.com/jascal/fieldrun/actions/runs/40404779667) |
| Normalization correction/replay hook | [fieldrun #149](https://github.com/jascal/fieldrun/pull/149) | research/pdc-qwen35-4b (#148) | [CI passed](https://github.com/jascal/fieldrun/actions/runs/40408285562) |
| Admission oracle and guarded learning | [pil #155](https://github.com/jascal/pil/pull/155) | main | [CI passed](https://github.com/jascal/pil/actions/runs/40495786960) after lint-only correction |
| Kernel proofs | [i-orca #37](https://github.com/jascal/i-orca/pull/37) | main | No hosted checks reported; recorded strict Isabelle build is cited in the PR/evidence map |

Review the fieldrun stack in order #147, #148, #149. The proof and learning
PRs can be reviewed independently; the central document links all evidence.
The bases above retain the intended small diffs. No retargeting or merge is
part of this preparation.

PIL's previous hosted check failed on four lint findings in
`experiments/pdc_qwen35_learning_check.py`. The approved correction changes
import spacing and line wrapping only (`81f6b53`). The Python AST is identical, the
repository-wide lint check passes locally, and the updated hosted CI
passes. No experiment/data/result file is changed. The frozen evidence archives retain their original bytes.

The citation/tag correction in pdc commit `f0d1a9f` keeps spec v0.17 and
historical version notes unchanged, marks the finished R8/criterion-9
sample unmet, and distinguishes the archived Qwen binary from the corrected
runtime. The paper is rebuilt with the normalization correction together on
the final page. [EVIDENCE.md](../spec/EVIDENCE.md) links the immutable raw
releases and their hashes.

Scientific limits remain: the original final 25 contexts are consumed; old
Qwen counts concern archived binary
`90cd5c8dda5b1f5c16888387baa92b78205c82a99b0eb04a98679ca324c1928d`;
no old coalition/admission count is a corrected-runtime count. Useful
service and admitted-memory transfer remain unestablished. No frozen
threshold, body, model or failed scientific gate was changed here.
