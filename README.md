# Self-Supervised Representation of Liquid Loading in Piezoelectric Micromachined Ultrasonic Transducers (PMUTs)

This repository contains the dataset, trained models, and implementation used in the paper:

**"Self-Supervised Representation of Liquid Loading in Piezoelectric Micromachined Ultrasonic Transducers"**

Submitted to *IEEE Journal of Microelectromechanical Systems (JMEMS) Letters*.

The work demonstrates a self-supervised learning framework for modelling the full frequency-domain response of liquid-loaded PMUT sensors and extracting physics-aware representations from the spectral measurements.

---

# Repository Contents

## Dataset

dataset.csv

Frequency-domain measurement dataset obtained from dual-mode PMUT devices operating in Tx-Rx configuration.

The dataset contains spectral responses measured under multiple liquid environments, including:

- Air
- Deionized water
- Isopropyl alcohol
- Acetone
- Glucose concentration ladder

Each sample corresponds to a frequency sweep capturing the electromechanical response of the PMUT under fluid loading.

---

## Training and Analysis Notebook

upr_final.ipynb

Main notebook implementing the full machine learning pipeline:

- Data preprocessing
- Spectral augmentations
- Self-supervised contrastive learning (SimCLR-style training)
- Encoder training
- Representation extraction
- Downstream classification tasks

The notebook reproduces the training pipeline used in the paper.

---

## Trained Models

best_simclr_model.keras

Full SimCLR contrastive learning model used during representation learning.

best_upr_encoder.weights.h5

Weights for the trained encoder network used to extract compact latent representations of PMUT spectral responses.

These pretrained weights allow direct inference without retraining the model.

---

# Method Overview

The proposed framework treats the PMUT frequency response as a high-dimensional physical object and learns invariant representations using contrastive self-supervised learning.

The pipeline consists of:

1. Frequency-domain spectral measurements
2. Physically motivated spectral augmentations
3. Contrastive representation learning
4. Encoder training
5. Latent feature extraction
6. Downstream classification

The learned representation captures physical effects such as:

- Added mass loading
- Viscous damping
- Resonance shifts

---

# Requirements

The implementation was developed using Python.

Recommended environment:

Python ≥ 3.9

Typical dependencies include:

numpy  
pandas  
tensorflow / keras  
scikit-learn  
matplotlib

Install dependencies using:

pip install numpy pandas tensorflow scikit-learn matplotlib

---

# Using the Pretrained Encoder

The pretrained encoder weights can be loaded to extract latent representations from new PMUT frequency spectra.

Example workflow:

1. Load trained encoder weights
2. Input frequency sweep data
3. Extract latent representation
4. Perform classification or regression tasks

---

# Reproducibility

This repository provides:

- Raw dataset
- Training notebook
- Pretrained models

allowing reproduction of the representation learning framework presented in the paper.

---

# Citation

If you use this dataset or code, please cite the associated paper:

M. Zaid, M. Zayan, A. Seshia  
"Self-Supervised Representation of Liquid Loading in Piezoelectric Micromachined Ultrasonic Transducers,"  
submitted to IEEE JMEMS Letters, 2026.

---

# Contact

For questions regarding the dataset or implementation, please contact the author.
