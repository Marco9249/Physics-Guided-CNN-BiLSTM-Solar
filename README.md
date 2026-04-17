<div align="center">

<img src="https://img.shields.io/badge/%E2%98%80%EF%B8%8F-Solar%20AI-FFD700?style=for-the-badge&labelColor=1a1a2e" alt="Solar AI"/>

# Physics-Guided Neural Networks for Solar Irradiance Forecasting

### ✨ *Outperforming Self-Attention: A Leaner, Smarter Approach* ✨

<br/>

[![arXiv](https://img.shields.io/badge/arXiv-2604.13455-b31b1b?style=for-the-badge&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2604.13455)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![MATLAB](https://img.shields.io/badge/MATLAB-R2022a+-0076A8?style=for-the-badge&logo=mathworks&logoColor=white)](https://www.mathworks.com/)
[![NASA POWER](https://img.shields.io/badge/Data-NASA%20POWER-005288?style=for-the-badge&logo=nasa&logoColor=white)](https://power.larc.nasa.gov/)

<br/>

<img src="https://img.shields.io/badge/Author-Mohammed%20Ezzeldin%20Babiker%20Abdullah-4A90D9?style=flat-square&logo=google-scholar&logoColor=white" alt="Author"/>

---

*"In high-noise meteorological tasks, explicit physical constraints offer a more efficient and more accurate alternative to self-attention mechanisms."*

</div>

---

## 🎯 The Complexity Paradox

> **Key Discovery:** While the AI community races toward ever-larger Transformer architectures, we demonstrate that a lightweight **Physics-Informed CNN-BiLSTM** with only **15 engineered features** from NASA POWER can **outperform** complex attention-based models by **36%** in RMSE.

| Metric | 🧠 Physics-Guided (Ours) | 🤖 Attention Baseline |
|:------:|:------------------------:|:---------------------:|
| **RMSE** | **19.53 W/m²** ✅ | 30.64 W/m² |
| **Approach** | Domain Knowledge First | Complexity First |
| **Architecture** | CNN → BiLSTM → Attention | Full Transformer |

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────┐
│                                                     │
│   ☀️  NASA POWER Input (15 Physics Features)        │
│       GHI, DNI, DHI, SZA, KT, Tamb, RH, ...       │
│                        │                            │
│                  ┌─────▼─────┐                      │
│                  │  1D-CNN   │  Spatial extraction   │
│                  └─────┬─────┘                      │
│                        │                            │
│               ┌────────▼────────┐                   │
│               │    BiLSTM       │  Temporal deps.   │
│               └────────┬────────┘                   │
│                        │                            │
│          ┌─────────────▼─────────────┐              │
│          │  🎯 Attention Layer       │  Placed      │
│          │  (after BiLSTM)           │  AFTER BiLSTM│
│          └─────────────┬─────────────┘              │
│                        │                            │
│             ┌──────────▼──────────┐                 │
│             │  Physics Gate       │ Night=0         │
│             │  (SZA + Clear-Sky)  │ enforcement     │
│             └──────────┬──────────┘                 │
│                        │                            │
│              📊 GHI Prediction (W/m²)               │
│                                                     │
└─────────────────────────────────────────────────────┘
```

### 🔬 Design Principles

| Principle | Implementation |
|:---------:|:--------------:|
| 🌡️ **15 Physics Features** | Clear-Sky, SZA, KT, DNI, DHI, Tamb, RH, cyclical time |
| 🪟 **Sliding Window** | 3 time-step stride — prevents temporal over-sampling |
| 🎯 **Attention Placement** | After BiLSTM — focused temporal weighting |
| 🔧 **Hyperparameter Tuning** | Bayesian Optimization (30 iterations) |

---

## 📂 Repository Structure

```
📦 Physics-Guided-CNN-BiLSTM-Solar/
│
├── 📁 training_code/
│   ├── 🧠 train_hybrid_model.txt         # Main training pipeline (MATLAB)
│   └── 🔧 utils_helper_functions.txt     # Clear-sky calculation utilities
│
├── 📁 training_data/
│   ├── 📊 Hourly_2010_2015.csv           # NASA POWER hourly data
│   ├── 📊 Hourly_2015_2020.csv
│   └── 📊 Hourly_2020_2025.csv
│
├── 📄 Physics_Guided_CNN_BiLSTM_Paper.pdf # Published paper
├── 📄 Physics_Guided_CNN_BiLSTM_Paper.docx
└── 📖 README.md
```

---

## 🚀 Quick Start

```matlab
% 1. Open MATLAB R2022a+
% 2. Navigate to the training_code/ directory
% 3. Run the main training script:
run('training_code/train_hybrid_model.txt')

% The script will:
%   → Load NASA POWER data automatically
%   → Engineer 15 physics-informed features
%   → Run Bayesian Optimization (30 iterations)
%   → Train final CNN-BiLSTM model
%   → Output RMSE, MAE, R² metrics
```

---

## 🎮 Interactive 3D Visualization

> Want to **explore the model architecture interactively**? We built a full **scrollytelling 3D simulation** powered by Three.js + KaTeX:

<div align="center">

[![3D Viz](https://img.shields.io/badge/🎮_Explore_Interactive_3D_Visualization-4A90D9?style=for-the-badge)](https://github.com/Marco9249/PI-Hybrid-3D-Viz)

*Animated data flow • Mathematical notation • Layer-by-layer walkthrough*

</div>

---

## 📚 Related Research Papers

<div align="center">

| # | Paper | Repository | arXiv |
|:-:|:------|:----------:|:-----:|
| **1** | **Physics-Guided CNN-BiLSTM** *(this repo)* 🌟 | [![Repo](https://img.shields.io/badge/-Repo-181717?style=flat-square&logo=github)](https://github.com/Marco9249/Physics-Guided-CNN-BiLSTM-Solar) | [![arXiv](https://img.shields.io/badge/-2604.13455-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.13455) |
| 2 | Physics-Informed State Space Model (PISSM) | [![Repo](https://img.shields.io/badge/-Repo-181717?style=flat-square&logo=github)](https://github.com/Marco9249/PISSM-Solar-Forecasting) | [![arXiv](https://img.shields.io/badge/-2604.11807-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.11807) |
| 3 | Thermodynamic Liquid Manifold Networks | [![Repo](https://img.shields.io/badge/-Repo-181717?style=flat-square&logo=github)](https://github.com/Marco9249/TLMN-Thermodynamic-Solar-Microgrids) | [![arXiv](https://img.shields.io/badge/-2604.11909-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.11909) |
| 4 | Asymmetric-Loss Industrial RUL Prediction | [![Repo](https://img.shields.io/badge/-Repo-181717?style=flat-square&logo=github)](https://github.com/Marco9249/Industrial-RUL-Prediction-Architecture) | [![arXiv](https://img.shields.io/badge/-2604.13459-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.13459) |
| 🎮 | Interactive 3D Architecture Visualization | [![Repo](https://img.shields.io/badge/-Repo-181717?style=flat-square&logo=github)](https://github.com/Marco9249/PI-Hybrid-3D-Viz) | — |

</div>

---

## 📖 Citation

```bibtex
@misc{abdullah2026physicsguidedcnn,
  title   = {Outperforming Self-Attention Mechanisms in Solar Irradiance
             Forecasting via Physics-Guided Neural Networks},
  author  = {Mohammed Ezzeldin Babiker Abdullah},
  year    = {2026},
  eprint  = {2604.13455},
  archivePrefix = {arXiv},
  primaryClass  = {cs.LG},
  url     = {https://arxiv.org/abs/2604.13455}
}
```

> **APA 7th Edition:**
> Abdullah, M. E. B. (2026). *Outperforming Self-Attention Mechanisms in Solar Irradiance Forecasting via Physics-Guided Neural Networks*. arXiv. https://arxiv.org/abs/2604.13455

---

<div align="center">

### 👤 Author

**Mohammed Ezzeldin Babiker Abdullah**

[![GitHub](https://img.shields.io/badge/GitHub-Marco9249-181717?style=for-the-badge&logo=github)](https://github.com/Marco9249)

---

© 2026 Mohammed Ezzeldin Babiker Abdullah — All rights reserved.

</div>
