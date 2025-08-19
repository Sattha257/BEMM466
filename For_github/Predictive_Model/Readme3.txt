README – Predictive Model for Learner Recommendation System

Overview

This module implements the **Supervised Prediction Phase** of the learner recommendation system. Using the clustered profiles and mapped instructional strategies (Plans A–D), it trains a **Random Forest classifier** to predict the most suitable instructional strategy for new learners based on their cognitive, emotional, and behavioural traits.

Contents

- `Test_01.ipynb` – Notebook for training, evaluating, and testing the predictive model.
- `rf_model_gridsearch.joblib` – Trained Random Forest model (best parameters selected by GridSearch).
- Encoders:

  - `encoder_Learning_Style.joblib`
  - `encoder_Motivation_Type.joblib`
  - `encoder_Social_Interaction_Style.joblib`
  - `encoder_target.joblib` (for instructional strategies A–D).

Requirements

- Python 3.8+
- Jupyter Notebook
- Libraries:

  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `joblib`
  - `matplotlib`

Install with:

"pip install pandas numpy scikit-learn joblib matplotlib"

Usage

1. Ensure you have the **clustered dataset** with assigned strategy labels (A–D).

   - ⚠️ Use the dataset derived from the provided `Simulated_Learner_Dataset.csv` to reproduce the report’s results.
   - Using a new dataset will generate different labels and prediction outcomes.

2. Open the notebook:


   "jupyter notebook Test_01.ipynb"


3. Run all cells to:

   * Load the preprocessed dataset.
   * Train and tune a **Random Forest classifier** using GridSearchCV.
   * Evaluate performance with Accuracy and Macro-F1 Score.
   * Save trained model and encoders as `.joblib` files.
   * Predict instructional strategies (A–D) for new learner profiles.

Output

- Trained Model: `rf_model_gridsearch.joblib` (Random Forest, tuned hyperparameters).
- Encoders: Category encoders for consistent input preprocessing and label decoding.
- Metrics: Accuracy and Macro-F1 Score to assess balanced performance across all strategies.
- Feature Importance: Rankings of which learner traits (e.g., attention span, emotional regulation, parental involvement) most strongly influenced predictions.

Notes

- This represents **Phase 3: Predictive Modelling** of the pipeline.
- To replicate the results presented in the dissertation, you must use the **provided dataset** and not regenerate new random data.
- The model is explainable (via feature importance) to ensure transparency in educational contexts.
- Predictions are single-label (best-fit instructional strategy) for interpretability in classroom settings.

