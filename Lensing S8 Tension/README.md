# Weak Lensing Forward Model

A weak gravitational lensing forward model for flat ΛCDM, built from scratch
using only `numpy` and `scipy`. No external cosmology libraries required.

Implements the full chain:
```
(Ωₘ, σ₈) → P(k) → D(z) → W(χ) → Cₗ → ξ₊(θ), ξ₋(θ)
```

Motivated by understanding what the UNIONS and Euclid lensing surveys are
actually measuring before attempting any parameter inference on top.

---

## What it does:

- **Matter power spectrum** via the Eisenstein & Hu (1998) transfer function,
  normalized to σ₈ using a top-hat window integral
- **Growth factor** D(z) from Heath (1977), normalized to unity at z=0
- **Lensing kernel** W(χ) from the FLRW comoving distance and a parametric
  source n(z) at mean redshift z̄ ~ 0.5
- **Shear power spectrum** Cₗ via the Limber approximation
- **Correlation functions** ξ₊ and ξ₋ via Hankel transform using J₀ and J₄
- **S8 tension** reproduced at ~3.8σ between Planck 2018 and KiDS-1000
- **Sensitivity analysis** — fractional response of ξ₊ to 10% shifts in
  Ωₘ and σ₈ across angular scales 1–300 arcmin

---

## Figures

| Figure | Description |
|--------|-------------|
| `fig1_power_spectrum.png` | P(k) varying Ωₘ and σ₈ |
| `fig2_lensing_kernel.png` | W(χ) for three cosmologies |
| `fig3_xi_vary_omega_m.png` | ξ₊, ξ₋ varying Ωₘ |
| `fig4_xi_vary_sigma8.png` | ξ₊, ξ₋ varying σ₈ |
| `fig5_s8_tension.png` | S8 tension: Planck vs KiDS-1000 vs DES Y3 |
| `fig6_sensitivity.png` | Fractional change in ξ₊ for 10% parameter shifts |

---

## Requirements
```
numpy
scipy
matplotlib
```

All standard Anaconda packages. No `pyccl`, no `camb`, no compiler needed.

Install if missing:
```bash
pip install numpy scipy matplotlib
```

---

## Usage

Open `lensing_analysis_v2.ipynb` in Jupyter and run all cells in order.
Runtime is a few minutes on a standard laptop — the Limber integral and
Hankel transforms are the slow steps.

The main callable is:
```python
xi_plus, xi_minus = compute_xi(Omega_m, sigma8)
```

which returns ξ₊ and ξ₋ at the 11 angular bins defined in `THETA_ARCMIN`.

---

## Known limitations

- Uses the **linear** power spectrum throughout. At θ ≲ 10 arcmin nonlinear
  structure growth substantially enhances the signal; the sensitivity results
  in Figure 6 should be interpreted as valid only at θ ≳ 10 arcmin.
  Implementing HaloFit or the EuclidEmulator is the most important numerical
  extension.
- The source n(z) is a smooth analytic approximation, not the real UNIONS n(z).
- The Limber approximation introduces errors of order (1/ℓ)² at the lowest
  multipoles.

---

## Next steps

- Fisher matrix forecast for a UNIONS-like survey geometry
- HaloFit nonlinear power spectrum at small scales
- Neural network inference: train on a grid of simulated ξ₊, ξ₋ vectors
  and recover Ωₘ, σ₈ from real SDSS or UNIONS data

---

## References

- Eisenstein & Hu 1998, ApJ, 496, 605
- Heath 1977, MNRAS, 179, 351
- Bartelmann & Schneider 2001, Phys. Rep., 340, 291
- Aghanim et al. 2020, A&A, 641, A6 (Planck 2018)
- Asgari et al. 2021, A&A, 645, A104 (KiDS-1000)
- Amon et al. 2022, Phys. Rev. D, 105, 023514 (DES Y3)

---

*Ashok Kumar Ramu, University of Waterloo, 2026*
