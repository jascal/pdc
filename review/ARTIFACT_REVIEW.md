> Archived pre-publication record. Current remote links and review prompts are in [GROK_REVIEW.md](GROK_REVIEW.md). Statements below about unpublished status describe the original snapshot.

# PDC v0.10 stopped-stage review package

Start with PDC_GOAL.md (original objective), PDC_REQUIREMENTS_AUDIT.md
(requirement-by-requirement disposition), and pdc/spec/EVIDENCE.md
(claim-to-artifact map). The paper is pdc/paper/pdc_calculus.pdf.
This package records a stopped research stage: the original north star
is not achieved. R5's epistemic claim is retired, R7 is negative and R8
has zero coverage on both the 75-context sample and the final 25 contexts.
The latter reservation is consumed. No new policy should call it fresh.

## Integrity and scope

The archive contains a file inventory with sizes and SHA-256 digests,
plus an archive metadata file for the workspace-level review documents.
It contains the saved captures, charts, frames, oracle outputs, source
and strict proof theories. It does not contain a Python environment,
Isabelle installation, GPT-2 weights, compiled runtime or a git repository.
Current native source and PIL package dependencies are included to make
review possible without importing sibling checkout code. These are local
uncommitted source snapshots, not a claim of released upstream revisions.

After extracting into a new directory, verify the main inventory:

```
python3 fieldrun/scripts/pdc_inventory.py --workspace . --out fieldrun/experiments/pdc/release_inventory.json --verify
```

The supplementary package manifest pins this document, the goal and audit
records. Verify their hashes as well before relying on the package.
Hashes establish file identity; the named independent auditors establish
their limited numerical claims. Intermediate R7 parameter trajectories
were not saved: its logged budgets and endpoint frames are distinct evidence.

## Rechecking saved evidence

Use a scratch copy: some original audit CLIs write their reports next to
the saved evidence. Do not rerun one-shot native experiments for integrity
checking or overwrite the original inventory. A fresh independent native
forward requires external pinned model weights; the saved reference
reports are not substitutes for a new execution claim.

From pil, with NumPy and PyTorch installed:

```
PYTHONPATH=. python experiments/verify_pdc_r7.py --data ../fieldrun/experiments/pdc/r7_fixed_data.npz --results results/pdc_r7
```

From fieldrun, with NumPy installed and the pinned GPT-2 model at bundles/gpt2:

```
OPENBLAS_NUM_THREADS=4 python3 scripts/pdc_final_audit_check.py --artifacts experiments/pdc --model-bundle bundles/gpt2
```

The model manifest and weights hashes are pinned in
fieldrun/experiments/pdc/final_audit/manifest.json. The weights are an
external prerequisite, not silently bundled or downloaded. Historical
checks used system Python 3.12 / NumPy 1.26.4 for model reference and PIL's
Python 3.12 environment for learning. Individual run manifests retain
additional protocol and input identities. Installing the included PIL
package requires its declared dependencies, including torch/scipy.

From the extracted root, with Isabelle2025-2 installed:

```
isabelle build -o timeout=40 -d i-orca/examples/pic_core -D i-orca/examples/pdc
isabelle build -o timeout=40 -D i-orca/examples/pic_learn
```

Both sessions disable quick_and_dirty. PIC_Learn is a side-condition
proof, not a theorem that the measured learner improves admission.

From pdc/paper, with TeX Live and latexmk installed:

```
latexmk -pdf -interaction=nonstopmode -halt-on-error pdc_calculus.tex
```

Publication is pending a destination. Draft GitHub paths are intended
locations and do not establish public availability. The package makes
no new positive research claim and authorizes no policy retuning.
