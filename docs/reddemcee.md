# ```reddemcee```
![Front logo](img/dark/logo-full-crop.svg#only-dark){width="50%"}
![Front logo](img/light/logo-full-crop.svg#only-light){width="50%"}

[`reddemcee`](https://reddemcee.readthedocs.io/en/latest) - Next-generation ladder adaptation and evidence estimators for Adaptive Parallel Tempering.

Markov Chain Monte Carlo (MCMC) excels at sampling complex posteriors but traditionally lags behind nested sampling in accurate evidence estimation, which is crucial for model comparison in astrophysical problems.

Here I introduce `reddemcee`, an Adaptive Parallel Tempering Ensemble Sampler, aiming to close this gap by simultaneously presenting next-generation automated temperature-ladder adaptation techniques and robust, low-bias evidence estimators.

`reddemcee` couples an affine-invariant stretch move with five interchangeable ladder-adaptation objectives--Uniform Swap Acceptance Rate, Swap Mean Distance, Gaussian-Area Overlap, Small Gaussian Gap, and Equalised Thermodynamic Length--implemented through a common differential update rule. Three evidence estimators are provided: Curvature-aware Thermodynamic Integration (TI+), Geometric-Bridge Stepping Stones (SS+), and a novel Hybrid algorithm that blends both approaches (H+).
