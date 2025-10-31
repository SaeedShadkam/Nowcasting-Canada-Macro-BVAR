# Nowcasting Canada — Macro BVAR

## Introduction
This project (developed at the start of the COVID‑19 pandemic) demonstrates Bayesian vector autoregression (BVAR) applied to Canadian macroeconomic indicators to evaluate how alternative shock scenarios (for example, housing‑price or CPI shocks) affect short‑term forecasts. The implementation is Colab‑first and integrates R's `BVAR` package with Python via `rpy2`, producing interactive Plotly visualizations embedded in the notebook.

Here is a model results snapshot showing the impact of a Canada CPI shock on Canada Housing Starts:
![IRF Function Results](Figs/IRF2.jpg)

## Data Summary
- The notebook uses monthly macro series (CPI, HPI, Housing Starts, nominal household income, unemployment, plus a large set of FRED‑MD variables). Series are transformed for stationarity (log differences and appropriate first/second differences) and merged.
- Variables are explored with correlation matrices, clustered dendrograms, and other visual diagnostics to guide factor selection.

## Models used and implemented
- Core model: Bayesian Vector Autoregression (BVAR) estimated with the R package `BVAR`.
-- Priors tested and demonstrated in the notebook:
	- Minnesota / Litterman prior (`bv_minnesota`) — standard shrinkage toward random-walk behavior.
	- Sum‑of‑coefficients (SOC) prior (`bv_soc`) — (Doan et al., 1984).
	- Single‑unit‑root (SUR) prior (`bv_sur` / `bv_dummy`) — (Sims; Sims & Zha).
	- Impulse Response Functions (IRFs): computed with `bv_irf` (or `irf()` on fitted objects) to show how shocks propagate over the forecast horizon; the notebook plots IRFs with confidence bands.

- Estimation details: hierarchical prior selection via `bv_priors`, Metropolis‑Hastings (`bv_metropolis` / `bv_mh`) tuning for hyperparameters.

## Model convergence results
- The notebook includes standard Markov chain Monte Carlo (MCMC) diagnostics: trace and density plots for hyperparameters and selected coefficients, Geweke within‑chain diagnostics, and Gelman–Rubin (potential scale reduction) across parallel chains (via R's `coda` functions such as `as.mcmc()` and `gelman.diag()`).

- Trace and density plots (MCMC diagnostics):
  
![Convergence](Figs/Convergence-Analysis.png)

- Model residuals and forecast plots:
  
![Residuals](Figs/Residuals.png)

- Impulse Response Function (IRF):
  
![IRF Function Results](Figs/IRF.png)

Example settings used in the notebook (illustrative): `n_draw=15000`, `n_burn=5000`, `n_thin=1`; Metropolis tuning with `scale_hess` and `adjust_acc` to target acceptance rates (~0.25–0.45). Parallel runs are collected as a list of `bvar` objects and converted to Python for plotting. The notebook shows visually acceptable convergence for the example runs, but diagnostics should be re-checked if you change data or priors.

## Conclusion (resume-ready summary)
- Demonstrates application of Bayesian time‑series modeling (BVAR) to macro nowcasting and scenario analysis.









