# GSA for Robust XAI — SAMO Summer School 2026

**Giulia Vannucci · University of Naples Federico II**

Exercise material for the hands-on session accompanying the talk:

> *Global Sensitivity Analysis for Robust XAI: Quantifying Clinical Risk and Prediction Instability in Dermoscopic Image Classification*
> Vannucci, Coppolecchia & Siciliano (2026) — **Risk Analysis** (accepted March 2026)

---

## Goal

Replicate the core GSA pipeline from the paper on a real clinical black-box model: a DenseNet-121 CNN trained for melanoma classification on the HAM10000 dataset.

You will apply Sobol indices to quantify which photometric parameters (brightness, contrast, sharpness, saturation, hue) drive the most variance in the model's predicted probability of melanoma — and explore what happens when you change the bounds, aggregate over multiple images, and compare with a different model.

---

## Files in this repository

| File | Description |
|------|-------------|
| `GSA_SAMO2026_exercise.ipynb` | Colab notebook for the exercise |
| `ISIC_0024940.jpg` ... `ISIC_0025520.jpg` | 5 melanoma images from ISIC test set |
| `ISIC_0024452.jpg` ... `ISIC_0024855.jpg` | 5 non-melanoma images from ISIC test set |

The model `melanoma_model.keras` (DenseNet-121, 34MB) is downloaded automatically from Google Drive when you run the notebook.

---

## How to run

1. Open the notebook in Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Giuliana87/Samo2026/blob/main/GSA_SAMO2026_exercise.ipynb)

2. Run cells 1–5 (setup, model, images, perturbation function, sampling) — nothing to implement here.

3. **Cell 6** — implement the evaluation loop yourself.

4. **Cell 7** — compute Sobol indices with SALib.

5. **Cell 8** — already implemented as an example: plot your results and compare with paper Table 2.

6. **Cell 9** — change the bounds and observe what happens to the ranking.

7. **Cell 10** — run the same pipeline with ResNet50 and compare.

8. **Cell 11** — final challenge: loop over all 10 images and aggregate ST.

---

## Reference

Saltelli, A. (2002). Making best use of model evaluations to compute sensitivity indices. *Computer Physics Communications*, 145(2), 280–297.

Saltelli, A. (2002). Sensitivity analysis for importance assessment. *Risk Analysis*, 22(3), 579–590.

Vannucci, G., Coppolecchia, R.P.W., & Siciliano, R. (2026). Global Sensitivity Analysis for Robust XAI: Quantifying Clinical Risk and Prediction Instability in Dermoscopic Image Classification. *Risk Analysis* (accepted March 2026).
