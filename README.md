# Nowcasting-Canada-Macro-BVAR

This project applies Bayesian Vector Autoregression (BVAR) to nowcast Canadian macroeconomic indicators such as GDP growth, inflation, and unemployment. The goal is to leverage Bayesian priors to improve forecasting accuracy in environments with limited data and high uncertainty. This project was implemented at the start of Covid-19 pandamic to anlayze the Canadian economy response to the different possible future shocks.

The notebook demonstrates:

## Data preprocessing and transformation of Canadian macroeconomic time series.
- Specification of Minnesota and shrinkage priors for BVAR.
- Posterior sampling using Gibbs sampling.
- Forecast generation with credible intervals.


## Data Used
More than 100 Canadian macroeconomic indicators sourced from official datasets (e.g., GDP, CPI, unemployment).

Data transformations include log-differencing and scaling to ensure stationarity.


## Models Implemented
- Feature selection (Correlation matrix + Clustering Dendogram)
- Bayesian VAR (BVAR) implemented with 3 different priors (Sum of Coefficients (Doan et al. (1984)), Single unit root prior (Sims (1993), SIms and Zha (1998)), and Litterman/Minnesota prior setttings).
- Emplyoing Markov Chain Monte Carlo (Metropolis-Hastings settings)
- Analyzing Model Convergence via trace and density plots:

  
- Model Residuals:

  


## Results
**- Forecast Accuracy:** The BVAR model provides robust short-term forecasts with uncertainty bounds.

**- Posterior Distributions:** Visualizations show parameter uncertainty and credible intervals.

**- Impulse Response Functions (IRFs):** Capture dynamic responses of macroeconomic variables to shocks:


## Conclusion
The BVAR approach improves forecast reliability by incorporating prior beliefs and uncertainty quantification. This methodology is particularly useful for policy analysis and real-time decision-making in macroeconomics








