# 🧠 Predicting Emotional Overeating from Psychological Schemas

A graduate-level data science project exploring the psychological and behavioural predictors of emotional overeating, using a dataset of 1,500 participants across 35 variables.

---

## 📌 Project Overview

This project pursues **two analytically distinct goals**:

| Goal | Description | Tool Used |
|------|-------------|-----------|
| **Effect Size Estimation** | How large is the association between schema burden and emotional overeating? | Ridge Regression with bootstrapped 95% CIs |
| **Prediction** | Can we build an accurate predictive model for emotional overeating? | Gradient Boosted Machine (GBM) |

The study tests the **stress-buffering hypothesis** — that stress translates into emotional overeating primarily when emotional regulation capacity is compromised.

---

## 📁 Repository Structure

```
├── eating_behavior_FINAL.ipynb        # ✅ Main analysis notebook (final submission)
├── data/
│   └── eating_behavior_body_weight_dataset.csv   # Dataset (1,500 obs × 35 vars)
├── archive/
│   ├── eating_behavior_analysis_V3.ipynb          # Earlier iteration (V3)
│   └── eating_behavior_analysis-Copy2.ipynb       # Draft version
└── README.md
```

---

## 📊 Dataset

| Property | Value |
|----------|-------|
| Observations | 1,500 participants |
| Variables | 35 |
| Missing values | None |
| Duplicates | None |
| Recruitment groups | Medical (77%) & Community (23%) |

**Key variable types:**
- **Psychological schema scores** — YSQ-S3 maladaptive schemas
- **Emotion regulation** — DERS (Difficulties in Emotion Regulation Scale)
- **Perceived stress** — PSS (Perceived Stress Scale)
- **Social support** — MPSS (Multidimensional Perceived Social Support Scale)
- **Anthropometric measures** — BMI, body weight

---

## 🔬 Analytical Pipeline

The final notebook (`eating_behavior_FINAL.ipynb`) covers:

1. **Problem Overview & Analytical Goals** — Dual-goal framing
2. **Data Loading & Setup** — Libraries and configurations
3. **Data Quality & Validation** — Sentinel value detection, range checks, duplicate/missing value audit
4. **Exploratory Data Analysis (EDA)** — Distributions, correlations, group differences
5. **Feature Engineering** — Interaction term (Stress × DERS), centring, ablation tests
6. **Stratified Train-Test Split** — Stratified by recruitment group (medical/community)
7. **Assumption Testing** — OLS baseline; linearity, homoscedasticity, normality of residuals
8. **PCA Sensitivity Analysis** — Empirical test of whether PCA preprocessing is justified
9. **Model Comparison** — Six model configurations compared head-to-head
10. **Final Models**
    - Nested Cross-Validation for unbiased generalisation estimate
    - Ridge Regression with bootstrapped confidence intervals
    - Final model evaluation
11. **Sensitivity Analyses** — Four robustness checks on main findings
12. **GBM Feature Importance Stability** — Stability across CV folds
13. **Ethical & Clinical Reflection** — Limitations, generalisability, clinical implications

---

## 🧪 Key Findings

- **Negativity/Mistrust** and **Emotional Deprivation** schemas show the strongest associations with emotional overeating (largest standardised betas, non-overlapping 95% CIs)
- The **Stress × Emotion-Regulation interaction** term adds predictive signal, supporting the stress-buffering hypothesis
- **PCA preprocessing was not justified** — raw schema features perform equivalently or better
- **Schema_Sum simplification loses information** — individual schema scores retained in the final model
- GBM feature importance rankings are **stable across CV folds**, reinforcing confidence in the top predictors

---

## 🛠️ Requirements

```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy statsmodels shap jupyter
```

**Python version:** 3.8+

---

## 🚀 Getting Started

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# 2. Install dependencies
pip install numpy pandas matplotlib seaborn scikit-learn scipy statsmodels shap jupyter

# 3. Launch the notebook
jupyter notebook eating_behavior_FINAL.ipynb
```

> ⚠️ Make sure the dataset path in the notebook points to `data/eating_behavior_body_weight_dataset.csv`

---

## 📂 Archive

The `archive/` folder contains earlier iterations of the analysis kept for version history. **Do not use these for evaluation** — the final, corrected analysis is in `eating_behavior_FINAL.ipynb`.

---

## 🎓 Academic Context

- **Course:** Data Science (Week 4 Assignment)
- **Program:** PGS (Postgraduate Studies)
- **Analysis type:** Cross-sectional, observational
- **Statistical framework:** Frequentist (with bootstrapped uncertainty quantification)

---

## ⚠️ Ethical Notes

- Data is cross-sectional — **no causal claims** are made
- Schema scores are psychological constructs with **measurement error**
- Findings should not be used for clinical screening without validation on independent samples
- Medical and community recruitment groups differ systematically — results may not generalise uniformly

---

## 📄 License

This project is submitted as academic coursework. All rights reserved.
