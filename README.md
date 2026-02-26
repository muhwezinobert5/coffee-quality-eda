# Determinants of Specialty Coffee Quality  
Construct-Based Statistical Exploratory Data Analysis

---

## 1. Project Overview

This study investigates the determinants of specialty coffee quality using a construct-grounded statistical framework. The objective is to identify which sensory, processing, and origin-related variables significantly influence Total Cup Points.

This project emphasizes:
- Theoretical justification of feature selection
- Advanced preprocessing techniques
- Statistical hypothesis testing prior to modeling
- Clean and reproducible repository structure

---

## 2. Dataset

Dataset: Coffee Quality Data (CQI)  
Source: Kaggle  

The dataset contains professional sensory evaluations of Arabica coffee samples, including aroma, flavor, acidity, body, processing method, and country of origin.

Target Variable:
- Total.Cup.Points (continuous)

Problem Type:
- Regression

---

## 3. Theoretical Framework

Feature selection is grounded in Sensory Evaluation Theory used in professional coffee cupping.

Variables are grouped into three domain-specific constructs:

### A. Sensory Attributes
- Aroma
- Flavor
- Aftertaste
- Acidity
- Body
- Balance

### B. Processing & Physical Characteristics
- Processing Method
- Moisture

### C. Origin & Terroir Effects
- Country of Origin

These constructs theoretically influence perceived quality through chemical composition, post-harvest treatment, and environmental factors.

---

## 4. Construct Mapping Table

| Raw Feature | Construct | Theoretical Justification | Expected Effect |
|-------------|----------|---------------------------|----------------|
| Aroma | Sensory | Volatile compounds influence perception | Positive |
| Flavor | Sensory | Primary taste driver | Positive |
| Aftertaste | Sensory | Persistence affects evaluation | Positive |
| Acidity | Sensory Balance | Brightness impacts grading | Positive |
| Body | Mouthfeel | Texture affects preference | Positive |
| Processing Method | Post-Harvest | Alters chemical development | Varies |
| Moisture | Physical Stability | Affects roasting behavior | Optimal range |
| Country of Origin | Terroir | Soil & climate influence chemistry | Varies |

---

## 5. Missing Data Strategy

Missingness was analyzed to determine mechanism (MCAR vs MAR).

Given evaluator and exporter reporting patterns, missingness is assumed Missing At Random (MAR).

Instead of mean imputation, K-Nearest Neighbors (KNN) imputation was used to preserve multivariate relationships among correlated sensory attributes.

---

## 6. Encoding Strategy

Nominal variables:
- Country of Origin
- Processing Method

These were One-Hot Encoded to prevent false ordinal assumptions.

No ordinal encoding was applied since no natural ranking exists among categories.

---

## 7. Statistical Exploratory Data Analysis

Statistical validation was performed prior to modeling.

### Pearson Correlation
Used to measure linear association between numerical sensory attributes and Total Cup Points.

### ANOVA
Used to test whether processing method significantly affects quality score.

### Chi-Square Test
Used when quality was categorized into high vs low groups to test association with origin.

Significance threshold:
α = 0.05 (Bonferroni correction applied for multiple comparisons)

Raw dataset files are excluded via .gitignore to ensure repository cleanliness and reproducibility.

---
## 8. Statistical Exploratory Data Analysis

### 8.1 Pearson Correlation (Numerical Features vs Target)

- Measures linear association between numeric sensory features and Total Cup Points  
- p-value < 0.05 indicates statistical significance  

### 8.2 ANOVA (Categorical Features vs Target)

- Tests whether `Processing Method` significantly affects Total Cup Points  
- p-value < 0.05 indicates significant difference between groups  

### 8.3 Chi-Square Test (Categorical Features vs Binary Target)

- `High_Quality` = 1 if Total Cup Points > 82, else 0  
- Chi-square test determines association between country of origin and high-quality coffee  

### 8.4 Multiple Testing Adjustment

- Bonferroni correction applied for multiple hypotheses to control Type I error
---
## 9. Reproducibility

To reproduce the analysis:

1. Clone the repository
2. Install dependencies:
   pip install -r requirements.txt
3. Open the notebook in Jupyter or Google Colab
4. Run all cells sequentially

---

## 10. Academic Integrity Statement

This repository demonstrates structured, theory-driven exploratory data analysis in alignment with master's-level methodological standards.
