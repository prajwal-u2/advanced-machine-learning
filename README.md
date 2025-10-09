# advanced-machine-learning

## Bayesian Linear Regression

This repository includes a notebook that implements Bayesian Linear Regression with a conjugate Gaussian prior and Gaussian likelihood.

- **Notebook**: `Bayesian_Linear_Regression/Bayesian_Linear_Regression.ipynb`
- **Goal**: Fit a linear model while quantifying parameter and prediction uncertainty via the posterior and predictive distributions.

### What the notebook does
- Defines a prior over weights (Gaussian) and assumes Gaussian observation noise.
- Derives the closed-form posterior over weights and the predictive distribution.
- Visualizes posterior samples, predictive mean, and uncertainty bands.
- Compares Bayesian estimates to Ordinary Least Squares (frequentist) regression.

### How to run
1. Open the notebook in Jupyter or VS Code:
   - `Bayesian_Linear_Regression/Bayesian_Linear_Regression.ipynb`
2. Run cells from top to bottom. Adjustable hyperparameters (prior precision, noise variance) are exposed in the early cells.

### Dependencies
- Python 3.9+
- Jupyter
- numpy, scipy, matplotlib, seaborn

Install (example):
```bash
pip install numpy scipy matplotlib seaborn jupyter
```

### Outputs and visuals
- Posterior mean and covariance of the weights.
- Predictive mean and variance for new inputs.
- Plots showing data, posterior predictive mean, and credible intervals.
- Side-by-side comparison with OLS fit to highlight uncertainty quantification.

### References
- Bishop, C. M. Pattern Recognition and Machine Learning — Chapter 3.
- Murphy, K. P. Machine Learning: A Probabilistic Perspective — Chapters 7–8.

## Problem: Predicting Concrete Strength and Choosing the Next Experiment

The notebook applies Bayesian Linear Regression to predict the compressive strength of concrete from mixture composition features and then uses Bayesian Optimization concepts to decide which mixture to try next.

- **Task**: Model the mapping from mixture inputs to compressive strength, quantify predictive uncertainty, and identify the next candidate mixture to evaluate.
- **Dataset**: Concrete strength dataset with 8 input features (e.g., Cement, Fly Ash, Slag, Water, HRWR, Fine Aggregate, Curing Temp, Time) and the target `strength`.
- **Surrogate Model**: BLR provides predictive mean `μ(x)` and uncertainty `σ(x)` for any candidate `x`.
- **Acquisition Function**: Expected Improvement (EI)
  - `EI(x) = (μ(x) − y*) Φ(Z) + σ(x) φ(Z)`, where `Z = (μ(x) − y*) / σ(x)` and `y*` is the best observed strength.
  - Balances exploration (large `σ(x)`) and exploitation (large `μ(x)`).

### How it connects in the notebook
- Builds BLR for concrete strength with k-fold CV and reports R2/RMSE/MAE.
- Derives and interprets EI from decision-theory perspective.
- Explains how to pick the next experiment by maximizing EI over candidate mixtures.

### Reproduce the analysis
1. Open `Bayesian_Linear_Regression/Bayesian_Linear_Regression.ipynb`.
2. Run the data loading cell (uses `gdown` to fetch the dataset).
3. Execute the BLR model cells to fit and evaluate.
4. Follow the Bayesian Optimization section to compute EI and select the next candidate.