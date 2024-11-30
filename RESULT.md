# Model Performance Comparison

This document presents a detailed evaluation of various machine learning models and hybrid approaches applied to our diarrhea dataset. The models are assessed based on their **accuracy** and **R² scores**, with a focus on both individual and hybrid model performances.

### Note on Hybrid Models
- **Hybrid RF-GBT**: Combines Random Forest with Gradient Boosting Trees to leverage the strengths of both algorithms.
- **Hybrid RF-XGB**: Combines Random Forest with XGBoost, aiming to combine the power of decision trees with gradient boosting techniques.

### Note on Severity Levels
Severity levels (*Mild, Medium, Severe*) were determined based on the distribution of diarrhea cases within each region:
- **Mild (0)**: Cases falling below or equal to the first quartile (Q1).
- **Medium (1)**: Cases between the first quartile (Q1) and the third quartile (Q2).
- **Severe (2)**: Cases exceeding the third quartile (Q2).

The severity levels were computed region-wise to account for the varying distributions of cases across different regions.

### Note on Lagged Variables
Lagged variables were created to account for temporal dependencies and model the historical impact of environmental factors:
- **1-day lag**: Includes `Severity_Level_1day_lag` and `Diarrhea_1day_lag`, which capture how changes in weather conditions from the previous day might influence the current day's diarrhea severity.
- **3-day lag**: Includes `Severity_Level_3day_lag` and `Diarrhea_3day_lag`, which help model delayed effects of weather and environmental factors, such as how weather patterns from three days ago could still impact diarrhea outcomes today.

These lagged variables enhance the models by incorporating past trends, providing a more accurate prediction of future outcomes.

---

## Regression Model on Diarrhea

### Individual Model Performance

| **Model**             | **R² Score** |
|------------------------|--------------|
| Linear Regression      | 0.18         |
| Random Forest          | 0.18         |
| Gradient Boosting      | 0.23         |
| XGBoost                | -0.02        |

### Hybrid Model Performance

| **Hybrid Model**       | **R² Score**       |
|------------------------|--------------------|
| Hybrid RF-GBT          | 0.22              |
| Hybrid RF-XGB          | 0.12              |

---

## Regression Model on Diarrhea with 1-Day Lag

### Individual Model Performance

| **Model**             | **R² Score** |
|------------------------|--------------|
| Linear Regression      | 0.13         |
| Random Forest          | 0.16         |
| Gradient Boosting      | 0.20         |
| XGBoost                | -0.01        |

### Hybrid Model Performance

| **Hybrid Model**       | **R² Score**       |
|------------------------|--------------------|
| Hybrid RF-GBT          | 0.20              |
| Hybrid RF-XGB          | 0.11              |

---

## Regression Model on Diarrhea with 3-Day Lag

### Individual Model Performance

| **Model**             | **R² Score** |
|------------------------|--------------|
| Linear Regression      | 0.13         |
| Random Forest          | 0.19         |
| Gradient Boosting      | 0.20         |
| XGBoost                | 0.03         |

### Hybrid Model Performance

| **Hybrid Model**       | **R² Score**       |
|------------------------|--------------------|
| Hybrid RF-GBT          | 0.22              |
| Hybrid RF-XGB          | 0.14              |

---

## Classification Model on Severity

### Individual Model Performance

| **Model**             | **Accuracy** |
|------------------------|--------------|
| Logistic Regression    | 0.52         |
| Random Forest          | 0.50         |
| Gradient Boosting      | 0.51         |
| XGBoost                | 0.49         |

### Hybrid Model Performance

| **Hybrid Model**       | **Accuracy**       |
|------------------------|--------------------|
| Hybrid RF-GBT          | 0.51              |
| Hybrid RF-XGB          | 0.50              |

---

## Classification Model on Severity with 1-Day Lag

### Individual Model Performance

| **Model**             | **Accuracy** |
|------------------------|--------------|
| Logistic Regression    | 0.49         |
| Random Forest          | 0.50         |
| Gradient Boosting      | 0.51         |
| XGBoost                | 0.51         |

### Hybrid Model Performance

| **Hybrid Model**       | **Accuracy**       |
|------------------------|--------------------|
| Hybrid RF-GBT          | 0.52              |
| Hybrid RF-XGB          | 0.51              |

---

## Classification Model on Severity with 3-Day Lag

### Individual Model Performance

| **Model**             | **Accuracy** |
|------------------------|--------------|
| Logistic Regression    | 0.54         |
| Random Forest          | 0.51         |
| Gradient Boosting      | 0.52         |
| XGBoost                | 0.47         |

### Hybrid Model Performance

| **Hybrid Model**       | **Accuracy**       |
|------------------------|--------------------|
| Hybrid RF-GBT          | 0.53              |
| Hybrid RF-XGB          | 0.47              |

---

For further details on methodology, feature engineering, and implementation, refer to the accompanying notebook.
