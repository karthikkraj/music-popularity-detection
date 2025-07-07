---

# 🎵 Music Popularity Prediction via Regression Modeling

This project explores the construction and evaluation of regression-based machine learning models to predict the **popularity of music tracks** using a diverse set of acoustic and musical features. The goal is to build a predictive system that enables **music industry stakeholders**—including producers, distributors, and marketing teams—to make informed, data-driven decisions regarding song performance.

---

## 🎯 Objective

To develop and assess a suite of supervised regression algorithms capable of estimating a track’s **popularity score**—defined on a continuous scale from 0 to 100—based solely on measurable musical attributes.

### Feature Set:

- `acousticness`
- `danceability`
- `energy`
- `instrumentalness`
- `liveness`
- `speechiness`
- `tempo`
- `valence`
- `loudness`
- `duration_ms`
- `key` (categorical)
- `mode` (categorical)
- `time_signature` (categorical)

The primary research question is:

> *Can musical and acoustic features reliably predict the commercial success of a song using regression models?*

---

## 📊 Dataset Overview

The dataset comprises **227 songs**, each annotated with:

- Quantitative audio features (float)
- Categorical musical attributes
- Target variable: **`popularity`**

The dataset was manually reviewed and preprocessed to ensure modeling integrity.

---

## 🔍 Methodological Framework

### 1. 🧹 Data Preprocessing

- Missing value imputation
- Outlier detection and mitigation using IQR
- Feature normalization using **StandardScaler**
- One-hot encoding of categorical variables (`key`, `mode`, `time_signature`)

---

### 2. 📊 Exploratory Data Analysis (EDA)

- Univariate and bivariate statistical plots
- Pearson correlation matrix
- Feature-target relationships via scatterplots and histograms

---

### 3. 🧠 Feature Engineering & Selection

- Correlation filtering to identify highly relevant predictors
- **Variance Inflation Factor (VIF)** analysis to remove multicollinearity

---

### 4. 🏗️ Model Architecture

The following regression models were implemented, trained, and tuned:

| Model                     | Description                           |
|--------------------------|---------------------------------------|
| Linear Regression        | Baseline OLS regression               |
| Ridge Regression         | L2-regularized linear model           |
| Lasso Regression         | L1-regularized linear model           |
| Decision Tree Regressor  | Non-parametric tree-based model       |
| Random Forest Regressor  | Ensemble of decision trees (bagging)  |
| Gradient Boosting        | Ensemble using additive optimization  |
| XGBoost Regressor        | Efficient gradient boosting variant   |

---

### 5. 📈 Model Evaluation

Models were benchmarked using the following metrics:

**Mean Absolute Error (MAE)**  
MAE = (1/n) * Σ | yᵢ - ŷᵢ |

**Mean Squared Error (MSE)**  
MSE = (1/n) * Σ (yᵢ - ŷᵢ)²

**Root Mean Squared Error (RMSE)**  
RMSE = √MSE

**Coefficient of Determination (R²)**  
R² = 1 - [ Σ(yᵢ - ŷᵢ)² / Σ(yᵢ - ȳ)² ]


These metrics were used to assess the predictive accuracy and generalization performance of each model.

---

## 🧪 Results Summary

After hyperparameter tuning and cross-validation:

- The **Random Forest Regressor** emerged as the best-performing model.
- It achieved:
  - **R² ≈ 0.89**
  - **Low MAE and RMSE**, indicating minimal deviation from actual popularity scores.

> Random Forests demonstrated superior robustness to outliers and captured complex nonlinear relationships in the dataset.

---

## 📊 Visual Analytics

Visualizations included in the project:

- Heatmaps for correlation analysis
- Boxplots for distribution and outlier detection
- Scatter plots: Actual vs. Predicted values
- Bar plots for feature importances in tree-based models

---

## ⚙️ Installation & Usage

### 🔗 GitHub

```bash
git clone https://github.com/karthikkraj/music-popularity-prediction.git
cd music-popularity-prediction

### 📦 Dependencies

Install required Python libraries:

```bash
pip install -r requirements.txt
```

Or simply open the `.ipynb` file using **Google Colab** for direct execution without local setup.

---

## 🧾 Conclusion

✅ The project demonstrates that **audio and musical features can serve as strong predictors** of song popularity using supervised regression approaches.
✅ Ensemble models, particularly **Random Forest** and **Gradient Boosting**, deliver significantly higher accuracy compared to linear baselines.

---

## 🔮 Future Work

To enhance the predictive power and practical applicability:

* Incorporate **natural language processing (NLP)** on lyrics
* Model **temporal dynamics** (seasonality, release dates)
* Convert to a **multi-class classification** model (e.g., Hit vs. Flop)
* Integrate **real-time streaming metrics** from platforms like Spotify API

---

## 👨‍💻 Author

**Karthik Raj**
*Machine Learning & Data Science Practitioner*
**Project: Music Popularity Prediction | 2025**

---

## 🪪 License

Distributed under the **MIT License**. See [`LICENSE.md`](./LICENSE.md) for full terms.

---
