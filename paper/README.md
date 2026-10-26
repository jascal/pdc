# Stopped-stage PDC paper draft

`pdc_calculus.tex` expands the R0–R8 specification, records the triggered
R5 epistemic stop rule, R6's narrowed refused-slice outcome and R8-H's
negative coverage experiment, R7's negative learning result and the final held-out audit. `pdc_calculus.pdf` is the eight-page compiled draft including the v0.16 fixed-coalition diagnostic.
It is a review artifact with its source and PDF in the central GitHub PR;
the complete original evidence snapshot is in the v0.10 GitHub prerelease. It does not close the
full R9 gate or claim admitted-memory transfer, useful R8 service coverage, or criterion-9 success.
The final audit consumed the 25 reserved contexts and has zero coverage.
The evidence map is `spec/EVIDENCE.md`.

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error pdc_calculus.tex
```

Validated with pdfTeX/TeX Live 2023 and latexmk 4.83. Build exit 0, no LaTeX
warnings or overfull boxes after layout correction; the rendered R5 result
page was visually inspected. Every proved claim points to a named i-orca
theory/lemma; empirical claims point to their preregistration and result files.
The experiment artifacts stay in fieldrun/pil, with no executable experiment
or Isabelle source imported into this repo.


The v0.12 Qwen3.5-4B follow-up is included in the current paper: both
readouts commit correctly on all 50 heldout cases, with only full-program
witnesses. This does not establish compact circuits, learning, multi-hop
memory, hallucination reduction over its perfect baseline or compute savings.
See fieldrun PR #148 and the separate `pdc-qwen35-4b-v1` evidence release.
