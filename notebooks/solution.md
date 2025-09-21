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

### 2. Feature Engineering – Polymer Backbone & Sidechain

This project extracts structural features from polymer SMILES by separating backbone and sidechains.
It computes descriptors such as:
* Backbone: length, aromatic fraction, rotatable bonds, molecular weight, TPSA, LogP, heteroatom fraction, ring fraction, fraction of rotatable bonds
* Sidechains: count, mean length, hydrogen bond donors/acceptors, density, attachment density, mass/TPSA/LogP mean, branching degree, maximum length, spacing standard deviation

These features capture polymer architecture and physicochemical properties, which are then used as input for model training.

### 3. 3D Feature Engineering

This project generates 3D molecular conformations from polymer SMILES (using ETKDG + UFF optimization) and computes 3D shape descriptors.
Extracted features include:
* Surface area (TPSA, LabuteASA)
* Principal moments of inertia (PMI1, PMI2, PMI3, PMI ratios)
* Inertial shape factor
* Shape descriptors (spherocity, asphericity, eccentricity, radius of gyration)

These features capture the 3D geometry and shape anisotropy of polymers, which are important for predicting physical properties.

### 4. ChemBERTa-based Molecular Embedding Features

* SMILES strings are encoded using ChemBERTa, a pretrained transformer model for molecules.
* For each molecule, the CLS token embedding is extracted as a fixed-length vector.
* Embeddings are scaled and then clustered using:
  *
