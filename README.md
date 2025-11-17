# CSIRO-Image2Biomass-Prediction

## Project Overview

This project predicts pasture biomass using machine learning models trained on field images, NDVI values, pasture height, species information, and ground-truth biomass measurements. The goal is to estimate five biomass components and support data-driven grazing decisions.

**Final Performance:** Weighted R² = 0.59

## Dataset

The dataset comprises multi-modal pasture measurements including:

- RGB pasture images
- Sampling date, state, and species
- NDVI (GreenSeeker)
- Pasture height
- Five biomass targets:
  - Dry_Green_g
  - Dry_Dead_g
  - Dry_Clover_g
  - GDM_g
  - Dry_Total_g

Each image has five target values, and evaluation uses a weighted R² score.

## Methodology

### 1. Preprocessing
- Image resizing and normalization
- Encoding species/state
- Scaling NDVI and height
- Outlier removal (IQR)

### 2. Feature Engineering
- NDVI × height interaction
- Seasonal features from sampling date
- CNN-based image embeddings

### 3. Model
- Fusion model combining image features + tabular data
- Outputs all five biomass components
- Final performance: Weighted R² = 0.59

## Results

- NDVI and pasture height were the strongest predictors
- Species composition influenced biomass variation
- Fusion model performed better than tabular baselines
- Predictions were consistent across most regions and seasons

## How to Run

1. Install requirements
2. Open and run the Jupyter notebook
3. Model outputs predictions and generates `submission.csv`

## Future Work

- Add multispectral/UAV imagery
- Improve species-specific accuracy
- Build a simple prediction dashboard
