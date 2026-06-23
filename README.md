# F-ViT-Cocoa

**An Engineered Vision Transformer with a Fabricated Reconfigurable Focal-Loss Layer for Early Cocoa Swollen Shoot Virus (CSSV) Detection in Ghanaian Smallholder Farms**

## Overview
This repository contains the code, configuration, and reproducibility artefacts for the F-ViT research project. F-ViT is a novel Vision Transformer variant that fabricates a custom **Reconfigurable Focal-Loss (RFL) layer** — with γ implemented as a learnable backpropagation-updated parameter — to address extreme class imbalance in field-collected CSSV imagery from Ghana.

## Model Engineering Contribution
- **Operation:** Fabricate [F]
- **Engineered model:** F-ViT (Fabricated Vision Transformer)
- **Base architecture:** ViT-Base/16 (ImageNet-21k pre-trained)
- **Key modification:** Learnable γ parameter (initialised at 2.0, constrained to [0.5, 5.0] via sigmoid) replacing the fixed focal loss modulating factor

## Repository Structure
F-ViT-Cocoa/

├── README.md

├── requirements.txt        # Pinned library versions

├── notebooks/

│   ├── 01_baseline_vit.ipynb       # Locked Standard ViT baseline

│   └── 02_fvit_rfl_training.ipynb  # F-ViT with RFL layer

├── src/

│   ├── rfl_layer.py        # Reconfigurable Focal-Loss implementation

│   └── fvit_model.py       # F-ViT model definition

└── data/

└── README.md           # Data access instructions
## Baselines
| Model | Type |
|---|---|
| Standard ViT-Base/16 | Unengineered control |
| ResNet-50 | CNN classification benchmark |
| XGBoost | Traditional ML benchmark |

## Reproducibility
- **Seed:** 42 (Python, NumPy, PyTorch, CUDA)
- **Split:** Stratified 70/15/15 + 5-fold cross-validation
- **Significance test:** Wilcoxon Signed-Rank (p < 0.05) + rank-biserial correlation

## Ethics
This study was approved by the KNUST Committee on Human Research, Publications and Ethics (CHRPE). All field data was collected with written informed consent from participating farmers.

## Target Journal
Computers and Electronics in Agriculture (Elsevier, Q1)

## Status
🔬 In progress — data collection phase
