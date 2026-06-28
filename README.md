# Peptide Predictor: Data Mining Pipeline for Epitope Identification
*Author: Minan Kahai*

## Overview
Identifying linear B-cell epitopes is a crucial early step in the development of vaccines, diagnostics, and therapeutics for infectious diseases. Because experimental discovery is highly resource-intensive, computational methods are increasingly relied upon to prioritise candidate epitopes.

This repository contains a full data mining pipeline designed to develop a robust classifier capable of predicting epitopes based on features extracted using a state-of-the-art protein embedder. 

## Dataset Architecture
The data pipeline processes high-dimensional protein information:
*   **Training Dataset:** 45,000 samples (44,262 positive class / 738 negative class) across 1,280 initial feature columns.
*   **Holdout Dataset:** 4,606 samples reserved to simulate the real-world deployment of the final predictive model.

## Pipeline Methodology
1.  **Data Preprocessing:** Identified and handled 196,316 missing values across feature columns using median imputation. Features were evaluated against a 50% missingness threshold to prevent noise and avoid overfitting.
2.  **Feature Engineering:** Extracted `peptide_length` and engineered 20 distinct amino acid frequency features (`aa_freq_A` through `aa_freq_Y`) to enrich the predictive capacity of the model.
3.  **Exploratory Data Analysis (EDA):** Mapped feature variance distribution and visualised the top 30 features with the highest missing data counts.
4.  **Modelling:** Evaluated multiple architectures to construct a final predictive ensemble model 

## Core Technologies
*   **Data Processing:** Pandas, NumPy
*   **Visualisation:** Matplotlib, Seaborn
*   **Machine Learning:** Scikit-Learn (RandomForest, SVC, LogisticRegression, GradientBoosting, VotingClassifier, PCA, TruncatedSVD)
