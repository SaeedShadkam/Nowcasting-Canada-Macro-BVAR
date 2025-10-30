# Nowcasting-Canada-Macro-BVAR

This project applies Bayesian Vector Autoregression (BVAR) to nowcast Canadian macroeconomic indicators such as GDP growth, inflation, and unemployment. The goal is to leverage Bayesian priors to improve forecasting accuracy in environments with limited data and high uncertainty.

The notebook demonstrates:

## Data preprocessing and transformation of Canadian macroeconomic time series.
- Specification of Minnesota and shrinkage priors for BVAR.
- Posterior sampling using Gibbs sampling.
- Forecast generation with credible intervals.


## Data Used
Canadian macroeconomic indicators sourced from official datasets (e.g., GDP, CPI, unemployment).

Data transformations include log-differencing and scaling to ensure stationarity.


## Models Implemented
- Bayesian VAR (BVAR) with Minnesota prior.
- Hyperparameter tuning for lag decay and variance shrinkage.
- Gibbs sampling for posterior estimation.


## Results
**Forecast Accuracy:** The BVAR model provides robust short-term forecasts with uncertainty bounds.
**Posterior Distributions:** Visualizations show parameter uncertainty and credible intervals.
**Impulse Response Functions (IRFs):** Capture dynamic responses of macroeconomic variables to shocks.


## Conclusion
The BVAR approach improves forecast reliability by incorporating prior beliefs and uncertainty quantification. This methodology is particularly useful for policy analysis and real-time decision-making in macroeconomics








