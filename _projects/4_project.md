---
layout: page
title: "Deep Learning–Enhanced ANSA Quantification"
description: Machine learning for time resolved image data
img:
importance: 3
category: work
---

# Time-Resolved HIV DNA Quantification Using Deep Learning and ResNet

This project advances the quantitative capabilities of isothermal nucleic acid amplification by combining time-resolved image data with deep convolutional neural networks (ResNet-18). Building on the Amplification Nucleation Site Analysis (ANSA) framework, we trained models to classify HIV-1 DNA concentrations using temporal-spatial patterns from fluorescence microscopy videos.

## 🧪 Key Contributions:
- Developed two ResNet-18 models trained on seven time points from 15-minute image sequences:
  - A Clinical Utility Model with 95% accuracy across actionable viral load categories.
  - A Logarithmic Model classifying samples across five log-scale bins with 91% accuracy.
- Model input frames selected based on amplification kinetics, capturing lag, exponential, and plateau phases.
- Temporal and spatial fluorescence features enabled classification even at high DNA concentrations where traditional spot counting fails.
- Preprocessing pipeline using PyTorch and scikit-image handled >180-frame .tif stacks for model training and validation.

## 🔬 Why It Matters:
This approach eliminates the need for physical compartmentalization (e.g., droplets) and bypasses quantification limits caused by site overlap. The system significantly extends the dynamic range of isothermal diagnostics while maintaining simplicity in imaging hardware—making it ideal for low-resource settings. The study also introduces a scalable ML workflow for future diagnostic tools based on time-series microscopy.

---

## 📄 Citation:

Martin, C.D., Benson, N.C., Gummalla, N.S., Shimazu, K.N., Bender, A.T., Beck, D.A.C., Posner, J.D.  
Extending the Dynamic Range of Isothermal HIV-1 DNA Amplification Nucleation Site Analysis Using a Residual Neural Network  
Prepared manuscript, 2024.

---

### 📥 PDF:

shared when published
