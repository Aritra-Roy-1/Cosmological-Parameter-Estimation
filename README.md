# Cosmological Parameter Estimation

End-to-end analysis of a galaxy cluster dataset to estimate the **Hubble constant H₀** and quantify the **dark matter fraction** of the cluster, using observational spectroscopy and Cepheid variable stars.

---

## Overview

This notebook reconstructs a mini cosmic distance ladder using simulated observational data:

1. **Redshift & Radial Velocity** — Hα spectral line shifts are used to compute radial velocities for all galaxies in the field.

2. **Cepheid Calibration (Leavitt's Law)** — ~5000 Galactic Cepheids from a Gaia-like catalogue are used to calibrate the Period–Luminosity relation.

3. **Galaxy Distances** — The calibrated P–L relation is applied to extragalactic Cepheids to calculate distances to individual galaxies.

4. **Hubble's Constant** — Gaussian fits to the velocity and distance distributions are used to estimate the Hubble's Constant.

6. **Dark Matter** — The amount of non-luminous dark matter is computed using the Virial Theorem and luminosity-based mass estimates.

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
| Cluster angular diameter | ~7.40° |
| Cluster distance | ~14.54Mpc |
| Cluster physical diameter | ~1.88 Mpc |
| Velocity dispersion σᵥ | ~516.31 km/s |
| P–L slope α | −1.826 |
| P–L intercept β | 0.257 |
| Hubble constant H₀ | 46.47 ± 35.90 km/s/Mpc |
| Total cluster mass | 2.69 × 10¹⁴ M☉ |
| Visible mass | 3.48 × 10¹³ M☉ |
| Dark matter fraction | ~87% |

---

*Self-guided project in observational/computational astrophysics.*
