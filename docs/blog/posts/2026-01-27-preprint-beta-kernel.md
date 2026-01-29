---
date: 2026-01-28
categories:
  - Research
  - Software
  - Open Source
---

# New Preprint: A Fast Rule for Beta Kernel Density Estimation

If you have ever tried to estimate a probability density for data bounded in [0, 1] (like percentages, probabilities, or Gini coefficients) using a standard Gaussian KDE, you know the pain: **Boundary Bias**. The Gaussian kernel "leaks" probability mass below 0 and above 1, ruining the estimate at the edges.

The theoretical solution—the **Beta Kernel**—has existed since 1999, but it has been held back by a major practical flaw: it lacked a simple "rule-of-thumb" bandwidth selector, forcing users to rely on slow, unstable numerical optimization.

In my latest preprint, **"A Fast, Closed-Form Bandwidth Selector for the Beta Kernel Density Estimator"**, I solve this computational bottleneck.

I derive the **Beta Reference Rule**, a closed-form analytical formula for the optimal bandwidth. By eliminating the need for iterative optimization, this new rule matches the accuracy of the "gold standard" methods while delivering a computational speedup of over **35,000x**.


This turns the Beta Kernel from a theoretical curiosity into a practical, drop-in replacement for the Gaussian KDE for bounded data.

### Key Contributions
* **Derivation:** A closed-form bandwidth rule based on the asymptotic mean integrated squared error (AMISE).
* **Heuristic Fallback:** A principled heuristic for "hard" (U-shaped and J-shaped) distributions where standard asymptotics fail.
* **Software:** A fully documented Python package, `beta-kde`, that is API-compatible with scikit-learn.

You can now fit a boundary-corrected density estimator in $\mathcal{O}(1)$ time:

```python
from beta_kde import BetaKDE
import numpy as np

# Fits instantly, no boundary bias
data = np.random.beta(2, 5, 1000)
est = BetaKDE(bandwidth='beta-reference').fit(data.reshape(-1, 1))
```

* **Read the preprint:** [arXiv:2601.19553](https://arxiv.org/pdf/2601.19553)
* **Get the software:** ```pip install beta-kde``` | [GitHub](https://github.com/egonmedhatten/beta-kde)