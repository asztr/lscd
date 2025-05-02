---
title: "LSCD: Lomb–Scargle Conditioned Diffusion for Irregular Time-Series Imputation"
description: "A spectrum-conditioned diffusion model that achieves state-of-the-art imputation accuracy on highly irregular and missing time-series data."
theme: academic
tags: [ICML 2025, diffusion, time-series, Lomb–Scargle, imputation]
---

<div align="center">

# LSCD  
### Lomb–Scargle Conditioned Diffusion for Irregular Time-Series Imputation  
ICML 2025 • Vancouver, Canada • Proceedings of Machine Learning Research 267  

[PDF](./assets/LSCD_ICML2025.pdf) • 
[Poster (hi-res)](./assets/LSCD_poster.pdf) • 
[Slides](./assets/LSCD_slides.pdf) • 
<!-- Replace the link below when the repo goes live -->
[Code (coming soon)](https://github.com/your-org/LSCD)  

</div>

---

## Authors & Affiliation

| | Name | Affiliation |
|---|---|---|
| ★ | **Alejandro Sztrajman** \* | University of Cambridge |
| ★ | **Elizabeth Fons** \* | J.P. Morgan AI Research |
| | Yousef El-Laham | J.P. Morgan AI Research |
| | Luciana Ferrer | Univ. of Buenos Aires & CONICET |
| | Svitlana Vyetrenko | J.P. Morgan AI Research |
| | Manuela Veloso | J.P. Morgan AI Research |

\*Equal contribution.  
Correspondence: <elizabeth.fons@jpmorgan.com> :contentReference[oaicite:0]{index=0}&#8203;:contentReference[oaicite:1]{index=1}

---

## Abstract

Time-series imputation with missing or irregularly sampled data remains challenging.  
**LSCD** trains a score-based diffusion model *conditioned on a full Lomb–Scargle periodogram* so it can reason directly over uneven samples, eliminating the FFT grid assumption and costly pre-interpolation.  
Across synthetic and real-world benchmarks with up to 90 % missingness, LSCD recovers values more accurately **and** preserves spectral structure better than state-of-the-art baselines. :contentReference[oaicite:2]{index=2}&#8203;:contentReference[oaicite:3]{index=3}

---

## Why LSCD?

1. **Spectrum-conditioned diffusion.** We fuse the irregular-sampled Lomb–Scargle spectrum into every denoising step, keeping time- and frequency-domains consistent. :contentReference[oaicite:4]{index=4}&#8203;:contentReference[oaicite:5]{index=5}  
2. **Differentiable Lomb–Scargle layer.** An efficient PyTorch implementation lets gradients flow through the periodogram. :contentReference[oaicite:6]{index=6}&#8203;:contentReference[oaicite:7]{index=7}  
3. **Spectral consistency loss.** A final alignment term tightens frequency fidelity even at 90 % missing data. :contentReference[oaicite:8]{index=8}&#8203;:contentReference[oaicite:9]{index=9}  
4. **SOTA results.** LSCD lowers MAE/RMSE while halving Spectral-MAE against strong diffusion, transformer, and GAN baselines on PhysioNet ICU, PM 2.5 and controlled sine data. :contentReference[oaicite:10]{index=10}&#8203;:contentReference[oaicite:11]{index=11}  
5. **Plug-and-play.** Drop-in spectral layer enables other generative models to benefit from Lomb–Scargle without resampling.

---

## Method at a Glance

![Method diagram](./assets/LSCD_architecture.png)  
*Figure 2 from the paper: LSCD injects a spectral encoder and consistency path into a conditional diffusion pipeline.* :contentReference[oaicite:12]{index=12}&#8203;:contentReference[oaicite:13]{index=13}

---

## Key Results

| Dataset | Missing-rate | Best baseline (MAE) | **LSCD (MAE)** | Δ ↓ |
|---------|--------------|---------------------|---------------|-----|
| PhysioNet ICU | 10 % | CSDI 0.219 | **0.211** | **-4 %** |
| PhysioNet ICU | 90 % | CSDI 0.481 | **0.479** | **-0.4 %** |
| PM 2.5 | 10 % | CSDI 9.670 | **9.069** | **-6 %** |

LSCD also attains the lowest Spectral-MAE on every setting above. :contentReference[oaicite:14]{index=14}&#8203;:contentReference[oaicite:15]{index=15}

---

## Paper, Poster & Supplementary

| Format | File |
|--------|------|
| Full paper (camera-ready) | [`LSCD_ICML2025.pdf`](./assets/LSCD_ICML2025.pdf) |
| Poster | [`LSCD_poster.pdf`](./assets/LSCD_poster.pdf) |
| Slides (15 min) | [`LSCD_slides.pdf`](./assets/LSCD_slides.pdf) |
| Supplement | [`LSCD_appendix.pdf`](./assets/LSCD_appendix.pdf) |

---

## BibTeX

```bibtex
@inproceedings{Sztrajman2025LSCD,
  title     = {LSCD: Lomb--Scargle Conditioned Diffusion for Irregular Time-Series Imputation},
  author    = {Alejandro Sztrajman and Elizabeth Fons and Yousef El-Laham and Luciana Ferrer and Svitlana Vyetrenko and Manuela Veloso},
  booktitle = {Proc.\ 42nd International Conference on Machine Learning (ICML)},
  series    = {PMLR},
  volume    = {267},
  pages     = {1--24},
  year      = {2025}
}

