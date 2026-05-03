# QRNG Randomness Evaluation Framework

## Overview
This project proposes a hybrid framework to evaluate the randomness of numerical data, particularly focusing on quantum-generated random numbers (QRNG).
The framework combines Statistical Testing (NIST SP 800-22) with Spatial Analysis of data, using a Convolutional Neural Network (CNN) classification model.
The project aims to assess randomness across multiple dimensions.

---

## Pipeline

QRNG Data → Bias Injection → NIST Testing → Image Conversion → CNN Classification

---

## Key Components

### 1. Data Collection
- QRNG data is collected and preprocessed
- Initial statistical checks performed

### 2. Transformer-based Assessment
- Predicts next byte in sequence
- Achieves ~0.39% accuracy (≈ random baseline 1/256)
- Indicates absence of sequential patterns

### 3. Bias Injection (Markov)
- Artificial dependencies introduced
- Used to validate detection capability

### 4. NIST Statistical Testing
- Applied on windowed sequences
- Original data passes tests
- Biased data fails → confirms sensitivity

### 5. Image Conversion
- Sequences converted into images
- Labels assigned based on NIST results and Source Labels

### 6. CNN-based Spatial Analysis
- Classifies images as 'Random' or 'Non-Random'
- Achieves ~50–54% accuracy (baseline)
- Fails to learn → no spatial patterns detected
---
