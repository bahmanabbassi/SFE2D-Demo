# SFE2D-Demo

**Demo version** of SFE2D: a 2D tool for **spatial and spectral feature extraction** from geo-images (PCA, ICA, CWT, S-PCA, S-ICA). The demo is distributed in **P-code** form (`.p` files) with **SFE2D.fig**. Try the workflow with limited parameters; for full functionality, use the [Full version](https://github.com/bahmanabbassi).

**Lead Developer:** Bahman Abbassi  
**Principal Investigator:** Li-Zhen Cheng  
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
2. Add the folder containing the **P-codes** (`.p` files) and **SFE2D.fig** to your MATLAB path, or set it as the current directory.
3. Ensure **SFE2D.fig** is in the same folder as **SFE2D.p**.
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

The demo is provided as **P-codes** (`.p` files) plus the GUI layout file:

- **SFE2D.p**, **SFE2D.fig** — Main GUI (P-code; demo limits enforced).
- **PCA.p**, **fastICA.p**, **fastICA_CWT.p**, **kmeans_fast_Color.p**, **fig.p**, **FilterB.p**, **grd_write.p**, **centerRows.p**, **whitenRows.p**, **PlaceThresholdBars.p** — Core routines (P-code).

---

## Full version

For unrestricted parameters, multiple inputs, and all wavelets, use the **Full version** of SFE2D:

**https://github.com/bahmanabbassi**

---

## References

- Abbassi, B., Cheng, L.Z. **SFE2D: A Hybrid Tool for Spatial and Spectral Feature Extraction.** In: *Mining Technology*. IntechOpen, 2022. DOI: [10.5772/intechopen.101363](http://dx.doi.org/10.5772/intechopen.101363)
- Abbassi, B., Cheng, L-Z., 2020, **SFE2D : Un outil d'extraction de caractéristiques spectrales de géo-images.** Rapport pour le ministère de l'Énergie et des Ressources naturelles, Bureau de la connaissance géoscientifique du Québec. [Lien (SIGEOM)](https://sigeom.mines.gouv.qc.ca/signet/classes/I1103_index?l=f&type_reqt=U&entt=LG&mode=NOUVELLE&format=RESUME&alias_table_crit=EXADOC&mnen_crit=NUMR_RAPR&oper_crit=EGAL&valr_crit=MB%202020-11)
- Abbassi, B., and Cheng, L-Z., 2019, **Integrated feature extraction in high-dimensional geophysical imaging.** Présentation à Québec Mines + Énergie 2019. DOI: [10.13140/RG.2.2.36577.93286](https://doi.org/10.13140/RG.2.2.36577.93286)
- SFE2D User Manual (ver. 2.0), April 2021.

---

## License & copyright

© B. Abbassi, 2022. All rights reserved. This demo is for evaluation only. For licensing and the full version, see the [author’s GitHub](https://github.com/bahmanabbassi) and User Manual.
