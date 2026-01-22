# Bayesian Linear Regression

This repository includes a notebook that implements Bayesian Linear Regression with a conjugate Gaussian prior and Gaussian likelihood.

- **Notebook**: `Bayesian_Linear_Regression.ipynb`
- **Goal**: Fit a linear model while quantifying parameter and prediction uncertainty via the posterior and predictive distributions.

## What it's about

- Defines a prior over weights (Gaussian) and assumes Gaussian observation noise.
- Derives the closed-form posterior over weights and the predictive distribution.
- Visualizes posterior samples, predictive mean, and uncertainty bands.
- Compares Bayesian estimates to Ordinary Least Squares (frequentist) regression.
- Applies BLR to predict concrete strength from mixture composition features.
- Uses Bayesian Optimization concepts (Expected Improvement) to decide which mixture to try next.

## How to run

1. Open the notebook in Jupyter or VS Code: `Bayesian_Linear_Regression.ipynb`
2. Run cells from top to bottom. Adjustable hyperparameters (prior precision, noise variance) are exposed in the early cells.
3. The notebook uses `gdown` to fetch the concrete strength dataset automatically.

## Dependencies

- Python 3.9+
- Jupyter
- numpy, scipy, matplotlib, seaborn, pandas, gdown, sklearn

Install:
```bash
pip install numpy scipy matplotlib seaborn pandas gdown scikit-learn jupyter
```

## What we're trying to achieve

- **Uncertainty Quantification**: Unlike OLS, BLR provides uncertainty estimates for both parameters and predictions.
- **Concrete Strength Prediction**: Model the mapping from 8 mixture features (Cement, Fly Ash, Slag, Water, HRWR, Fine Aggregate, Curing Temp, Time) to compressive strength.
- **Bayesian Optimization**: Use Expected Improvement (EI) to identify the next candidate mixture to evaluate, balancing exploration and exploitation.

## Outputs

- Posterior mean and covariance of the weights.
- Predictive mean and variance for new inputs.
- Plots showing data, posterior predictive mean, and credible intervals.
- Side-by-side comparison with OLS fit.
- K-fold cross-validation results (R², RMSE, MAE).
- Expected Improvement analysis for experiment selection.

## References

- Bishop, C. M. Pattern Recognition and Machine Learning — Chapter 3.
- Murphy, K. P. Machine Learning: A Probabilistic Perspective — Chapters 7–8.

