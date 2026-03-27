# SNO Solar Neutrino Analysis

**Ashok Kumar Ramu**  
Department of Physics and Astronomy, University of Waterloo  
*March 2026*

Reproduction of the SNO Phase I (2002) measurement of the solar neutrino
mixing angle θ₁₂ using the charged-current (CC) and neutral-current (NC)
flux ratio in the adiabatic MSW regime.

---

## Result
θ₁₂ = 36.0° ± 2.3°   (SNO Phase I only, consistent with 2002 publication)

The vacuum-averaged formula predicts P_ee ≈ 0.548 — ruled out by SNO at **5.5σ**.  
The correct adiabatic MSW formula gives P_ee = sin²(θ₁₂) ≈ 0.303, consistent
with the observed CC/NC ratio of 0.346 ± 0.037.

---

## Physics

High-energy ⁸B solar neutrinos (3–12 MeV) are produced deep in the Sun's core
where electron density is ~10²⁶ cm⁻³. The MSW effect rotates the in-matter
mixing angle to θ_m ≈ 90°, so the neutrino is born as the heavy matter
eigenstate |ν₂ᵐ⟩. Adiabatic propagation through the decreasing solar density
keeps it in that eigenstate all the way to the surface, where it exits as a
pure vacuum mass eigenstate |ν₂⟩. The survival probability is then simply:
P_ee = |⟨νe|ν₂⟩|² = sin²(θ₁₂)

The vacuum-averaged formula P_ee = 1 - ½sin²(2θ) has a hard lower bound of 0.5
and cannot reach the observed ~35% for any physical value of θ₁₂.

---

## Key Quantities

| Quantity | Value |
|---|---|
| φ_CC (SNO Phase I) | 1.76 ± 0.11 × 10⁶ cm⁻² s⁻¹ |
| φ_NC (SNO Phase I) | 5.09 ± 0.45 × 10⁶ cm⁻² s⁻¹ |
| P_ee (CC/NC) | 0.3458 ± 0.0374 |
| θ₁₂ (this work) | 36.0° ± 2.3° |
| θ₁₂ (PDG combined) | 33.4° ± 0.8° |
| Vacuum P_ee ruled out at | 5.5σ |

The ~2.6° offset from the PDG value arises from two known sources:
the Earth's day-night regeneration effect (slightly inflates the observed P_ee)
and the absence of a KamLAND Δm²₂₁ constraint in the SNO-only fit.

---

## Repository Structure
SNO_neutrino_analysis/
├── README.md
├── data/
│   ├── b8spectrum_raw.txt       ← raw B8 solar neutrino spectrum
│   └── b8spectrum.csv           ← cleaned CSV used in analysis
├── figures/
│   ├── panel_A.png              ← survival probability models
│   ├── panel_B.png              ← chi-squared profile
│   ├── panel_C.png              ← B8 spectrum and missing neutrinos
│   └── panel_D.png              ← numerical summary
├── paper/
│   ├── Solar_Neutrino_Oscillation_Analysis.tex
│   └── Solar_Neutrino_Oscillation_Analysis.pdf
└── python_notebook/
└── SNO_neutrino_analysis.ipynb   ← full analysis notebook

---

## How to Run
pip install numpy pandas matplotlib scipy jupyter
jupyter notebook python_notebook/SNO_neutrino_analysis.ipynb

---

## References

- Q. R. Ahmad et al. (SNO Collaboration), *Phys. Rev. Lett.* **89**, 011302 (2002)
  [arXiv:nucl-ex/0204009](https://arxiv.org/abs/nucl-ex/0204009)
- K. Eguchi et al. (KamLAND Collaboration), *Phys. Rev. Lett.* **90**, 021802 (2003)
  [arXiv:hep-ex/0212021](https://arxiv.org/abs/hep-ex/0212021)
- R. L. Workman et al. (PDG), *Prog. Theor. Exp. Phys.* **2022**, 083C01 (2022)
