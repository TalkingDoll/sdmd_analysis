# SDMD analysis: code for the numerical experiments

The three notebooks reproduce every table and the figure of Section 5 of the paper; each notebook is
self-contained (all helper functions are defined inside it). Run them from this directory (for example
`jupyter lab`, or `jupyter execute <notebook>`); the Fourier notebook writes the figure into `../figures/`,
the folder that `main.tex` loads from, and embeds a PNG preview.

| Notebook | Main result tested | Paper item | Output |
|---|---|---|---|
| `5_1_fourier_accuracy_cost.ipynb` | Theorem 4.3, Corollary 4.4, Example 4.5 (accuracy against the Koopman semigroup, contraction, cost of the matrices) | Section 5.1, Tables 2--3, Figure 1 | printed tables, `results_fourier_1d.json`, `fig_work_precision.pdf` |
| `5_1_fourier_torus2d.ipynb` | Theorem 4.3 and Corollary 4.4 in two dimensions (torus, tensor trigonometric dictionary) | Section 5.1, Table 4, right panel of Figure 1 | printed table (LaTeX rows), `results_torus2d.json` |
| `5_2_ou_fixed_dictionary.ipynb` | Theorem 3.3 (time-stepping term, leading operator and lower bound, data term), Lemma 3.5 and Proposition 3.6 | Section 5.2, Tables 5--6 | printed tables |
