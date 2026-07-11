# 🌊 Underwater Image Enhancement using DIRS-CLAHS

### Implementation, Analysis & Optimization of the DIRS-CLAHS Algorithm

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green.svg)
![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-orange.svg)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-red.svg)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-F37626.svg)
![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)

---

## 📌 Overview

This repository contains a complete implementation and analysis of the **DIRS-CLAHS (Dual-Image Rayleigh-Stretched Contrast-Limited Adaptive Histogram Specification)** algorithm for **underwater image enhancement**.

The project was completed as part of a Computer Vision assignment at the **National University of Sciences and Technology (NUST), Pakistan**.

In addition to reproducing the original algorithm proposed by **Ghani & Isa**, this work introduces a **Gray World White Balance preprocessing stage**, resulting in measurable improvements in image quality across multiple objective evaluation metrics.

The implementation includes:

* Complete DIRS-CLAHS pipeline
* Image enhancement using OpenCV
* Performance evaluation on the UIEB dataset
* Runtime complexity analysis
* Quantitative comparison using five image quality metrics
* Proposed optimization using Gray World White Balance

---

# 📖 Table of Contents

* Project Motivation
* Problem Statement
* Features
* Dataset
* Methodology
* Processing Pipeline
* Proposed Improvement
* Experimental Results
* Performance Metrics
* Runtime Analysis
* Repository Structure
* Installation
* Usage
* Future Improvements
* References
* Authors

---

# 🌍 Motivation

Underwater imaging is critical for numerous applications including

* Marine biology
* Coral reef monitoring
* Underwater robotics
* Autonomous Underwater Vehicles (AUVs)
* Shipwreck exploration
* Offshore pipeline inspection
* Oceanographic research

However, underwater photographs typically suffer from:

* Strong blue/green color casts
* Loss of red wavelengths
* Low contrast
* Light scattering
* Haze
* Poor visibility
* Blurred object boundaries

These degradations significantly reduce the performance of downstream computer vision tasks such as:

* Object Detection
* Semantic Segmentation
* Image Classification
* Feature Matching
* SLAM
* 3D Reconstruction

Image enhancement is therefore an essential preprocessing step.

---

# ❗ Problem Statement

Traditional histogram equalization methods often over-enhance images and introduce artifacts.

DIRS-CLAHS was proposed to jointly address:

* Color degradation
* Low contrast
* Uneven illumination
* Poor local detail

This project faithfully reproduces the original algorithm and investigates whether additional preprocessing can further improve enhancement quality.

---

# ✨ Features

* Complete implementation from scratch
* Rayleigh histogram stretching
* CLAHE enhancement
* HSV saturation correction
* Objective quality evaluation
* Runtime benchmarking
* Gray World White Balance enhancement
* Quantitative comparison with baseline
* Fully documented implementation

---

# 📂 Dataset

The experiments were performed using the **Underwater Image Enhancement Benchmark (UIEB)** dataset.

Dataset characteristics:

* Real underwater photographs
* Expert-enhanced reference images
* Multiple underwater degradation scenarios
* Widely used benchmark for underwater enhancement research

Images were sampled from four degradation categories for evaluation.

> **Note:** The dataset is not included in this repository due to licensing and size constraints.

---

# 🧠 DIRS-CLAHS Pipeline

The enhancement pipeline consists of the following stages.

```
Input Image
      │
      ▼
RGB Channel Separation
      │
      ▼
Rayleigh Histogram Stretching
      │
      ▼
Dual Image Generation
      │
      ▼
CLAHE Enhancement
      │
      ▼
HSV Conversion
      │
      ▼
Saturation Adjustment
      │
      ▼
RGB Reconstruction
      │
      ▼
Enhanced Image
```

---

# 🚀 Proposed Improvement

A preprocessing stage based on the **Gray World White Balance assumption** was introduced before the original DIRS-CLAHS pipeline.

The rationale is that underwater images often contain severe color imbalance due to wavelength-dependent light absorption.

Applying white balancing first:

* reduces dominant blue-green color casts
* restores missing red information
* improves contrast normalization
* provides a better input for histogram stretching

This modification produced measurable improvements across objective quality metrics.

---

# 📊 Evaluation Metrics

Five quantitative metrics were used.

### PSNR (Peak Signal-to-Noise Ratio)

Measures similarity between enhanced and reference images.

Higher is better.

---

### SSIM (Structural Similarity Index)

Measures preservation of structural information.

Higher is better.

---

### MSE (Mean Squared Error)

Measures pixel-wise reconstruction error.

Lower is better.

---

### UCIQE

A no-reference underwater image quality metric evaluating

* chroma
* saturation
* contrast

Higher is better.

---

### UIQM

Measures

* colorfulness
* sharpness
* contrast

Higher values indicate better perceptual quality.

---

# 📈 Experimental Results

## Baseline DIRS-CLAHS

| Metric |         Score |
| ------ | ------------: |
| PSNR   | **15.307 dB** |
| SSIM   |    **0.6008** |
| UCIQE  |    **0.4009** |

---

## Proposed Method

Gray World White Balance + DIRS-CLAHS

| Metric |         Score |
| ------ | ------------: |
| PSNR   | **15.607 dB** |
| SSIM   |    **0.6149** |

### Improvement

* PSNR increased by **0.30 dB**
* SSIM increased by **0.0141**

These results indicate that the proposed preprocessing step improves both structural preservation and reconstruction quality.

---

# ⚡ Runtime Analysis

The algorithm was evaluated across multiple image resolutions.

Key observation:

* **320×240** achieved approximately **51 FPS** on CPU hardware.

As image resolution increases:

* processing time grows significantly
* real-time performance decreases

Future GPU implementations are expected to provide substantial speed improvements for practical deployment.

---

# 📁 Repository Structure

```
Underwater-Image-Enhancement-DIRS-CLAHS/

│
├── README.md
├── requirements.txt
├── Assignment1_CV_Attiqa_Sana.ipynb
│
├── report/
│   └── Assignment1_Report.pdf
│
├── presentation/
│   └── Assignment1_Presentation.pdf
│
├── images/
│   ├── input/
│   ├── output/
│   └── comparisons/
│
├── results/
│   ├── metrics.csv
│   ├── runtime_analysis.csv
│   └── figures/
│
└── LICENSE
```

---

# 💻 Installation

Clone the repository

```bash
git clone https://github.com/yourusername/Underwater-Image-Enhancement-DIRS-CLAHS.git
```

Move into the project directory

```bash
cd Underwater-Image-Enhancement-DIRS-CLAHS
```

Install dependencies

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook

```bash
jupyter notebook
```

Open

```
Assignment1_CV_Attiqa_Sana.ipynb
```

and run all cells.

---

# 📦 Dependencies

* Python
* OpenCV
* NumPy
* Matplotlib
* scikit-image
* SciPy
* Pillow
* Jupyter Notebook

---

# 📷 Example Results

You can add screenshots like:

```
Original Image

        ↓

DIRS-CLAHS Output

        ↓

Gray World + DIRS-CLAHS Output
```

GitHub visitors appreciate visual comparisons.

---

# 🔬 Future Improvements

Potential directions include:

* Deep Learning-based underwater enhancement
* GPU acceleration using CUDA
* Adaptive parameter optimization
* Real-time deployment on Autonomous Underwater Vehicles
* Integration with underwater object detection pipelines
* Comparison against modern transformer-based enhancement methods

---

# 🎓 Academic Context

This project was developed as part of the **Computer Vision** course at **NUST (SEECS)**.

The work demonstrates practical implementation of research literature, quantitative evaluation, and algorithmic improvement through experimentation.

---

# 📚 References

1. Ghani, A. S. A., & Isa, N. A. M. *Underwater Image Quality Enhancement through Integrated Color Model with Rayleigh Distribution.*

2. Li, C., Guo, J., Cong, R., Pang, Y., & Wang, B. *Underwater Image Enhancement Benchmark (UIEB).*

---

# 👩‍💻 Authors

**Sana Khan Khitran**

BS Data Science

National University of Sciences and Technology (NUST)

Islamabad, Pakistan

---

**Attiqa Bano**

BS Data Science

National University of Sciences and Technology (NUST)

Islamabad, Pakistan

---


