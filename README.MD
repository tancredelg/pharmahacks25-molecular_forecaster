# kiNNet: Kinase Selectivity Prediction

**2nd Place Winner & Best Pitch at PharmaHacks 2025 (Molecular Forecaster Challenge)**

A biochemistry-informed neural network designed to predict the selectivity profiles of small molecule inhibitors against the human kinome. This tool aids in drug discovery by prioritizing compounds that bind specifically to target kinases while minimizing off-target effects.

## 🧪 The Problem

Kinases are critical drug targets, but achieving selectivity is difficult. Inhibitors often bind to multiple kinases (off-target effects), leading to toxicity.
**Goal:** Predict the binding affinity ($K_d$) and selectivity score of small molecules across 442 kinases using only their chemical structure and the kinase protein sequence.

## 🚀 Our Approach

We developed a two-stage pipeline combining feature engineering, dimensionality reduction, and deep learning.

### 1. Feature Engineering

-   **Inhibitors (Small Molecules):** Extracted 2048-bit Morgan Fingerprints (ECFP4) and physicochemical descriptors (LogP, Molecular Weight, TPSA, etc.) using **RDKit**.
-   **Kinases (Proteins):** Utilized **ProteinBERT** embeddings to capture deep semantic representations of amino acid sequences, supplemented with biological classifications (Kinase Group, Mutation status).

### 2. Dimensionality Reduction

-   **PCA on Protein Embeddings:** Reduced high-dimensional ProteinBERT vectors to 150 principal components (retaining >95% variance).
-   **XGBoost Feature Selection:** Filtered sparse Morgan Fingerprint bits to the top ~50 most predictive features based on information gain.
-   **Result:** Compressed input space from ~17,000 features to a dense, highly relevant vector of 224 features.

### 3. The Model (`kiNNet`)

-   **Architecture:** A deep feed-forward neural network (PyTorch).
    -   3 Hidden Layers (512 -> 512 -> 64 neurons).
    -   **Batch Normalization** and **Dropout** (0.5) for regularization.
    -   **ReLU** activation.
-   **Objective:** Regression on log-transformed $K_d$ values.
-   **Performance:** Achieved **73.6% accuracy** in classifying binding affinity thresholds on the test set.

## 🛠️ Tech Stack

-   **ML/DL:** PyTorch, XGBoost, Scikit-learn
-   **Bioinformatics:** RDKit, ProteinBERT, Biopython
-   **Data Processing:** Pandas, NumPy

## 📂 Repository Structure

-   `data/`: Contains training datasets, kinase embeddings, and molecular features.
-   `kinase_selectivity_prediction.ipynb`: Complete pipeline: preprocessing, feature extraction, PCA/XGBoost reduction, training, and evaluation.
-   `regression_model.pth`: Trained model weights.

## 🏆 Results

Our solution secured **2nd Place Overall** and the **Best Pitch Award** at PharmaHacks 2025. The model demonstrated that intelligent dimensionality reduction on high-quality biological embeddings can outperform brute-force approaches on limited datasets.

---

_Team: Kointoss Solutions_
