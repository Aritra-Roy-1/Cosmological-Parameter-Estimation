# Cosmological Parameter Estimation

End-to-end analysis of a galaxy cluster dataset to estimate the **Hubble constant H₀** and quantify the **dark matter fraction** of the cluster, using observational spectroscopy and Cepheid variable stars.

---

## Overview

This notebook reconstructs a mini cosmic distance ladder using simulated observational data:

1. **Redshift & Radial Velocity** — Hα spectral line shifts are used to compute radial velocities for all galaxies in the field. Velocity-based and angular radial cuts isolate the gravitationally bound cluster core (~295 galaxies).

2. **Cepheid Calibration (Leavitt's Law)** — ~5000 Galactic Cepheids from a Gaia-like catalogue are used to calibrate the Period–Luminosity relation (α ≈ −1.83, β ≈ 0.26) via 3σ-clipped linear regression.

3. **Galaxy Distances** — The calibrated P–L relation is applied to extragalactic Cepheids to estimate distances to individual galaxies, with per-galaxy median-based outlier rejection.

4. **Hubble Constant** — Gaussian fits to the velocity and distance distributions yield **H₀ = 46.47 ± 35.90 km/s/Mpc**. The large uncertainty is consistent with the accepted value (~73.5 km/s/Mpc) within error margins, and the underestimation is attributed to peculiar velocities dominating at ~20 Mpc.

5. **Dark Matter** — The Virial Theorem gives a total cluster mass of ~2.69 × 10¹⁴ M☉. Luminosity-based mass estimates yield a visible component of ~3.48 × 10¹³ M☉, implying a **dark matter fraction of ~87%** — consistent with modern observations of galaxy clusters.

---

## Repository Structure

```
├── Cosmological_Parameter_Estimation.ipynb   # Main analysis notebook
├── galaxy.csv                                # Galaxy spectroscopic data (Hα wavelengths, positions)
├── gaia.csv                                  # Galactic Cepheid catalogue (period, magnitude, parallax)
├── cepheid.csv                               # Extragalactic Cepheid data (period, magnitude, host galaxy)
└── README.md
```

---

## Requirements

```
numpy
pandas
matplotlib
scipy
```

Install with:
```bash
pip install numpy pandas matplotlib scipy
```

---

## Key Results

| Quantity | Value |
|---|---|
| Cluster angular diameter | ~7.18° |
| Cluster distance | ~13.5 Mpc |
| Cluster physical diameter | ~1.69 Mpc |
| Velocity dispersion σᵥ | ~437 km/s |
| P–L slope α | −1.826 |
| P–L intercept β | 0.257 |
| Hubble constant H₀ | 46.47 ± 35.90 km/s/Mpc |
| Total cluster mass | 2.69 × 10¹⁴ M☉ |
| Visible mass | 3.48 × 10¹³ M☉ |
| Dark matter fraction | ~87% |

---

## Notes

- RA coordinates are converted from sexagesimal (h m s) to degrees with the factor of 15.
- The P–L zero-point offset from literature values is expected — Gaia G-band photometry is used without extinction correction or band transformation.
- The H₀ underestimate is a known effect at short distances where peculiar velocities (~300–500 km/s) are comparable to the Hubble flow.

---

*Project submitted as part of a supervised research application in observational/computational astrophysics.*
