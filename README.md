Physics Research Portfolio
Ashok Kumar Ramu
Department of Physics and Astronomy, University of Waterloo
This repository collects my independent and coursework physics research projects,
spanning computational astrophysics and experimental particle physics.
Each project includes full source code, figures, and a written report or paper.

Projects

1. Weak Lensing Forward Model for Flat ΛCDM
   
Computational Cosmology · Gravitational Lensing · Parameter Sensitivity

A weak gravitational lensing forward model built from scratch in Python using only
numpy and scipy — no external cosmology libraries. Implements the full chain from
(Ωₘ, σ₈) through the Eisenstein-Hu transfer function, Heath growth factor, and
lensing convergence kernel to the shear correlation functions ξ₊(θ) and ξ₋(θ) via
the Limber approximation and Hankel transform. Reproduces the S8 tension between
Planck 2018 and KiDS-1000 at ~3.8σ, and characterizes the scale-dependent
sensitivity of ξ₊ to cosmological parameters across angular scales 1–300 arcmin.
Motivated by the UNIONS and Euclid weak lensing surveys.

Key concepts: FLRW background · matter power spectrum · lensing kernel · Limber
approximation · shear correlation functions · S8 tension · parameter sensitivity

2. SNO Solar Neutrino Analysis

Particle Physics · Neutrino Oscillations · Chi-Squared Fitting

Reproduction of the SNO Phase I (2002) measurement of the solar mixing angle
using the CC/NC flux ratio in the adiabatic MSW regime.
Demonstrates that the vacuum oscillation formula is ruled out at 5.5σ
and extracts θ₁₂ = 36.0° ± 2.3°, consistent with the original SNO-only result.
Key concepts: MSW matter effect · adiabatic propagation · chi-squared profiling · error propagation

2. Numerical Reconstruction of the Apparent Orbit of Alpha Centauri

Computational Astrophysics · Orbital Mechanics · Numerical Methods

Numerical reconstruction of the apparent sky-plane orbit of Alpha Centauri B
relative to Alpha Centauri A using published Keplerian orbital elements.
Kepler's equation is solved via Newton's method; the 3D orbit is projected onto
the sky plane to compute angular separation and position angle as functions of time.
Key concepts: Kepler's equation · Newton–Raphson iteration · visual binary geometry · sensitivity analysis

Skills Demonstrated

Scientific computing in Python (NumPy, SciPy, Matplotlib, Pandas)
- Cosmological forward modelling and lensing statistics
- Chi-squared fitting and statistical uncertainty estimation
- Numerical methods (Newton–Raphson, trapezoidal integration, Hankel transforms)
- Physics writing and LaTeX typesetting
- Connecting theoretical models to observational data

Contact:
Feel free to reach out via GitHub or email for questions about any of these projects.
