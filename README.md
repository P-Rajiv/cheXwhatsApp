# Evaluation Metrics for CheXwhatsApp

This repository contains the implementation of evaluation metrics introduced in the paper:
**[CheXwhatsApp: A Dataset for Exploring Challenges in the Diagnosis of Chest X-rays through Mobile Devices](https://cvpr.thecvf.com/virtual/2025/poster/32580)** (CVPR 2025).

---

## 📖 Background

Medical images, when transferred via platforms such as WhatsApp, undergo compression that reduces image quality. This degradation negatively impacts the performance of CNN-based medical image classification models.

To quantify and evaluate these differences — in both **classification performance** and **explainability techniques** — the paper proposes three metrics: **LI-Score, OLS-Score, and PI-Score**.

---

## 📊 Metrics


---

### 1. **OLS-Score (Out-of-Lung Saliency Score)**

* **Definition:** Measures how much of the explainability map (e.g., Grad-CAM heatmap) lies **outside the lung region**.
* **Computation:**

  $$
  \text{OLS} = \frac{\text{heatmap} \cap \text{lung region}}{\text{heatmap pixels}}
  $$
* **Notes:**

  * Lung regions are generated using a pretrained lung-segmentation model.
  * Lower OLS indicates more relevant and localized explanations.

---

### 2. **PI-Score (Prediction Instability Score)**

* **Definition:** Fraction of images where predictions differ between original and WhatsApp-compressed versions.

*  **PI Score** = (number of images with different predictions) / (total number of images)


* **Goal:** Quantify overall prediction instability caused by compression.

---
### 3. **LI-Score (Localization Instability Score)**

* **Definition:** Proportion of cases where high-resolution (HR) and low-resolution (LR) versions of an image are assigned **different areas of prediction**.
* **Goal:** Measure stability of predictions under compression for detection based models.
---

## 🔗 Reference

If you use these metrics or the CheXwhatsApp dataset, please cite:

> Antony, Mariamma; Porana, Rajiv; Lathiya, Sahil M.; Kakileti, Siva Teja; Bhattacharyya, Chiranjib.
> *CheXwhatsApp: A Dataset for Exploring Challenges in the Diagnosis of Chest X-rays through Mobile Devices.*
> CVPR 2025.

---

Do you want me to also add **usage instructions with code snippets** (e.g., `python pi_score.py --input ...`) so the README is not just descriptive but also practical for new users?
