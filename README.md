<div align="center">

# 🌞 Physics-Guided Neural Networks for Solar Irradiance Forecasting
### *Outperforming Self-Attention: A Leaner, Smarter Approach*

[![arXiv](https://img.shields.io/badge/arXiv-2604.13455-b31b1b?style=for-the-badge&logo=arxiv)](https://arxiv.org/abs/2604.13455)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Author](https://img.shields.io/badge/Author-Mohammed%20E.%20B.%20Abdullah-blue?style=for-the-badge)](https://github.com/Marco9249)
[![MATLAB](https://img.shields.io/badge/Platform-MATLAB-orange?style=for-the-badge&logo=mathworks)](https://www.mathworks.com/)

</div>

---

## 📄 Abstract

This research challenges the prevailing *"complexity-first"* paradigm in solar irradiance forecasting. We propose a **lightweight Physics-Informed Hybrid CNN-BiLSTM** framework that prioritizes domain knowledge over architectural depth — outperforming expensive Transformer-based models by a significant margin.

Validated on **NASA POWER** multi-year hourly data for Sudan, our approach achieves:

| Metric | Physics-Guided Model | Attention Baseline |
|--------|---------------------|--------------------|
| **RMSE** | **19.53 W/m²** | 30.64 W/m² |
| **Architecture** | CNN-BiLSTM (Physics) | Transformer |

> 🔑 **Key Finding — "The Complexity Paradox":** In high-noise meteorological tasks, explicit physical constraints offer a *more efficient and more accurate* alternative to self-attention mechanisms.

---

## 🏗️ Model Architecture

```
NASA POWER Input (15 Features)
         │
    ┌────▼────┐
    │  1D-CNN │  ← Spatial feature extraction
    └────┬────┘
         │
    ┌────▼─────────┐
    │  BiLSTM       │  ← Long-range temporal dependencies
    └────┬──────────┘
         │
    ┌────▼──────────────────┐
    │  Attention Layer       │  ← Placed AFTER BiLSTM for focused weighting
    └────┬──────────────────┘
         │
    ┌────▼───────────────────────────┐
    │  Physics Gate (SZA + CI)       │  ← Structural night-zero enforcement
    └────┬───────────────────────────┘
         │
    [GHI Prediction — W/m²]
```

### 🔬 Key Design Principles

- **15 Engineered Features** from NASA POWER — including Clear-Sky indices & Solar Zenith Angle (SZA)
- **Sliding Window: 3 Time Steps** — matches physical sampling resolution, prevents temporal over-sampling
- **Attention after BiLSTM** — enables the model to weight the most degradation-relevant temporal context
- **Bayesian Hyperparameter Optimization** — global optimality without grid-search bias

---

## 📂 Project Structure

```
📁 Physics-Guided-CNN-BiLSTM-Solar/
├── 📁 كود التدريب والدالة المساعدة/     # Training scripts (MATLAB)
│   ├── train_hybrid_model.txt           # Main training pipeline
│   └── utils_helper_functions.txt       # Clear-sky & helper functions
├── 📁 بيانات التدريب/                    # NASA POWER Training datasets
│   ├── Hourly_2010_2015.csv
│   ├── Hourly_2015_2020.csv
│   └── Hourly_2020_2025.csv
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
- MATLAB R2022a or later
- Deep Learning Toolbox
- Statistics and Machine Learning Toolbox

### Running the Model
```matlab
% 1. Place your NASA POWER CSV in the working directory
% 2. Open and run the main script
run('كود التدريب والدالة المساعدة/train_hybrid_model.txt')
```

---

## 🌐 Interactive 3D Visualization

Want to explore the model architecture interactively? We built a full **scrollytelling 3D simulation** of this research:

> 🎮 **[Explore the Interactive Visualization →](https://github.com/Marco9249/PI-Hybrid-3D-Viz)**

Built with **Three.js** + **KaTeX** — visualizes the full 5-stage pipeline from feature input to physics gate, with animated data flow and embedded mathematical notation.

---

## 🔗 Related Research by the Same Author

This paper is part of a series of interconnected studies on Physics-Informed Deep Learning for renewable energy and industrial prognostics:

| # | Paper | Repository | arXiv |
|---|-------|------------|-------|
| 1 | **Physics-Guided CNN-BiLSTM Solar Forecast** *(this repo)* | [Here](https://github.com/Marco9249/Physics-Guided-CNN-BiLSTM-Solar) | [2604.13455](https://arxiv.org/abs/2604.13455) |
| 2 | Physics-Informed State Space Models (PISSM) | [PISSM-Solar-Forecasting](https://github.com/Marco9249/PISSM-Solar-Forecasting) | [2604.11807](https://arxiv.org/abs/2604.11807) |
| 3 | Thermodynamic Liquid Manifold Networks (TLMN) | [TLMN-Thermodynamic-Solar-Microgrids](https://github.com/Marco9249/TLMN-Thermodynamic-Solar-Microgrids) | [2604.11909](https://arxiv.org/abs/2604.11909) |
| 4 | Asymmetric-Loss RUL Prediction (Industrial AI) | [Industrial-RUL-Prediction-Architecture](https://github.com/Marco9249/Industrial-RUL-Prediction-Architecture) | [2604.13459](https://arxiv.org/abs/2604.13459) |

---

## 📖 Citation

If you use this code or find this work helpful, please cite:

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

**APA 7th Edition:**
> Abdullah, M. E. B. (2026). *Outperforming Self-Attention Mechanisms in Solar Irradiance Forecasting via Physics-Guided Neural Networks*. arXiv. https://arxiv.org/abs/2604.13455

---

## 👤 Author

**Mohammed Ezzeldin Babiker Abdullah**
*Researcher in Physics-Informed Deep Learning & Renewable Energy Systems*

[![GitHub](https://img.shields.io/badge/GitHub-Marco9249-black?style=flat-square&logo=github)](https://github.com/Marco9249)

---

<div align="center">

© 2026 Mohammed Ezzeldin Babiker Abdullah. All rights reserved.

*This work is officially attributed to the researcher and protected under applicable academic and intellectual property rights.*

</div>
