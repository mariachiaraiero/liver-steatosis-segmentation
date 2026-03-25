# Liver Steatosis Segmentation

This repository contains a collection of Jupyter Notebooks for training a PyTorch-based 2D U-Net model aimed at the semantic segmentation of liver steatosis in histological images. 

Given the standard challenges in histopathology image analysis—such as color variations across different staining protocols—this project robustly evaluates the impact of **color normalization algorithms** combined with Data Augmentation (DA) and K-Fold cross-validation.

## Overview of Notebooks

The repository explores different data preprocessing and normalization strategies:

- **`model_base.ipynb`**: Baseline U-Net model implementation without data augmentation or specific color normalization.
- **`model_baseline_DA_kfolD.ipynb` / `nuova_baseline_DA.ipynb`**: Baseline models incorporating standard Data Augmentation techniques.
- **`model_MACENKO_DA_kfold.ipynb`**: U-Net training pipeline using **Macenko** color normalization to standardize H&E stained images.
- **`model_REINHARD_DA_kfold.ipynb`**: U-Net training pipeline relying on **Reinhard** color normalization.
- **`model_BADE_kfold.ipynb`**: Experiments using BADE normalization.
- **`model_green_kfold.ipynb`**: Implementation possibly focusing on the green channel or a specific color representation for improved contrast.
- **`post_HED.ipynb`**: Post-processing and analysis utilizing Haematoxylin & Eosin (H&E) color deconvolution spaces.
- **`generate_balanced_kfold.ipynb`**: Utility script responsible for generating a properly balanced dataset split for K-Fold cross-validation.

## Model Architecture and Training

* **Architecture**: The core model is a standard U-Net with a `DoubleConv` encoder-decoder structure.
* **Loss Function**: `DiceBCELoss` (a combination of Dice Loss and Binary Cross Entropy) to handle unbalanced segmentation masks.
* **Metrics**: Standard and strict Dice Similarity Coefficient (DSC).
* **Framework**: PyTorch.

## Setup & Requirements

1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/mariachiaraiero/liver-steatosis-segmentation.git
   ```
2. Make sure you have the following primary dependencies installed (or setup a virtual environment):
   - PyTorch
   - OpenCV (`cv2`)
   - NumPy, Matplotlib, PIL
   - tqdm
   
*(Note: Most notebooks are designed to run in environments like Google Colab, leveraging Google Drive for dataset mounting and model checkpointing).*
