# ML Recommendation System for Personalized Early Childhood Education

**MSc Business Analytics Dissertation — University of Exeter, 2025**  
**Author:** Sattha Ungcharoenchai | BEMM466 Postgraduate Business Research Project  
**Grade:** Distinction

---

## 📌 Project Overview

This project designs and implements a machine learning-based recommendation system that generates **personalized learning strategies for children aged 5–7** based on their individual cognitive, emotional, and behavioural traits.

Traditional education adopts a "one-size-fits-all" approach that often fails the **"middle majority"** — children who are neither high-risk nor exceptionally high-performing, yet receive no individualized support. This system addresses that gap by using data-driven profiling to deliver scalable, personalized instruction.

The system was built on a **fully synthetic dataset** of 800 learner profiles, designed to avoid real-world privacy and ethical constraints while maintaining developmental plausibility grounded in educational psychology research.

---

## 🎯 Research Question

> *"How can a machine learning–based recommendation system be designed to generate personalized learning strategies for children in the majority (80%) population with common developmental traits, by identifying deep behavioural subgroups to support scalable, data-driven decision-making in education?"*

---

## 🏗️ System Architecture — Three-Phase Pipeline

```
Phase 1: Data Simulation
        ↓
   Generate 800 synthetic learner profiles
   (Attention Span, Emotional Regulation, Motivation Type,
    Learning Style, Social Interaction Style, Parental Involvement)
        ↓
Phase 2: Unsupervised Clustering (K-Means, K=4)
        ↓
   Identify 4 distinct learner profiles
   Map each cluster to tailored instructional strategy (Plan A–D)
        ↓
Phase 3: Supervised Prediction (Random Forest)
        ↓
   Train classifier to predict strategy for new learners
   Evaluate with Accuracy, Macro-F1, Feature Importance
```

---

## 📂 Repository Structure

```
BEMM466/
└── Model/
    ├── 01_Generating_Data/
    │   ├── S0_1.ipynb                     # Data simulation notebook
    │   ├── Simulated_Learner_Dataset.csv  # Pre-generated dataset (800 learners)
    │   └── Readme1.txt
    │
    ├── 02_Clustering_Model/
    │   ├── C2_1.ipynb                     # K-Means clustering notebook
    │   ├── kmeans_model_backup.joblib     # Trained K-Means model (K=4)
    │   ├── scaler_backup.joblib           # StandardScaler
    │   ├── encoder_backup.joblib          # OneHotEncoder
    │   ├── cluster_pipeline_backup.joblib # Full preprocessing + clustering pipeline
    │   └── Readme2.txt
    │
    └── 03_Predictive_Model/
        ├── Test_01.ipynb                          # Random Forest classifier notebook
        ├── rf_model_gridsearch.joblib             # Trained Random Forest model
        ├── encoder_Learning_Style.joblib
        ├── encoder_Motivation_Type.joblib
        ├── encoder_Social_Interaction_Style.joblib
        ├── encoder_target.joblib
        └── Readme3.txt
```

---

## 🔧 Technologies & Libraries

| Tool | Purpose |
|------|---------|
| Python 3.8+ | Core programming language |
| Scikit-learn | K-Means clustering, Random Forest, GridSearchCV, preprocessing |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical computation and data simulation |
| Matplotlib | Visualizations (elbow plots, silhouette, PCA, confusion matrix) |
| Joblib | Model serialization and persistence |
| Jupyter Notebook | Interactive development environment |

---

## 🚀 How to Run

Follow the phases in order for full pipeline execution:

### Phase 1 — Data Simulation
```bash
cd Model/01_Generating_Data
jupyter notebook S0_1.ipynb
```
Generates synthetic learner profiles. To reproduce dissertation results exactly, use the provided `Simulated_Learner_Dataset.csv` instead of regenerating.

### Phase 2 — Clustering
```bash
cd Model/02_Clustering_Model
jupyter notebook C2_1.ipynb
```
Applies K-Means clustering (K=4), validates with elbow method and silhouette analysis, and saves trained models.

### Phase 3 — Predictive Modelling
```bash
cd Model/03_Predictive_Model
jupyter notebook Test_01.ipynb
```
Trains and tunes a Random Forest classifier using GridSearchCV, evaluates performance, and predicts instructional strategies for new learner profiles.

---

## 📊 Dataset Features

| Feature | Type | Description |
|---------|------|-------------|
| Attention Span | Numerical | Minutes of sustained focus (based on developmental benchmarks for ages 5–7) |
| Emotional Regulation | Numerical | Self-regulation ability score |
| Parental Involvement | Numerical | Level of parental engagement |
| Motivation Type | Categorical | Intrinsic / Extrinsic (Self-Determination Theory) |
| Learning Style | Categorical | Visual / Auditory / Kinesthetic / Mixed |
| Social Interaction Style | Categorical | Cooperative / Solitary / Flexible |
| Outcome Score | Numerical | Computed weighted performance score (0–100) |

> **Note:** All 800 profiles are fully synthetic — no real student data was used. Simulation was grounded in established developmental psychology literature to maintain ecological plausibility while ensuring full GDPR compliance.

---

## 📈 Results Summary

- **4 learner clusters** identified with statistically distinct and pedagogically meaningful profiles
- Each cluster mapped to a tailored instructional strategy (Plans A–D) aligned with established pedagogical frameworks
- **Random Forest classifier** trained with GridSearchCV hyperparameter tuning
- Model evaluated using Accuracy and Macro-F1 Score for balanced performance across all strategy classes
- Feature importance analysis identified **Attention Span**, **Emotional Regulation**, and **Parental Involvement** as strongest predictors

---

## 🧠 Instructional Strategies

| Plan | Profile Description | Strategy Focus |
|------|-------------------|----------------|
| A | High attention, high self-regulation, intrinsic motivation | Independent inquiry, advanced scaffolding |
| B | Moderate attention, extrinsic motivation, cooperative style | Structured peer collaboration |
| C | Low attention span, high parental involvement | Short task cycles, multimodal instruction |
| D | Mixed learning style, flexible social interaction | Differentiated blended learning |

---

## ⚖️ Ethical Considerations

- **No real student data used** — fully synthetic dataset eliminates privacy risks
- **GDPR compliant** — no identifiable personal information collected or processed
- **Explainable AI design** — K-Means + Random Forest chosen for interpretability over black-box accuracy
- **Bias awareness** — synthetic data designed to avoid demographic skew; limitations acknowledged
- **Human-in-the-loop** — system designed to support educator judgment, not replace it

---

## 🔬 Limitations & Future Work

- Synthetic data may not fully capture real classroom complexity or cultural variation
- Future validation with anonymised real-world datasets recommended
- Adaptive profiling (updating clusters as learners develop) is a key extension
- Fairness metrics and bias auditing should be applied before any real deployment

---

## 📬 Contact

**Sattha Ungcharoenchai**  
📧 sattha.un@gmail.com  
📍 Bangkok, Thailand  

---

*This project was developed as part of an MSc dissertation and serves as a proof-of-concept prototype. It is intended for academic and portfolio purposes.*
