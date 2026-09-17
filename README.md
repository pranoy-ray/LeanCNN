# LeanCNN

**Lean CNNs for Mapping Electron Charge Density Fields to Material Properties**

This repository contains the code accompanying the paper *"Lean CNNs for Mapping Electron Charge Density Fields to Material Properties"* by Pranoy Ray, Kamal Choudhary, and Surya R. Kalidindi, published in *Integrating Materials and Manufacturing Innovation* (2025).

📄 **Paper:** [Springer Nature Link](https://doi.org/10.1007/s40192-024-00389-9) · [arXiv:2505.09826](https://arxiv.org/abs/2505.09826)

---

## Overview

LeanCNN is a lightweight convolutional neural network framework for learning surrogate structure–property (S–P) linkages from Density Functional Theory (DFT) electron charge density (ECD) fields. The framework predicts effective material properties directly from featurized ECD fields, using a drastically reduced number of trainable parameters (**< 81K**) compared to benchmark CNN architectures in the current literature.

The key idea is to introduce a **feature-engineering pre-processing step** before the CNN: rather than feeding raw ECD fields into a large network, the fields are first transformed via their **2-point spatial correlations**. This physics-aware representation captures the salient spatial statistics of the charge density, allowing a much smaller ("lean") network to learn robust structure–property relationships.

## Highlights

- **Lean architecture** — fewer than 81K fittable parameters, substantially smaller than comparable models in the literature.
- **Feature-engineered inputs** — 2-point spatial correlations of the ECD fields serve as the sole model input.
- **Robust S–P linkages** — accurate prediction of effective material properties from featurized ECD fields.
- **Low computational cost** — a fast surrogate for expensive DFT-based property evaluation.

## Dataset

The framework is evaluated on a dataset of **crystalline cubic systems** comprising:

- **1,410** molecular/crystal structures
- **62** distinct elemental species
- **3** space groups

## Method

1. **Input** — DFT-computed electron charge density (ECD) fields for each structure.
2. **Feature engineering** — compute 2-point spatial correlations of the ECD fields to produce statistically rich, low-dimensional-friendly representations.
3. **Lean CNN** — a compact convolutional network maps the featurized fields to effective material properties.
4. **Output** — predicted effective properties, learned as surrogate structure–property linkages.

## Repository Structure

> Adjust the paths below to match the actual layout of your repository.

```
LeanCNN/
├── data/           # ECD field data and/or processed 2-point correlations
├── src/            # Model definitions, training, and evaluation code
├── notebooks/      # Example workflows and analysis
├── results/        # Trained models, figures, and outputs
└── README.md
```

## Installation

```bash
git clone https://github.com/pranoy-ray/LeanCNN.git
cd LeanCNN

# (recommended) create a virtual environment
python -m venv venv
source venv/bin/activate      # on Windows: venv\Scripts\activate

# install dependencies
pip install -r requirements.txt
```

## Usage

> Update these commands to reflect the actual entry points in the repository.

```bash
# 1. Compute 2-point spatial correlations from ECD fields
python src/featurize.py --input data/ecd_fields --output data/features

# 2. Train the lean CNN
python src/train.py --config configs/default.yaml

# 3. Evaluate / predict
python src/evaluate.py --model results/model.pt --data data/features
```

## Citation

If you use this code or find this work useful, please cite:

```bibtex
@article{ray2025leancnn,
  title   = {Lean CNNs for Mapping Electron Charge Density Fields to Material Properties},
  author  = {Ray, Pranoy and Choudhary, Kamal and Kalidindi, Surya R.},
  journal = {Integrating Materials and Manufacturing Innovation},
  volume  = {14},
  number  = {1},
  pages   = {1--13},
  year    = {2025},
  doi     = {10.1007/s40192-024-00389-9}
}
```

## Authors

- **Pranoy Ray** — Georgia Institute of Technology
- **Kamal Choudhary** — Johns Hopkins University / NIST
- **Surya R. Kalidindi** — Georgia Institute of Technology

## License

Add a license file (e.g., MIT) and reference it here.
