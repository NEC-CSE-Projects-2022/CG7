
CG7 – Echoes of the Hidden Filter: Interpretable Ensemble Intelligence for Early CKD Prognosis

## Team Info
- Dodda Venkata Reddy
_Work Done: Data preprocessing, ensemble model design, Random Forest & XGBoost implementation

- 22471A05J9 —   Sura Venkata Siva Naga Lakshmi
_Work Done: Feature engineering, SMOTE balancing, model evaluation, result analysis

- 22471A05G2 —  Kolli Kaveri
_Work Done: Exploratory Data Analysis (EDA), visualization, preprocessing pipeline

- 22471A05G3 —  Konda Pratyusha
_Work Done: Explainable AI integration (SHAP & LIME), documentation, deployment planning

---

## Abstract
Chronic Kidney Disease (CKD) is a silent and progressive condition that often remains undetected in its early stages. This project proposes Echoes of the Hidden Filter, an interpretable ensemble learning framework that combines multiple machine learning models to enable accurate and explainable early CKD prediction. By integrating robust preprocessing, feature selection, class balancing, and explainable AI techniques, the system achieves high predictive performance while maintaining clinical transparency.

---

## Paper Reference (Inspiration)
👉  Echoes of the Hidden Filter: Interpretable Ensemble Intelligence for Early CKD Prognosis
  – Dodda Venkata Reddy
 
Original conference/IEEE paper used as inspiration for the model.

---

## Our Improvement Over Existing Paper
Combined multiple classifiers instead of relying on a single model

Applied SMOTE to handle real-world class imbalance

Used variance thresholding + RFE for optimal feature selection

Integrated SHAP and LIME to improve interpretability and clinical trust

Achieved ~99% accuracy with Random Forest, outperforming baseline models

---

## About the Project

What the project does:
Predicts whether a patient has Chronic Kidney Disease using clinical and demographic data.

Why it is useful:
Early detection allows timely medical intervention, reducing the risk of kidney failure and costly treatments like dialysis or transplant.

Workflow:
Patient Data → Preprocessing → Feature Selection → Ensemble ML Models → CKD Prediction + Explanation
---

## Dataset Used
👉 https://www.kaggle.com/datasets/mansoordaku/ckdisease

**Dataset Details:**

400 patient records

25 clinical & demographic features

Binary target variable (CKD / Non-CKD)

Contains missing values and class imbalance


## Dependencies Used
Python, NumPy, Pandas, Scikit-learn, XGBoost, Matplotlib, Seaborn, SHAP, LIME, Imbalanced-learn (SMOTE)



## EDA & Preprocessing

Missing value analysis and visualization

Regression-based and statistical imputation

Label encoding for categorical features

Min-Max feature scaling

Variance threshold filtering

SMOTE for class balancing


## Model Training Info
Models used: Logistic Regression, SVM, Random Forest, XGBoost, KNN, Naive Bayes, ANN

Train-test split: 80:20

Stratified k-Fold Cross Validation

Hyperparameter tuning for ensemble models

## Model Testing / Evaluation
Evaluation metrics:

Accuracy

Precision

Recall

F1-Score

Confusion Matrix

Random Forest achieved the best overall performance.

## Results
All models achieved >95% accuracy

Random Forest: ~99% accuracy

Ensemble and ANN models showed stable and reliable performance

SHAP and LIME highlighted key biomarkers such as:

   Serum Creatinine

   eGFR

    Blood Urea

    Hemoglobin

## Limitations & Future Work
Limitations:

  Small dataset size

  No external or multi-center validation

  Computational cost of explainability techniques

Future Work:

  Use larger, multi-institution datasets

  Incorporate longitudinal patient data

  Optimize model inference for real-time deployment

Integrate system into clinical decision support tools
## Deployment Info
Can be deployed as a Flask / FastAPI web application

Input: Patient clinical values

Output: CKD prediction with explainable insights

Suitable for hospital screening and decision support systems
