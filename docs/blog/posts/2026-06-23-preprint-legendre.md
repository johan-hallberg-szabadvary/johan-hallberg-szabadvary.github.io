---
date: 2026-06-23
categories:
  - Research
  - Conformal Prediction
  - Conformal Test Martingales
---

# Betting on Moments: Legendre Jumper Martingales for Online Exchangeability Testing

In online exchangeability testing, conformal test martingales—such as the Simple Jumper—are powerful tools for detecting distributional shifts in data streams. However, they are traditionally limited to detecting location shifts (mean). Extending these martingales to detect higher-order deviations (like variance, skewness, or kurtosis) is theoretically straightforward but computationally prohibitive.

The requirement to adapt to multiple moments simultaneously leads to an exponential expansion of the martingale's state space—a "jumping tax" that makes real-time deployment impossible.

In my latest preprint, "Betting on Moments: Legendre Jumper Martingales for Online Exchangeability Testing", I bypass this combinatorial bottleneck.

By reformulating the betting function using a basis of shifted Legendre polynomials, I provide a closed-form approach to detecting complex distributional deviations. To ensure scalability, I introduce the Variational Legendre Jumper, which uses a mean-field approximation to decouple the joint adaptation. This reduces the computational scaling from exponential to $\mathcal{O}(1)$ time.

### Key Contributions
* **Orthogonal Basis:** A Legendre-polynomial framework for capturing higher-order moments.
* **Variational Inference:** A mean-field approach that eliminates the "jumping tax" while preserving statistical power.

* **Read the preprint:** [arXiv:2606.20859](https://arxiv.org/abs/2606.20859)
* **Get the software:** ```pip install online-cp``` | [GitHub](https://github.com/egonmedhatten/online-cp)