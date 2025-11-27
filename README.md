# Species-Importance Ranking Similarity Using Hybrid ML Models Across Ecosystems
Validation-based framework for ecologists — not a new keystone prediction tool.

This repository contains ecosystem datasets and scripts used to evaluate how closely machine-learning derived species-importance rankings reproduce expert Ecopath keystone rankings.  
The objective is not to output new influential species, but to demonstrate whether this approach is reliable enough for ecological use when expert classifications are missing or incomplete.

<p align="center">
  <img src="assets/overview.png" width="650">
</p>

---

##  Project Summary

Expert keystone ranking traditionally requires full Ecopath parameterization, long-term diet surveys, and ecological knowledge.  
Our approach tests whether ML-based ranking similarity can match expert ordering using minimal data — biomass + diet + network metrics.

If similarity remains consistently high across ecosystems:

✔ ecologists may safely adopt the method in future  
✔ full EwE reconstruction is not always necessary  
✔ model can be extended later for keystone prediction

This study is *validation-focused* — similarity is the output.

---

##  Ecosystem Sets Included

### 🔹 Training Ecosystems (used for learning)
| ID | Ecosystem | Region |
|---|---|---|
| **E1** | Lake Kinneret | Israel |
| **E2** | Alto Golfo | Northern Gulf of California |
| **E3** | Celtic Sea | Northeast Atlantic |

### 🔹 Test Ecosystems (used only for similarity validation)
| ID | Ecosystem | Region |
|---|---|---|
| **E4** | *Reserved for additional test set* | — |
| **E5** | Cap de Creus MPA | Western Mediterranean |
| **E6** | Bay of Biscay Shelf System | Northeast Atlantic |

These are used to calculate how close ML ranking orders are to expert ground truth.

---

##  Ranking Similarity Workflow

Biomass + Diet + Network → Feature Engineering → { RF | LP | GraphSAGE } → Ensemble → Ranking Similarity


### Evaluation Metrics
- **Top-K Overlap** — shared top species count
- **Jaccard Index** — Top-K intersection vs union
- **Spearman ρ** — rank-ordering monotonic similarity
- **Extinction-AUC** — system robustness under node removal

Output = **Similarity percentage**, not a new species list.

---

##  Repository Structure

data/
├── training/
│   ├── E1_Kinneret.csv
│   ├── E2_AltoGolfo.csv
│   └── E3_CelticSea.csv
├── testing/
│   ├── E4.csv
│   ├── E5_CapDeCreus.csv
│   └── E6_BayOfBiscay.csv

code/
├── features_engineering.ipynb
├── train_RF_LP_GraphSAGE.py
├── ensemble_ranking_similarity.py
├── extinction_curve_analysis.py
└── utils/
    ├── metrics.py
    ├── loaders.py
    ├── graph_ops.py
    ├── shap_importance.py
    └── plot_utils.py

results/
├── similarity_scores/
├── extinction_AUC_plots/
└── feature_importance/

assets/
└── overview.png

README.md






##  How to Run

### 1. Install requirements
```bash
pip install -r requirements.txt
python code/train_RF_LP_GraphSAGE.py
python code/ensemble_ranking_similarity.py
python code/extinction_curve_analysis.py
/results/similarity_scores/
/results/extinction_AUC_plots/


##  Interpretation for Ecologists
| Similarity Score | Interpretation                                                              |
| ---------------- | --------------------------------------------------------------------------- |
| >0.75            | Model aligns strongly with expert keystone rankings → reliable for adoption |
| 0.50–0.75        | Useful with partial expert oversight                                        |
| <0.50            | Ecopath re-evaluation or richer input recommended                           |

This study does not produce new keystone species.
It demonstrates method reliability, enabling future ecological adoption.

## Citation

Ghosh, M. (2025). Species Importance Ranking Similarity Using Hybrid ML.
GitHub Repository & Manuscript Release.

