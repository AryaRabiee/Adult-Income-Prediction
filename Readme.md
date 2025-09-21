# 🏆 Adult Income Prediction (Census Income Dataset)

This project uses the Adult Dataset (from the UCI Machine Learning Repository) to predict whether a person earns more than $50K per year based on demographic and work-related attributes.

## 📂 Dataset

32,561 records with demographic and occupational attributes

Key features:

age – Age of the individual

workclass – Type of employment (Private, Self-emp, Government, etc.)

education_num – Education level (numeric)

occupation – Occupation category

relationship – Relationship status (Husband, Wife, Single, etc.)

race, sex

capital_gain, capital_loss

hours_per_week

Target: income → >50K or <=50K

## 🛠 Data Preprocessing

✅ Steps applied to the dataset:

Replaced missing values (?) with "Unknown"

Dropped records where workclass was "Never-worked" or "Without-pay"

Merged similar categories:

All government jobs → "Government"

"Handlers-cleaners" & "Priv-house-serv" → "Other-service"

"Protective-serv" & "Armed-Forces" → "Protective/Armed"

"Married-AF-spouse" → "Married-civ-spouse"

"Married-spouse-absent" → "Separated"

"Own-child" & "Not-in-family" → "Single"

Dropped irrelevant columns (fnlwgt, native_country, education)

Created new features:

age_group using pd.cut() (bins: 0–25, 26–35, …)

capital_net = capital_gain - capital_loss

Converted sex to numeric (Male=1, Female=0)

## 📊 Models Used

We trained and evaluated multiple models:

KNN (with hyperparameter tuning for best k)


SVC (RBF kernel)

XGBoost ✅ (best performing model)

📈 Metrics

Evaluation metrics:

Accuracy

Precision, Recall, F1-score

ROC-AUC

Sample Results (Best Model - XGBoost):

Accuracy ≈ 0.87

F1-score ≈ 0.70

ROC-AUC ≈ 0.92

📉 Visualizations

Confusion Matrix (for each model)

ROC Curve & AUC Score

Error Rate vs. K (for KNN)

