# SFE2D-Demo

**Demo version** of SFE2D: a 2D tool for **spatial and spectral feature extraction** from geo-images (PCA, ICA, CWT, S-PCA, S-ICA). Try the workflow with limited parameters; for full functionality, use the [Full version](https://github.com/bahmanabbassi).

**Authors:** Bahman Abbassi, Li Zhen Cheng  
**Affiliation:** Institut de Recherche en Mines et en Environnement (IRME), Université du Québec en Abitibi-Témiscamingue (UQAT)

---

## What this demo includes

- Same GUI and workflow as SFE2D: load imagery and/or point data, run spatial (PCA, kICA, nICA) and spectral (CWT, S-PCA, S-kICA, S-nICA) extraction, visualize and export.
- **Demo limits** (full version removes these):
  - **Inputs:** 1 satellite image, 1 XYZ (point) dataset.
  - **Grid:** max 500 pixels in X and Y (suggested spacing shown if exceeded).
  - **Spatial ICA:** convergence fixed at 1e-4, max iterations 20.
  - **Spectral:** max 3 scales, 6 angles; mother wavelet **Gaussian** only; S-ICA convergence 1e-4, max iterations 20; CWT Filter and Scale Dilation fixed at 1.
  - **Segmentation:** max 6 colors.

When a limit is reached, the GUI shows a message and directs you to the full version.

---

## Requirements

- **MATLAB:** R2021a (9.10) or later; tested up to R2025b.
- **Toolbox:** Wavelet Toolbox (for 2D CWT).
- **System:** Windows 7/8/10; ≥ 8 GB RAM recommended.

---

## Installation & run

1. Clone or download this repository.
2. Add the **M Files** folder to your MATLAB path (or set it as the current directory).
3. Ensure **SFE2D.fig** is in the same folder as **SFE2D.m**.
4. In the MATLAB Command Window:
   ```matlab
   SFE2D
   ```

---

## Workflow (short)

1. **Preprocessing** — Set bounds (Min/Max Lon/Lat), **Spacing (Arc-Sec)** (use suggested value if you hit the 500-pixel limit), load one **Image** and/or one **XYZ Data** CSV.
2. **Spatial** — Choose **Select Inputs** (Satellite / Point Data / All), then run **PCA**, **kICA**, and/or **nICA**.
3. **Spectral** — Set **CWT Inputs**, scales (≤3), angles (≤6), mother wavelet Gaussian, then **CWT**, then **S-PCA**, **S-kICA**, and/or **S-nICA**.
4. **Plot & export** — Use **Plot Results** and **Exporting** (Surfer grids, XYZ CSV).

---

## Repository contents

- **SFE2D.m**, **SFE2D.fig** — Main GUI (demo limits enforced).
- **PCA.m**, **fastICA.m**, **fastICA_CWT.m**, **kmeans_fast_Color.m**, **fig.m**, **FilterB.m**, **grd_write.m**, **centerRows.m**, **whitenRows.m**, **PlaceThresholdBars.m** — Core routines.
- **build_pcodes.m** — Script to generate P-codes from all M-files (`build_pcodes` or `build_pcodes('P Files')`).

---

## Full version

For unrestricted parameters, multiple inputs, and all wavelets, use the **Full version** of SFE2D:

**https://github.com/bahmanabbassi**

---

## References

- Abbassi, B., Cheng, L.Z. **SFE2D: A Hybrid Tool for Spatial and Spectral Feature Extraction.** In: *Mining Technology*. IntechOpen, 2022. DOI: [10.5772/intechopen.101363](http://dx.doi.org/10.5772/intechopen.101363)
- SFE2D User Manual (ver. 2.0), April 2021.

---

## License & copyright

© B. Abbassi, 2020. All rights reserved. This demo is for evaluation only. For licensing and the full version, see the [author’s GitHub](https://github.com/bahmanabbassi) and User Manual.
