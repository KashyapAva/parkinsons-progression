# 🧬 Parkinson’s Disease Progression Prediction using ML & LSTM

This project applies advanced machine learning techniques to predict the progression of Parkinson’s Disease, focusing on forecasting Unified Parkinson's Disease Rating Scale (UPDRS) scores using clinical, protein, and peptide data.

## 🎯 Goal

To model Parkinson's progression by predicting UPDRS 1, 2, and 3 scores using time series and high-dimensional protein data from longitudinal patient visits.

## 📚 Dataset

- Clinical and protein data derived from cerebrospinal fluid (CSF) samples.
- Temporal structure: multiple visits per patient over several years.
- Features include protein abundance, visit timepoints, medication status, and more.

## 🧪 Models Implemented

- **🧠 LSTM**: Captures temporal dependencies from sequential patient visits.
- **💡 LightGBM**: Best overall performance; handles high-dimensional sparse data via Exclusive Feature Bundling (EFB).
- **🌲 CatBoost**: Gradient boosting with strong performance on categorical features.
- **📈 SVR (Support Vector Regression)**: Explores nonlinear relationships; tuned with Bayesian optimization.

## 🔧 LSTM Model Details

- Architecture: 2 LSTM layers (128 and 64 units) + dense output layer
- Sequence length: 3 visits
- Optimizer: Adam  
- Loss: MAE  
- Final test MAE:
  - UPDRS 1: **3.72**
  - UPDRS 2: **4.74**
  - UPDRS 3: **11.45**

## 📊 Model Comparison

| Model     | Key Strengths                  | Notes                          |
|-----------|--------------------------------|---------------------------------|
| LightGBM  | Best overall MAE and speed     | Great for high-dimensional data |
| LSTM      | Captures temporal patterns     | Competitive performance         |
| SVR       | Handles nonlinearity well      | Lower performance than ensembles |
| CatBoost  | Handles categorical features   | Slightly lower than others      |

## ⚠️ Challenges Addressed

- **Missing data**: Selective imputation and column exclusion (e.g., `updrs_4`, `upd23b`)
- **High dimensionality**: Feature bundling and importance filtering
- **Temporal dynamics**: Modeled with LSTM
- **Hyperparameter tuning**: Handled via Bayesian Optimization and grid search

## 💡 Key Insights

- Clinical features outperformed protein data significantly
- Visit frequency correlated with disease progression
- Feature engineering based on visit timeline improved model accuracy
- Protein signal was weak; time-based and clinical data were more predictive

## 🔗 Code & Notebooks

- [LSTM Notebook (Kashyap)](https://www.kaggle.com/code/kashyapava/stat542-pdp-lstm)
- [CatBoost Model](https://www.kaggle.com/code/shreyasharma23/catboost)
- [SVR Model](https://www.kaggle.com/code/akshatb4/parkinsons-svr/edit)
- [LightGBM Model](https://www.kaggle.com/code/anshankul/lightgbm)
- [EDA + Feature Engineering](https://colab.research.google.com/drive/1MYZMM4X8ehz9ZbkAWzHPzocfMTIhqXa6?usp=sharing)
- [Full Report PDF](STAT542_Midterm_Report_G11.pdf)
- [Python Code](Project_LSTM.ipynb)

## 👥 Contributors

- Kashyap Ava (LSTM modeling)
- Shreya Sharma (CatBoost)
- Akshat Bajpai (SVR)
- Anshankul Jain (LightGBM)
- Sanyam, Govind, Hetarth, Yashna (EDA, feature engineering, LMM, evaluation)

---

*Project submitted for STAT 542: Machine Learning in R at UIUC.*
