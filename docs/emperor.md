[`EMPEROR`](https://astroemperor.readthedocs.io/en/latest) (Exoplanet Mcmc Parallel tEmpering for Rv Orbit Retrieval), is an open-source Python-based framework designed for the efficient detection and characterisation of exoplanets by using radial velocity (RV) methods and astrometry.

Its combination of performance, flexibility, and ease of use makes it a robust tool for any exoplanet detection endeavour. `EMPEROR` integrates Dynamic Nested Sampling (DNS) and Adaptive Parallel Tempering (APT) Markov Chain Monte Carlo (MCMC), supporting multiple noise models such as Gaussian Processes (GPs) and Moving Averages (MA). The framework facilitates systematic model comparison using statistical metrics, including Bayesian evidence and Bayes Information Criterion (BIC), while providing automated, publish-ready visualisations.

The code is easy to install and easy to use, providing full publication-ready plots and copy-pastable latex tables:

```python

import astroemperor as emp
import numpy as np
np.random.seed(1234)

sim = emp.Simulation()
sim.load_data('51Peg')  # folder read from /datafiles/

sim.engine_config['setup'] = [10, 500, 3000, 1]  # ntemps, nwalkers, nsweeps, nsteps

sim.add_condition(['Period 1', 'limits', [3, 5]])  # short chain
```

Some Automatic Plots:
=== "Best Fit"
    Full model, and phase-folded per planet
    ![Best Fit](img/emperor/model/k1.png)
=== "Arviz: Trace and More"
    For every model block:
    === "Corner"
        ![Corner](img/emperor/trace/corner_kep.png)
    === "Trace"
        ![Trace](img/emperor/trace/trace_kep.png)
    === "HDI Intervals"
        ![hdi-intervals](img/emperor/trace/hdi_off.png)
    === "Normalised Posteriors"
        ![norm-post](img/emperor/trace/normpost_amp.png)


=== "Posteriors"
    For every model block, and temperature:
    === "Scatter"
        ![Posteriors1](img/emperor/posteriors/scatter_kep_t0.png)
    === "Higher temperatures!"
        ![Posteriors2](img/emperor/posteriors/scatter_kep_t8.png)
    === "Different styles 1"
        ![Posteriors3](img/emperor/posteriors/gau_offset_t0.png)
    === "Different styles 1"
        ![Posteriors4](img/emperor/posteriors/hex_offset_t0.png)
            
=== "Estimates"
    For every parameter:
    === "GME"
        ![GME](img/emperor/gm/kep_amp.png)
    === "Histograms"
        ![histo](img/emperor/histograms/OffsetBlock.png)


=== "Temperature Ladder"
    === "Swap Acceptance"
        ![temp_rates](img/emperor/betas/rates.png)
    === "Ladder"
        ![temp_ladder](img/emperor/betas/beta_ladder.png)
    === "Density"
        ![temp_dens](img/emperor/betas/density.png)
