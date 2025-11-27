# Species Ranking Similarity Evaluation Across Marine & Freshwater Ecosystems

This repository contains the dataset splits used to train, validate and test a hybrid framework for evaluating similarity between **machine-derived species-importance rankings** and **expert ground-truth ecological rankings**.

The study does **not generate new keystone species lists** — instead, it measures how closely ML-derived rankings reproduce existing expert ranking order, allowing ecologists to judge whether this approach is reliable for future adoption.

---

## 🌍 Study Ecosystems

The models were trained and evaluated using six Ecopath-based trophic networks.

### 🔹 Training Ecosystems (Used for Model Learning)
| ID | Ecosystem | Region |
|---|---|---|
| **E1** | Lake Kinneret | Israel |
| **E2** | Alto Golfo | Northern Gulf of California |
| **E3** | Celtic Sea | Northeast Atlantic |

These ecosystems provide the labeled reference needed to train Random Forest, Label Propagation, and GraphSAGE models.

---

### 🔹 Test Ecosystems (Used for Generalization Evaluation)
| ID | Ecosystem | Region |
|---|---|---|
| **E4** | *To be inserted / placeholder* | — |
| **E5** | Cap de Creus MPA | Western Mediterranean |
| **E6** | Bay of Biscay Shelf System | Northeast Atlantic |

These are used to measure **ranking similarity** between model output and expert-defined keystone rankings.

> A high similarity score indicates that the ML-based method can be trusted to approximate expert knowledge under minimal parameterization.

---


---

## 🎯 Purpose of This Repository

- To store structural + ecological feature matrices for **E1–E6 ecosystems**
- To provide benchmark datasets for **ranking similarity analysis**
- To enable ecologists to **reproduce our comparison-based methodology**

The goal of this study is *validation* — once similarity is proven, ecologists may confidently apply this approach in data-limited environments without requiring complete EwE parameterization.

---

## 📜 Citation

If using this dataset, please cite:



## 📁 Repository Structure

