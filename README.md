# QRNG Randomness Evaluation Framework

## Overview
This project proposes a hybrid framework to evaluate the randomness of numerical data, particularly focusing on quantum-generated random numbers (QRNG).

The framework combines Statistical Testing (NIST SP 800-22) with Spatial Analysis of data, using a Convolutional Neural Network (CNN) classification model.

The project aims to assess randomness across multiple dimensions: temporal, spatial and statistical, to provide a more comprehensive evaluation method than any single method alone.

---

## Pipeline

QRNG Data → Transformer Verification → Bias Injection → NIST Testing → Image Conversion → CNN Classification

---
## Repository Structure

    qrng-randomness-evaluation/
    │
    ├── notebooks/
    │   ├── 01_Data_Collection_Verification.ipynb
    │   ├── 02_Initial_Transformer_Analysis.ipynb
    │   ├── 03_Bias_Injection.ipynb
    │   ├── 04_NIST_Testing.ipynb
    │   ├── 05_Image_Conversion.ipynb
    │   └── 06_CNN_Model.ipynb
    │
    ├── .gitignore
    ├── README.md
    └── requirements.txt

> Run notebooks in order 01 → 06.

## Key Components

### 1. Data Collection and Verification
- QRNG data is collected and preprocessed
- Initial statistical checks performed

### 2. Transformer-based Temporal Assessment
- Predicts next byte in sequence
- Achieves ~0.39% accuracy (≈ random baseline 1/256)
- Indicates absence of sequential patterns

### 3. Bias Injection (Markov)
- Artificial dependencies introduced
- Used to validate detection capability

### 4. NIST SP 800-22 Statistical Testing
- Applied on windowed sequences
- Original data passes tests
- Biased data fails → confirms sensitivity

### 5. Image Conversion and Labeling
- Sequences converted into images
- Labels assigned based on NIST results and Source Labels

### 6. CNN-based Spatial Classification
- Classifies images as 'Random' or 'Non-Random'
- Achieves ~50–54% accuracy (baseline)
- Fails to learn → no spatial patterns detected
---

## Dependencies

Install all required packages with:
```bash
pip install -r requirements.txt
```

Key libraries: `numpy`, `tensorflow`, `scipy`, `matplotlib`, `scikit-learn`

---
## Dataset

The full dataset (~131M bytes) is not included in this repository due to size constraints.
Data can be fetched directly using the pipeline in `01_Data_Collection_Verification.ipynb`
via the [LFDR QRNG API](https://lfdr.de/qrng_api/).

---

## Project Info

**Institution**: Indira Gandhi Delhi Technical University for Women, Department of AI & Data Science

**Team**: Ishita Paul · Pallika Dhingra · Saachi Bansal · Tanya Gupta
