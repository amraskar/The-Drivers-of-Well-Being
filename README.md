# The Drivers of Well-Being: An Explainable AI Approach to OECD Socioeconomics

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange.svg)
![Statsmodels](https://img.shields.io/badge/Statsmodels-Econometrics-green.svg)

## 📌 Project Overview
This repository contains a Master's-level Data Science project that investigates the macroeconomic determinants of subjective well-being across OECD nations. 

**Academic Context**: Data Science Lab – Master's Degree in Data Science, University of Milano-Bicocca (UNIMIB)

Rather than relying on traditional economic assumptions, this project utilizes a **Dual-Model Strategy** to evaluate sovereign data:
1. **Explainable AI (Random Forest + SHAP):** Deployed to agnostically extract non-linear thresholds and identify the compound negative impact of extreme financial stress and energy poverty.
2. **Econometric Inference (Pooled OLS with HC3):** Deployed to mathematically prove a statistically significant behavioral shift in the psychological penalties of material deprivation between the 2021 pandemic crisis and the 2023 recovery.

---

## 📊 Key Findings & Visualizations

### 1. Predictive Validation (Random Forest)
The initial unconstrained algorithm identified employment stability, financial stress, physical pain, and material deprivation as the dominant predictors of national well-being, achieving an initial out-of-sample $R^2$ of 0.521. 

![Random Forest Feature Importance](images/output.png)
*Figure 1: Random Forest Feature Importance. Ranking of the 10 objective socio-economic features based on Mean Decrease in Impurity*

### 2. The Poverty Penalty & Demographic Paradox (SHAP)
Using SHapley Additive exPlanations, we elevated the model from a "black box" to an interpretable framework. 

![SHAP Summary Plot](images/output1.png)
*Figure 2: SHAP Summary Plot of Global Macroeconomic Well-Being. The horizontal axis denotes the marginal impact on predicted Life Satisfaction, while the color gradient represents the original feature magnitude (red = high, blue = low).*

### 3. The Post-Pandemic Temporal Shift (Pooled OLS)
To prove causation and handle the heteroskedasticity of macroeconomic outliers, the AI findings were passed to a Pooled Interaction Model utilizing HC3 Robust Standard Errors.

![Temporal Shift Coefficients](images/output2.png)
*Figure 3: Post-Pandemic Shift in Macroeconomic Penalties. A comparative visualization of standardized OLS coefficients. The graph visually confirms that while the penalty for general financial stress remained constant (far right), the psychological penalty for energy poverty drastically worsened during the 2023 inflationary recovery (far left). Furthermore, baseline employment re-emerged as a positive driver of well-being as pandemic-era labor anomalies subsided.*

---

## 📁 Repository Structure
* **`Project_final.ipynb`**: The complete Jupyter Notebook containing the data ingestion, automated ML pipeline, SHAP interpretability, and HC3 OLS regressions.
* **`Report.pdf`**: The formal 50-page academic thesis detailing the theoretical methodology and causal inference.
* **`data_all.csv`**: The raw OECD Current Well-Being Database extract *(Note: Only included if within size limits).*
* **`/images`**: Directory containing the generated analytical plots.

## ⚙️ Tech Stack
* **Data Processing & Imputation:** `pandas`, `scikit-learn` (KNNImputer, StandardScaler)
* **Machine Learning:** `RandomForestRegressor`, `GridSearchCV`
* **Explainable AI:** `shap`
* **Econometrics:** `statsmodels` (Pooled OLS, HC3 Robust Standard Errors)
* **Visualization:** `seaborn`, `matplotlib`
