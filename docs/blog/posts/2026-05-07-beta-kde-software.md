---
date: 2026-05-07
categories:
  - Software
  - Open Source
  - Python
  - R
  - Julia
---

# Beta KDE Software Rollout: Python, R, and Julia

Following the recent acceptance of my paper on Beta Kernel Density Estimation in the *Journal of Computational and Graphical Statistics* (JCGS), the focus has shifted to making the method immediately accessible to applied researchers. 

I am pleased to share that the new closed-form "HS" bandwidth selector is now available across the three major statistical computing languages.

The goal of this research was to provide a fast, rule-of-thumb solution for boundary-corrected density estimation without relying on unstable numerical optimization. To ensure it is a true plug-and-play solution, the method has been rolled out in the following ecosystems:

* **Python:** Available via `pip install beta-kde` (fully API-compatible with scikit-learn).
* **R:** Now integrated as the default bandwidth selector for beta kernels in the standard `kdensity` CRAN package (v1.2.0+).
* **Julia:** Available via the official package manager using `] add BetaKDE`.

A preprint detailing the derivation of the HS bandwidth rule is available on [arXiv](https://arxiv.org/abs/2601.19553), and the official journal version will be published in JCGS shortly.