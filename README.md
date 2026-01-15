# Marketing Spend Attribution Regression

This repository contains a regression-based marketing attribution project that attributes conversions across multiple marketing channels using historical spend data. The goal is to provide a transparent, reproducible analytical pipeline for marketing performance analysis and budget optimization.

---

## Project Overview

The project implements a multi-channel attribution framework using statistical regression techniques. It processes time-series marketing data, applies linear and regularized regression models, and produces structured analytical outputs suitable for both technical analysis and business reporting.

The solution is designed to be modular, extensible, and easy to adapt to new datasets with similar structure.

---

## Data Description

The expected dataset contains time-indexed observations with the following fields:

- `date` – Time period (weekly or daily)
- `conversions` – Total conversions for the period
- Channel spend variables (e.g.):
  - `search_spend`
  - `social_spend`
  - `display_spend`
  - `email_spend`

Data can be loaded from an Excel file or generated synthetically for demonstration purposes.

---

## Methodology

### 1. Data Preparation
- Enforces a consistent time frequency across all variables
- Aligns spend and conversion series on a common timeline
- Fills missing values to preserve continuity
- Treats extreme values to limit the influence of outliers

### 2. Modeling
Two regression models are applied to the cleaned dataset:

- **Ordinary Least Squares (OLS)**
  - Used for coefficient interpretability
  - Produces full statistical diagnostics

- **LASSO Regression**
  - Applies regularization to handle correlated predictors
  - Validates coefficient stability and feature importance

### 3. Attribution Framework
- Channel attribution is derived from regression coefficients
- Coefficients are normalized by average channel spend to allow efficiency-based comparison
- Outputs are structured for downstream reporting and documentation

---

## Tools & Libraries

- Python 3.x
- pandas, numpy
- statsmodels
- scikit-learn
- python-docx (for document generation)

---

## Repository Structure
├── marketing_attribution_regression.ipynb # Main analysis script
├── Marketing_Attribution_Executive_Summary.docx
├── README.md


---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/marketing-attribution-regression.git
   cd marketing-attribution-regression

2. Install dependencies:
   pip install pandas numpy statsmodels scikit-learn python-docx

3. Run the analysis:
   python marketing_attribution_regression.py

4. (Optional) Provide an Excel file path inside the script to use real data instead of sample data.

Outputs

Regression model outputs (OLS summary and LASSO coefficients)

Channel-level attribution and ROI proxy metrics

A standalone one-page executive summary document (DOCX format)

Assumptions & Limitations

Assumes linear relationships between spend and conversions

Does not explicitly model lagged or saturation effects

Results are intended for directional analysis, not causal inference

Extensibility

The project can be extended to include:

Adstock (lagged) effects

Nonlinear response curves

Alternative attribution models

Automated reporting and dashboards

License

This project is provided for educational and analytical purposes. Add a license if required.


---

If you want next:
**a.** Add **badges, screenshots, and example output tables**  
**b.** Convert this into a **portfolio-ready GitHub README (recruiter-focused)**
