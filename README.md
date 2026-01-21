# Marketing Spend Attribution using Regression (Marketing Mix Modeling)

## Overview

This project demonstrates a **regression-based marketing attribution framework** designed to evaluate the effectiveness of multiple marketing channels and support **data-driven budget allocation decisions**.

Using **historical weekly marketing spend data**, the analysis quantifies each channel’s **marginal contribution to conversions**, validates results using regularization, and produces **business-ready insights** suitable for stakeholders, marketing leaders, and analysts.

The solution emphasizes **transparency, interpretability, and reproducibility**, aligning with real-world marketing analytics workflows.

---

## Business Problem

Marketing teams invest across multiple channels (Search, Social, Display, Email), but determining **which channels truly drive conversions** is challenging due to overlap, correlation, and noise in performance data.

This project answers key business questions:
- Which marketing channels deliver the **highest return on spend**?
- Which channels are **underperforming**?
- How should budgets be **reallocated** to improve efficiency?
- Are insights **statistically stable** under correlated predictors?

---

## Dataset

- **Granularity:** Weekly  
- **Time Horizon:** 104 weeks (2 years)  
- **Data Type:** Synthetic but enterprise-realistic marketing spend data  

The dataset is structured to support regression-based attribution and ROI analysis.

---

## Methodology

### 1. Data Preparation
- Enforced consistent **weekly time frequency**
- Sorted and indexed time-series data
- Interpolated missing values to preserve continuity
- Applied **winsorization** to limit the influence of extreme outliers

### 2. Modeling Approach

#### Ordinary Least Squares (OLS)
- Provides **interpretable coefficients**
- Enables statistical diagnostics (p-values, confidence intervals)
- Serves as the primary attribution model

#### LASSO Regression
- Applies **regularization** to handle multicollinearity
- Validates coefficient stability
- Shrinks weak or redundant channel effects toward zero

---

## Attribution & ROI Framework

- Channel attribution is derived from **regression coefficients**
- Coefficients are normalized by **average channel spend**
- Produces an **ROI proxy metric** for relative efficiency comparison

This enables comparison of channels based on **incremental impact per dollar spent**, not just total volume.

---

## Key Insights (Example Results)

- **Email marketing** delivers the highest marginal return per dollar spent
- **Paid Search** shows strong and stable contribution
- **Display advertising** underperforms relative to cost
- LASSO confirms Email and Search as dominant drivers under regularization

### Business Recommendation
- Reallocate **10–20% of budget** from low-performing channels (e.g., Display)
- Increase investment in **high-efficiency channels** (e.g., Email)
- Review performance quarterly to monitor saturation effects

---

## Tools & Technologies

- **Python 3**
- **pandas, numpy** – data manipulation
- **statsmodels** – OLS regression and diagnostics
- **scikit-learn** – LASSO regression and preprocessing
- **openpyxl, python-docx** – reporting and documentation

---

## Repository Structure
├── marketing_attribution_regression.ipynb
├── marketing_spend_data_104_weeks_high_r2.xlsx
├── Marketing_Attribution_Executive_Summary.docx
├── README.md


---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/marketing-attribution-regression.git
   cd marketing-attribution-regression
2. Install dependencies:
   pip install pandas numpy statsmodels scikit-learn openpyxl python-docx

3. Run the analysis:
   main("marketing_spend_data_104_weeks_high_r2.xlsx")
## Data Dictionary

The dataset represents **weekly marketing performance and spend data** across multiple digital channels. Each row corresponds to a single weekly observation.

| Column Name | Data Type | Description |
|------------|----------|-------------|
| `date` | Date | Week start date (weekly frequency). Used as the time index for all analyses. |
| `conversions` | Integer | Total number of conversions (e.g., purchases, sign-ups, leads) recorded during the week across all marketing channels. |
| `search_spend` | Numeric | Weekly spend on paid search advertising platforms such as Google Ads or Bing Ads. |
| `social_spend` | Numeric | Weekly spend on paid social media advertising (e.g., Meta, LinkedIn, Twitter/X). |
| `display_spend` | Numeric | Weekly spend on display and programmatic advertising channels. |
| `email_spend` | Numeric | Weekly spend on email marketing campaigns, including tools, creative, and distribution costs. |

### Notes on Data Generation
- The dataset is **synthetically generated** to reflect realistic enterprise marketing spend patterns.
- Conversions are modeled as a **linear function of channel spend** with controlled random noise to simulate real-world variability.
- Spend values are **non-negative** and follow stable weekly distributions.
- The structure is designed to support:
  - Regression-based attribution modeling  
  - ROI-style efficiency comparisons  
  - Time-series preprocessing and analysis  

### Intended Use
This dataset is suitable for:
- Marketing mix modeling (MMM)
- Regression-based attribution analysis
- Budget allocation and performance benchmarking
- Portfolio demonstration and interview discussion



Combine statistical rigor with business interpretability

Validate insights under correlated data

Translate model output into clear budget recommendations

## Assumptions & Limitations

- Assumes **linear relationships** between marketing spend and conversions
- Does not explicitly model **lagged (adstock) or saturation effects**
- Attribution results are **directional**, not causal
- Intended for **decision support**, not experimental or causal inference

---

## Extensibility

This project can be extended to include:

- **Adstock (lagged) effects** to capture delayed channel impact
- **Nonlinear response curves** to model diminishing returns
- **Time-series cross-validation** for more robust model evaluation
- **Automated dashboards** using Power BI or Tableau
- **Scenario-based budget optimization** and forecasting

---

## Why This Project Matters

This project reflects how **real marketing analytics teams** operate by:

- Combining **statistical rigor** with **business interpretability**
- Validating insights under **correlated and noisy data**
- Translating model output into **clear, actionable budget recommendations**

It is designed to be **portfolio-ready**, **interview-ready**, and aligned with real-world marketing and analytics workflows.


