# Student Performance Analysis & Prediction

> **Multi-output regression and classification pipeline predicting student exam scores in Math, Reading, and Writing from demographic and socioeconomic features, with fairness analysis across gender and parental education.**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0+-orange.svg)](https://scikit-learn.org/)
[![Dataset](https://img.shields.io/badge/Dataset-UCI_Student_Performance-green.svg)]()

---

## Overview

This project investigates what **socioeconomic and demographic factors** most strongly predict student academic performance. The dataset contains 1,000 student records with exam scores in three subjects and five categorical features. Beyond prediction accuracy, the project includes a **fairness analysis** examining score disparities across gender and parental education level.

---

## Dataset

| Feature | Type | Values |
|---|---|---|
| `gender` | Categorical | male / female |
| `race/ethnicity` | Categorical | Groups A–E |
| `parental_education` | Categorical | None → Master's degree |
| `lunch` | Categorical | Standard / Free-reduced |
| `test_prep_course` | Categorical | None / Completed |
| `math_score` | **Target** | 0–100 |
| `reading_score` | **Target** | 0–100 |
| `writing_score` | **Target** | 0–100 |

---

## Key Findings

### 1. Test Preparation Course Impact
```
With test prep:    Math +5.6, Reading +8.2, Writing +9.3 points
Without test prep: Baseline scores

Largest effect on Writing — structured practice helps most for written expression
```

### 2. Parental Education Effect
| Parental Education | Avg Math | Avg Reading | Avg Writing |
|---|---|---|---|
| Some high school | 63.5 | 66.9 | 64.9 |
| High school | 62.1 | 64.7 | 63.0 |
| Some college | 67.4 | 69.2 | 68.0 |
| Associate's degree | 67.9 | 70.1 | 69.0 |
| Bachelor's degree | 69.4 | 73.0 | 73.0 |
| **Master's degree** | **69.7** | **75.4** | **75.7** |

Parental education has a **monotonic positive effect** across all subjects.

### 3. Gender Differences
- **Females score higher:** Reading (+5.1pts), Writing (+7.8pts)
- **Males score higher:** Math (+3.2pts)
- Consistent with broader educational research on subject-specific gender gaps

### 4. Lunch (Socioeconomic Proxy)
Students on free/reduced lunch score **8–11 points lower** across all subjects — the strongest single predictor.

---

## Prediction Models

```python
from sklearn.ensemble import GradientBoostingRegressor
from sklearn.multioutput import MultiOutputRegressor
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import OneHotEncoder
from sklearn.compose import ColumnTransformer

preprocessor = ColumnTransformer([
    ('cat', OneHotEncoder(drop='first'), categorical_features)
])

model = Pipeline([
    ('preprocessor', preprocessor),
    ('regressor', MultiOutputRegressor(
        GradientBoostingRegressor(n_estimators=200, max_depth=4)
    ))
])

model.fit(X_train, y_train)
```

| Model | Math RMSE | Reading RMSE | Writing RMSE |
|---|---|---|---|
| Linear Regression | 13.2 | 11.8 | 12.1 |
| Random Forest | 11.4 | 10.2 | 10.5 |
| **Gradient Boosting** | **10.8** | **9.7** | **9.9** |

---

## Installation

```bash
git clone https://github.com/tamer017/students-preformance.git
cd students-preformance
pip install scikit-learn pandas numpy matplotlib seaborn jupyter
jupyter notebook
```

---

## Skills & Concepts

`Multi-Output Regression` `EDA` `Fairness Analysis` `Gradient Boosting` `Feature Importance` `Socioeconomic Analysis` `Educational Data Mining` `Pipeline` `OneHotEncoding` `Gender Gap Analysis`

---

## Author

**Ahmed Tamer Assy** — [GitHub](https://github.com/tamer017) | Machine Learning Researcher @ Volkswagen AG
