## 🥈Kaggle NeurIPS - Open Polymer Prediction 2025 Silver (My Solution)

# Overview and goal

This repository contains my solution for the Kaggle competition "NeurIPS - Open Polymer Prediction 2025".
The task is to build a model that predicts key polymer properties directly from their chemical structure (SMILES).
The target properties are:
* Density
* Thermal conductivity (Tc)
* Glass transition temperature (Tg)
* Radius of gyration (Rg)
* Fractional free volume (FFV)

# Approach
In this project, various feature engineering techniques are applied to polymer SMILES, and LGBM model is used for training and inference to predict different polymer properties.

### 1. Preprocessing and data preparation

* Clean and validate SMILES strings by removing invalid patterns.
* Use RDKit to canonicalize SMILES and ensure chemical validity.
* Supplement the official competition training data with additional public datasets for properties such as Tc, Tg, Density, and FFV.
* Resolve duplicates by prioritizing competition-provided values.
* Add new unique SMILES entries from external sources to increase training coverage.

These steps help improve data quality and expand the dataset for more robust model training.

