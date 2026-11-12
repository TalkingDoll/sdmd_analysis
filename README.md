# SDMD analysis: code for the numerical experiments

Code for Section 5 of the paper "A Second-Order Stochastic Dynamic Mode Decomposition by Richardson Extrapolation".
The four notebooks reproduce every table and the figure of that section. Each notebook is self-contained (all helper
functions are defined inside it), is stored with its outputs, and ends with the LaTeX rows of its tables and the
software versions of the stored run.

| Notebook | Paper item | Results tested | Files written |
|---|---|---|---|
| `5_1_fourier_accuracy_cost.ipynb` | Section 5.1: Tables 2 and 3, rows for the circle of Table 5, Figure 1 | Theorem 4.3, Corollary 4.4, Example 4.5 (orders against the Koopman semigroup, contraction, cost of the matrices), Proposition 3.8 (data term for a fixed observable), Remark 3.5 (exponential of the generator matrix) | `results_fourier_1d.json`, `figures/fig_work_precision.pdf` |
| `5_1_fourier_torus2d.ipynb` | Section 5.1: Table 4, rows for the torus of Table 5, right panel of Figure 1 | Theorem 4.3 and Corollary 4.4 in two dimensions | `results_torus2d.json` |
| `5_2_ou_fixed_dictionary.ipynb` | Section 5.2: Tables 6 and 7 | Theorem 3.3 (time-stepping term, leading operator and lower bound, data term) | none |
| `5_3_spline_dictionary.ipynb` | Section 5.3: Table 8 | SDMD-R and the two forms of SDMD-2 for a dictionary in the domain of the generator but not of its square (Appendix A.2) | none |

In all periodic experiments the time step is `T/n` with `n` the smallest integer such that the step times the norm of
the Galerkin generator is at most 1.5.

## Running

```
pip install -r requirements.txt
jupyter execute --inplace 5_1_fourier_torus2d.ipynb
jupyter execute --inplace 5_1_fourier_accuracy_cost.ipynb
jupyter execute --inplace 5_2_ou_fixed_dictionary.ipynb
jupyter execute --inplace 5_3_spline_dictionary.ipynb
```

Run the commands from this directory. The order of the first two matters only for Figure 1:
`5_1_fourier_accuracy_cost.ipynb` draws the figure from `results_fourier_1d.json`, which it writes itself, and from
`results_torus2d.json`, which `5_1_fourier_torus2d.ipynb` writes. The four notebooks take about six minutes in total on
a two-core machine. The figure is typeset with LaTeX when `latex`, `dvipng`, and the `cm-super` fonts are installed, and
with the STIX fonts of Matplotlib otherwise. It is saved as `figures/fig_work_precision.pdf` at the text width of the
manuscript, in which it is included as `Fig1.pdf`.

## Reproducibility

The sampled computations use fixed seeds (20260507, and 20261029 in the two-dimensional model), and the computations
with exact matrices are deterministic, so the errors in the tables are reproduced up to rounding. The computing times of
Table 5 and of Figure 1 depend on the machine. The stored outputs were obtained on a two-core Linux machine with
Python 3.13, NumPy 2.5, SciPy 1.18 (OpenBLAS), mpmath 1.3, and Matplotlib 3.11.
