# Fractional Water Cover Mapping with EMIT (Validated on AVIRIS)

This repository demonstrates how to derive fractional cover of water from EMIT data and validate the results using AVIRIS imagery. It leverages spectral unmixing methods to separate water from other land-cover components (e.g., vegetation, soil).

---

## Overview
- **EMIT Water Library** (`emit_water_library`): Contains spectral reflectance values of shallow, turbid waters across different regions worldwide.
- **Spectral Unmixing**:
  - We employ the methods provided in [**SpectralUnmixing**](https://github.com/pgbrodrick/SpectralUnmixing) to unmix water and land cover classes.
  - We use **AVIRIS-NG** data to validate the results obtained with the EMIT water spectra.

---

## Requirements
**SpectralUnmixing GitHub Repository**  
   - Clone or download [**pgbrodrick/SpectralUnmixing**](https://github.com/pgbrodrick/SpectralUnmixing).  


---

## Key Files

1. **`emit_water_library`**  
   A collection of spectral reflectance values generated from EMIT data representing shallow, turbid water conditions around the globe.

2. **`convex_hull__n_dims_4_unmix_library_modified.csv`**  
   Spectral reflectance values for NPV (non-photosynthetic vegetation), PV (photosynthetic vegetation), and soil components. These spectra, combined with the EMIT water library, form the basis of the unmixing process.

3. **`simulation_mod`**  
   tests modeled results with simulated data from the EMIT water library of water, NPV, PV, and soil. This helps validate or refine the unmixing approach before applying it to real imagery.

4. **`unmix_demo_mod.ipynb`**
   - AVIRIS-NG scenes were cropped to a 60 m extent and averaged to obtain a "simulated" reflectance. Each pixel was hand-labeled as either npv, pv, soil, or water (aviris_unmix folder)
   - Apply spectral unmixing methods (from the **SpectralUnmixing** repo) to unmix simulated reflectances 
   - Derive fractional water cover estimates from EMIT spectral library and compare with true fractional covers.

---

