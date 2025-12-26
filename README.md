##  NeurIPS Polymer Property Prediction 2025

**🏅 Silver Medal — Rank 43 / 2,230 (Top 2%)**

###  Overview

This repository presents two end-to-end pipelines developed for the **NeurIPS Open Polymer Prediction 2025** competition on Kaggle.
The objective was to predict five key polymer properties from **molecular graph structures** and **chemical descriptors**.

Two complementary modeling strategies were implemented:

* **Traditional ML Ensemble** — leveraging **Morgan fingerprints**, **RDKit descriptors**, and **engineered feature interactions** with **gradient boosting models**.
* **Graph Neural Network (GNN) Pipeline** — utilizing **graph embeddings**, **descriptors**, and **3D molecular representations**.

The final **stacking ensemble**, integrating both approaches, secured a **Silver Medal (Top 2%)** on the leaderboard.


###  Problem Statement

Predict the following polymer properties from molecular structures with robust, generalizable models:

* Glass Transition Temperature (Tg)
* Density
* Fractional Free Volume (FFV)
* Thermal Conductivity (Tc)
* Radius of Gyration


###  Methodology & Workflow

#### **Exploratory Data Analysis & Preprocessing**

* Conducted comprehensive EDA to assess feature distributions, correlations, and missingness.
* Generated **Morgan fingerprints** (varied radii) and **RDKit descriptors**.
* Applied **imputation** for missing values to retain data completeness.
* Designed **handcrafted feature interactions** for enhanced expressiveness.
* Incorporated **3D molecular features** and **monomer-level augmentations**.

#### **Modeling**

* Established a **LightGBM baseline** for performance benchmarking.
* Trained **LightGBM, XGBoost, and CatBoost** models on curated features.
* Developed **MLP** and **GNN-based models** to capture non-linear and graph-structured relationships.
* Implemented **Stratified K-Fold Cross-Validation** for robust evaluation.
* Finalized with a **stacking ensemble** combining three gradient boosting models and an **ElasticNet meta-learner**.
* Utilized **out-of-fold (OOF)** predictions for unbiased ensemble training.

#### **Feature & Model Selection**

* Performed **feature importance analysis** to guide model-specific feature selection.
* Identified **RDKit descriptors** and **Morgan fingerprints** as dominant for FFV and Tc.
* Combined **RDKit, Morgan, and interaction features** for density and radius of gyration.
* Enhanced Tg predictions via **distribution-based post-processing**.

#### **Evaluation**

* Tracked metrics: **RMSE**, **MAE**, and **weighted MAE**.
* Conducted **diagnostic plots** for model validation and feature interpretation.


###  Results

* **Rank:** 43 / 2,230 (Top 2%)
* **Medal:** Silver
* **Final Approach:** Stacking ensemble (GNN embeddings + traditional ML models)
* Demonstrated **strong generalization** and **cross-validation alignment**.


###  Key Insights

* **Hybrid feature representations** (graph + descriptor) yield significant performance gains.
* **OOF training and stratified CV** are critical for reliable ensemble performance.
* **Post-processing** using target distribution analysis improved Tg accuracy.
* **Stacking ensembles** with diverse base learners and a linear meta-model achieved optimal balance between bias and variance.
