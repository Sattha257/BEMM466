
README – Generating Data for Learner Recommendation System

Overview

This repository contains the code and dataset used to generate a synthetic learner dataset for the **Machine Learning–based Recommendation System** described in the report. The aim is to simulate learner profiles (ages 5–7) with cognitive, emotional, and behavioural traits, then prepare the dataset for clustering, instructional strategy mapping, and predictive modelling.

Contents

- S0_1.ipynb – Jupyter Notebook implementing the data generation pipeline.
- Simulated_Learner_Dataset.csv – Pre-generated dataset (800 learners) used in the report.

Requirements

- Python 3.8+
- Jupyter Notebook
- Libraries:

  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `matplotlib` (for visualisation, if included)

Install dependencies with:


"pip install pandas numpy scikit-learn matplotlib"


Usage

1. Open the notebook:

   ```bash
   jupyter notebook S0_1.ipynb
   ```
2. Run all cells to generate a **new simulated dataset** of 800 learners.

   * The dataset includes features such as Attention Span, Emotional Regulation, Parental Involvement, Motivation Type, Learning Style, Social Interaction Style, and a computed Outcome Score.
   * The results will be saved as `Simulated_Learner_Dataset.csv`.

**Important Note:**

- Each run of the notebook produces a **different random dataset** due to stochastic generation.
- To reproduce the **exact same results** as presented in the report and appendix, you must use the **provided `Simulated_Learner_Dataset.csv` file**.
- Generating a new dataset will not perfectly match the report’s clustering, learning plans, or evaluation outcomes.

Output

- **Primary file:** `Simulated_Learner_Dataset.csv`
- Each row corresponds to a learner with complete simulated features.
- This dataset serves as the input for later processes:

  1. Clustering (K-Means) to identify learner profiles.
  2. Strategy Mapping to assign instructional plans (A–D).
  3. Classification (Random Forest) to predict strategies for new learners.

## Notes

- The dataset is fully **synthetic**, based on developmental psychology research, ensuring no privacy or ethical risks.
- This step represents **Phase 1: Data Simulation** of the full pipeline.
- For continuity and accurate replication of the dissertation results, always use the provided `Simulated_Learner_Dataset.csv` before moving to clustering and prediction.


