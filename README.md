# Turbofan Engine Failure Analysis

This project analyzes failure behavior in turbofan engines using the NASA CMAPSS dataset. The goal is to explore statistical characteristics of engine degradation and lay the foundation for predictive maintenance models.

## Dataset

The dataset used is from [NASA CMAPSS](https://www.kaggle.com/datasets/behrad3d/nasa-cmaps), which contains run-to-failure records of multiple aircraft engines under various operational conditions.

## Objectives

- Fit statistical distributions to engine failure times.
- Evaluate goodness-of-fit using visual and formal tests.
- Identify a suitable model for degradation behavior.

## Distributions Tested

### Log-Normal

- **Best fit** among tested models.
- Captures the natural skewness of failure times.
- Matches well on Q-Q plots and passes goodness-of-fit tests (K-S test, Anderson-Darling).

### Exponential

- Assumes a **constant hazard rate** (memoryless failures).
- Poor fit due to the presence of **early-life failures** and **wear-out failures**, both of which violate the memoryless assumption.

### Weibull

- Allows for **increasing or decreasing hazard rates**.
- Partially captures the distribution shape.
- Fails to match the **tail behavior**: underestimates long-lasting healthy engines, possibly due to unmodeled latent degradation factors.

## Next Steps

- Extend to survival models and reliability metrics.
- Apply machine learning for latent factors.
- Experiment with mixture models or non-parametric approaches.
