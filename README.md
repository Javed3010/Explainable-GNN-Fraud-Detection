# Explainable Graph Neural Networks for Financial Fraud Detection

A research implementation investigating graph-based detection of illicit financial transactions and interpretable fraud-risk propagation using the **Elliptic Bitcoin transaction dataset**. Developed as a group project for **CSE 543: Information Assurance & Security, Arizona State University (Spring 2026)**.

## Overview
Traditional transaction classifiers overlook relationships among transactions. This repository contains experiments with graph neural networks and classical machine-learning baselines, plus explanations of graph predictions using GNNExplainer and SHAP.

## Included work
- **`Ellptic_TAGCN.ipynb`** — TAGCN training/evaluation, graph visualizations, GNNExplainer and SHAP experiments.
- **`Baseline-GNNs.ipynb`** — GCN, GraphSAGE, GAT and other graph-model baselines.
- **`Baseline-ML.ipynb`** — Logistic Regression, SVM and KNN baselines.
- **`AblationStudy.ipynb`** — TAGCN K-hop ablation experiments.
- **`plot/`** — model comparison and precision–recall plotting notebooks.
- **`data/elliptic_bitcoin_dataset/`** — dataset CSVs included in the supplied archive; verify the dataset's license and redistribution terms before publishing.
- **`docs/`** — project overview, reproducibility notes, and publishing checklist.

## Dataset
The Elliptic dataset represents Bitcoin transactions and transaction-to-transaction connections. The source notebooks load:

```text
data/elliptic_bitcoin_dataset/elliptic_txs_classes.csv
data/elliptic_bitcoin_dataset/elliptic_txs_edgelist.csv
data/elliptic_bitcoin_dataset/elliptic_txs_features.csv
```

Classes are mapped in the notebooks as `1 = illicit`, `2 = licit`; unknown labels are excluded in some experiments. Consult the original Elliptic dataset source for licensing and citation.

## Quick start

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

Open the notebook of interest and run cells in order from the repository root. **Important:** the original notebooks contain Colab shell-install cells, hard-coded paths, and potentially environment-specific assumptions; adapt those cells before running locally. PyTorch Geometric installation may require platform-specific wheels; see its official installation guide. These notebooks have **not been rerun or validated** in this packaging process.

## Research approach
1. Load and preprocess the Elliptic graph and class labels.
2. Train classical ML and GNN baseline models.
3. Train a topology-adaptive graph convolution (TAGCN) model.
4. Compare accuracy, precision, recall, F1, and MCC where recorded.
5. Investigate feature and graph-edge contributions using SHAP and GNNExplainer.
6. Examine sensitivity to neighborhood-hop configuration through ablation studies.

## Results and interpretation
The final course report documents model comparisons and local explanations. Reported values are **research experiment outputs**, not independently reproduced production benchmarks. Consult the notebooks and report for the exact split, model configuration, and metrics; do not treat notebook output as a guarantee of performance on new datasets.

## Limitations
- Fraud labels are imbalanced; unknown labels and graph connectivity require careful treatment.
- Explanation importance is not proof of causation or regulatory compliance.
- Temporal leakage and train/test graph construction can affect apparent generalization.
- Not a deployed or production-ready fraud monitoring service.

## Team and attribution
Group 2, CSE 543, Arizona State University, Spring 2026. The course report lists Mohamed Javed Khan among the group members. This repository reflects a **team project**; retain attribution to all contributors when publishing. Review the report for full author names and research references.

## Documentation
See [`docs/PROJECT_OVERVIEW.md`](docs/PROJECT_OVERVIEW.md), [`docs/REPRODUCIBILITY.md`](docs/REPRODUCIBILITY.md), and [`docs/PUBLISHING_CHECKLIST.md`](docs/PUBLISHING_CHECKLIST.md).

## License
No software license was supplied with the original project. **Do not assume this repository is open-source licensed.** Confirm all contributors' permission and select a license before public release. Dataset rights are separate from code rights.
