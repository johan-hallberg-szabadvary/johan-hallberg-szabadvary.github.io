---
date: 2026-01-06
categories:
  - Research
  - Conformal Prediction
---

# New Preprint: Conformal Blindness

We typically assume that if a data distribution shifts drastically, our Conformal Test Martingales (CTMs) will explode and warn us. The standard logic is simple: exchangeability implies uniform p-values; therefore, non-uniform p-values imply a break in exchangeability.

**But what if the p-values stay uniform while the data moves?**

In my new note, **"Conformal Blindness: A Note on A-Cryptic change-points"**, I demonstrate that this is possible.

By constructing a specific counter-example using **bivariate Gaussian distributions** and an **oracle conformity measure**, I identify a trajectory (an "A-cryptic line") along which the data can shift arbitrarily far without triggering *any* CTM. In this specific setting, the p-values remain perfectly uniform, and the CTM remains flat.

This finding serves as a proof-of-concept for a fundamental "blind spot" in conformal testing: we only detect shifts that are distinguishable by our specific conformity measure. If the shift aligns with the measure's blind spot, we are flying blind.

* **Read the full note:** [arXiv:2601.01147](https://arxiv.org/abs/2601.01147)