# Taxi Tipping Paper — LaTeX Source

This folder contains the Springer Nature template source for the final paper.

## Files

- `main.tex` — the main paper source
- `refs.bib` — bibliography (BibTeX format)
- `figures/` — figure files referenced in the paper
  - `fig1_empirical_trajectory.png` — Figure: 13-quarter tip rate trajectory
  - `fig2_phase_cooperative.png` — Figure: Strong signaling phase portrait
  - `fig3_phase_collapse.png` — Figure: Weak signaling phase portrait

## How to compile

### Option A — Overleaf (easiest)

1. Go to <https://www.overleaf.com> and create a new project
2. Choose **New project → Templates → "Springer Nature LaTeX Template"** (search for it)
3. Replace the default `main.tex` with the `main.tex` from this folder
4. Add `refs.bib` and the `figures/` folder to the project
5. Hit **Recompile**

### Option B — local TeX Live / MacTeX

You'll need the Springer Nature class file `sn-jnl.cls` and the supporting Springer style files. Download them from the Springer Nature template page:

<https://www.springernature.com/gp/authors/campaigns/latex-author-support>

Then place `sn-jnl.cls` and the supporting files in this folder and run:

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

## Notes

- Document class options used: `pdflatex,sn-mathphys-num,Numbered` (numbered citations, math + physical sciences template variant)
- Citations use `\cite{}` and the bibliography style is the default Springer Nature numbered style
- Equations use `align` and `equation` environments
- Tables use `booktabs` (`\toprule`, `\midrule`, `\botrule`)
- Figures use `\includegraphics` with PNG files (fine for `pdflatex`)
