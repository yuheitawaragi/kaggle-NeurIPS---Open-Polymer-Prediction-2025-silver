# 🥈Kaggle NeurIPS - Open Polymer Prediction 2025 Silver

Kaggle competition silver (36/2240) solution<br>
This repository contains my solution for the Kaggle competition "NeurIPS - Open Polymer Prediction 2025". The goal of this competition is to develop a model that predicts a polymer’s real-world performance metrics—density, thermal conductivity (Tc), glass transition temperature (Tg), radius of gyration (Rg), and fractional free volume (FFV)—directly from its chemical structure (SMILES).

## Competition Overview

This competition challenges participants to predict fundamental polymer properties directly from their chemical structures. By building accurate models, we can accelerate materials discovery, enabling the development of sustainable and biocompatible polymers that benefit society and the environment.

## Competition Goal

This competition focuses on building models that can forecast key polymer properties—density, thermal conductivity (Tc), glass transition temperature (Tg), radius of gyration (Rg), and fractional free volume (FFV)—directly from their chemical structures (SMILES).

## Evaluation

The competition uses a weighted Mean Absolute Error (wMAE) across the five polymer properties as the evaluation metric. A reweighting factor is applied to ensure fairness:
* Scale normalization: Adjusts for differences in numerical ranges.
* Inverse square-root scaling: Gives more weight to properties with fewer samples.
* Weight normalization: Ensures the total weights sum to one.

## Submission

The submission file must be a CSV containing predictions for all five polymer properties. For each id in the test set, you should output one row with the predicted values. The file must include a header and follow this format:

```csv
   id,Tg,FFV,Tc,Density,Rg
   2112371,0.0,0.0,0.0,0.0,0.0
   2021324,0.0,0.0,0.0,0.0,0.0
   343242,0.0,0.0,0.0,0.0,0.0
```
## Data

Data is available on [link](https://www.kaggle.com/competitions/neurips-open-polymer-prediction-2025/data).

## Model And External data

ChemBERTa-MLM-dataset: [link](https://huggingface.co/DeepChem/ChemBERTa-77M-MLM/tree/main)<br>
IBM-TED: [link](https://huggingface.co/ibm-research/materials.selfies-ted)<br>
T-SMILES: [link](https://github.com/juanniwu/t-SMILES.git), [link](https://github.com/BiomedSciAI/r-BRICS/blob/main/rBRICS_public.py)   (rBRICS)<br>
JCIM_sup_bigsmiles.csv: [link](https://springernature.figshare.com/articles/dataset/dataset_with_glass_transition_temperature/24219958?file=42507037)<br>
data_tg3.xlsx: [link](https://www.sciencedirect.com/science/article/pii/S2590159123000377#ec0005)<br>
data_dnst1.xlsx: [link](https://github.com/Duke-MatSci/ChemProps)<br>
Tc_SMILES.csv: [link](https://www.kaggle.com/datasets/minatoyukinaxlisa/tc-smiles)<br>
Tg_SMILES_class_pid_polyinfo_median.csv: [link](https://www.kaggle.com/datasets/fridaycode/tg-smiles-pid-polyinfo-class)

## Citation

Gang Liu, Jiaxin Xu, Eric Inae, Yihan Zhu, Ying Li, Tengfei Luo, Meng Jiang, Yao Yan, Walter Reade, Sohier Dane, Addison Howard, and María Cruz. NeurIPS - Open Polymer Prediction 2025. https://kaggle.com/competitions/neurips-open-polymer-prediction-2025, 2025. Kaggle.


