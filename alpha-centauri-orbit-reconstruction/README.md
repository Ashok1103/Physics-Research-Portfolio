# Numerical Reconstruction of the Apparent Orbit of Alpha Centauri

**Ashok Kumar Ramu**  
Department of Physics and Astronomy, University of Waterloo  
*March 2026*

Numerical reconstruction of the apparent sky-plane orbit of Alpha Centauri B
relative to Alpha Centauri A using published Keplerian orbital elements.

---

## Result

The apparent orbit is successfully reconstructed over one full orbital period (~79.9 years),
reproducing the strongly foreshortened, eccentric ellipse characteristic of the system.
Newton-Raphson iteration solves Kepler's equation to **machine precision (~10⁻¹⁵)**.

---

## Physics

Alpha Centauri AB is the nearest stellar binary system to the Sun (~1.34 pc).
The true 3D Keplerian orbit is not observed directly — instead, observers measure
a time-dependent projection onto the sky plane characterized by angular separation
ρ and position angle θ.

**Kepler's equation** (solved via Newton–Raphson):
E - e sin(E) = M(t)

**Sky-plane projection** (standard visual binary geometry):
x = r [cos Ω cos(ν+ω) - sin Ω sin(ν+ω) cos i]
y = r [sin Ω cos(ν+ω) + cos Ω sin(ν+ω) cos i]

**Observables:**
ρ = √(x² + y²)        (angular separation)
θ = arctan2(x, y)     (position angle, eastward from north)

---

## Key Results

| Quantity | Value |
|---|---|
| Orbital period | ~79.9 years |
| Eccentricity | ~0.518 |
| Max separation (apoastron ~1980) | ~21.7 arcsec |
| Min separation (periastron ~1956) | ~2.1 arcsec |
| Newton–Raphson residual | ~10⁻¹⁵ (machine precision) |

A sensitivity analysis shows that a ±1° variation in the longitude of the ascending
node Ω produces a measurable rotation of the projected orbit, detectable in
high-precision astrometry.

---

## Repository Structure
alpha-centauri-orbit-reconstruction/
├── README.md
├── Alpha_Centauri_Apparent_Orbit.ipynb   ← full analysis notebook
├── figures/
│   ├── Orbit.png        ← projected sky-plane orbit
│   ├── Separation.png   ← angular separation vs time
│   └── Angle.png        ← position angle vs time
└── paper/
├── Alpha_Centauri.tex
└── Numerical_Reconstruction_of_Stellar_Orbit.pdf

---

## How to Run
pip install numpy matplotlib scipy jupyter
jupyter notebook Alpha_Centauri_Apparent_Orbit.ipynb

---

## References

- D. Pourbaix et al., "The orbit of α Centauri revisited,"
  *Astronomy & Astrophysics* **386**, 280–285 (2002)
- B. Koberlein and D. Meisel, *Astrophysics through Computation*,
  Cambridge University Press, 2016
- C. R. Harris et al., "Array programming with NumPy," *Nature* **585**, 357–362 (2020)
- J. D. Hunter, "Matplotlib: A 2D graphics environment,"
  *Computing in Science & Engineering* **9**(3), 90–95 (2007)
