---
layout: page
title: "Deep Learning-Enhanced ANSA Quantification"
description: Machine learning for time resolved image data
img:
importance: 1
category: work
---

# Time-Resolved HIV DNA Quantification Using Deep Learning and ResNet

This project advances the quantitative capabilities of isothermal nucleic acid amplification by combining time-resolved image data with deep convolutional neural networks (ResNet-18). Building on the Amplification Nucleation Site Analysis (ANSA) framework, we trained models to classify HIV-1 DNA concentrations using temporal-spatial patterns from fluorescence microscopy videos.

## Key Contributions
- Developed two ResNet-18 models trained on seven time points from 15-minute image sequences:
  - A Clinical Utility Model with 95% accuracy across actionable viral load categories.
  - A Logarithmic Model classifying samples across five log-scale bins with 91% accuracy.
- Model input frames were selected based on amplification kinetics, capturing lag, exponential, and plateau phases.
- Temporal and spatial fluorescence features enabled classification even at high DNA concentrations where traditional spot counting fails.
- A preprocessing pipeline using PyTorch and scikit-image handled more than 180-frame `.tif` stacks for model training and validation.

## Why It Matters
This approach eliminates the need for physical compartmentalization (for example, droplets) and bypasses quantification limits caused by site overlap. The system significantly extends the dynamic range of isothermal diagnostics while maintaining simplicity in imaging hardware, making it ideal for low-resource settings. The study also introduces a scalable ML workflow for future diagnostic tools based on time-series microscopy.

---

## Citation
1. Martin, C. D. et al. Semi-quantitative Classification of HIV-1 Nucleic Acids Using ResNet Image Analysis of Discretized Isothermal Amplification Reactions in a Microfluidic Chip. 2026.06.24.734232 Preprint at https://doi.org/10.64898/2026.06.24.734232 (2026).

---

### PDF
A manuscript describing this workflow is in preparation for PLOS Computational Biology. A pre-print is available on [bioRxiv](https://www.biorxiv.org/content/10.64898/2026.06.24.734232)

