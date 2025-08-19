README – Clustering Model for Learner Recommendation System

Overview

This module implements the **Clustering Phase** of the learner recommendation pipeline. It applies **K-Means clustering** to the simulated learner dataset (`Simulated_Learner_Dataset.csv`) in order to identify **four distinct learner profiles**. These clusters are then used to map learners to tailored instructional strategies (Plans A–D).

Contents

- `C2_1.ipynb` – Jupyter Notebook for clustering, evaluation, and visualisation.
- `kmeans_model_backup.joblib` – Trained K-Means model (K=4).
- `scaler_backup.joblib` – StandardScaler used for numerical features.
- `encoder_backup.joblib` – OneHotEncoder used for categorical features.
- `cluster_pipeline_backup.joblib` – Combined preprocessing + clustering pipeline.

Requirements

- Python 3.8+
- Jupyter Notebook
- Libraries:

  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `matplotlib`
  - `joblib`

Install dependencies with:


"pip install pandas numpy scikit-learn matplotlib joblib"

Usage

1. Ensure the **dataset** (`Simulated_Learner_Dataset.csv`) is available in the working directory.

   - ⚠️ Use the provided dataset for consistency with the report.
   - Running the data generation notebook again will yield a different dataset and change the clustering results.

2. Open the notebook:

   "jupyter notebook C2_1.ipynb"

3. Run all cells to:

   - Preprocess the dataset (scaling + one-hot encoding).
   - Apply **K-Means clustering** with `K=4`.
   - Validate cluster quality using elbow method, silhouette scores, and PCA visualisation.
   - Save trained models and encoders as `.joblib` files for reuse.

Output

- Clustered Profiles – Segmentation of learners into four profiles with distinct behavioural and cognitive traits.
- Saved Models –

   `kmeans_model_backup.joblib` (trained clustering model).
   `scaler_backup.joblib` (numerical feature standardizer).
   `encoder_backup.joblib` (categorical encoder).
   `cluster_pipeline_backup.joblib` (full preprocessing + clustering pipeline).
- Visuals – Elbow plots, silhouette plots, PCA scatterplots, and boxplots for cluster traits.
Notes
- This step represents **Phase 2: Clustering** of the system pipeline.
- Clustering results directly inform the **strategy mapping** stage, where each cluster is aligned with an instructional plan (A–D).
- To replicate the exact cluster profiles presented in the report, always use the provided **`Simulated_Learner_Dataset.csv`**.
