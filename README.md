---

# Simple Linear Regression – Marketing ROI Analysis

## Project Overview

This project analyzes a marketing dataset to evaluate the performance of various advertising channels**TV**, **Radio**, and **Social Media**against **Sales**. Using Python and `statsmodels`, an Ordinary Least Squares (OLS) regression model was built to quantify the exact impact of marketing spend, validate structural assumptions, and translate raw statistical outputs into actionable, ROI-driven business recommendations.

---

## Project Goal

* **Data Quality:** Clean and filter marketing dataset anomalies (e.g., removing outliers in Social Media spend).
* **Assumption Verification:** Verify Linearity, Normality, and Homoscedasticity using rigorous diagnostic plots.
* **Business Insights:** Deliver a clear, data-backed recommendation for marketing budget optimization to maximize Return on Investment (ROI).

---

## Environment Setup & Requirements

To run this project locally, ensure you have Python installed along with the following libraries:

```bash
pip install pandas numpy matplotlib seaborn statsmodels notebook

```

### Repository Structure

* `README.md`: Project summary, setup, and key analytical findings.
* `regression_analysis.ipynb`: Complete Jupyter Notebook with clean code, markdown explanations, and executed cells.
* `marketing_and_sales_data.csv`

---

## Key Findings & Analytical Workflow

### 1. Exploratory Data Analysis & Data Cleaning

* **Outlier Detection:** Box plots and histograms initially indicated structural anomalies and outliers within the **Social Media** spend data.
* **Treatment:** Outliers were investigated using mathematical quantiles and systematically filtered out to prevent skewing the regression line.
* **Channel Correlation:** Baseline correlation checks revealed that **TV Advertisement** spend shares a near-perfect linear relationship (Pearson Correlation $\approx 1.0$) with Sales, making it the primary feature of interest.

### 2. Model Diagnostics (Assumption Testing)

Post-modeling diagnostics were conducted on the residuals to ensure the OLS math holds valid:

* **Linearity & Homoscedasticity:** The *Residuals vs. Fitted Values* plot showed a random, straight-line distribution centered around zero with an even spread from left to right. This confirms high linearity and stable variance of errors (**Homoscedasticity**).
* **Normality:** * The *Normal Q-Q Plot* showed residual points tightly hugging the 45-degree reference line.
* The *Residual Histogram* presented a beautifully symmetric, bell-shaped curve centered squarely at 0.
* **Statistical Proof:** The model's `Prob(Omnibus)` value of **0.984** ($> 0.05$) mathematically confirms that the residuals are perfectly normally distributed.



### 3. Model Performance & Key Metrics

The OLS summary generated the following critical statistical markers:

* **Goodness of Fit ($R^2 = 0.999$):** The model explains **99.9%** of the observed variance in Sales, indicating an exceptionally strong fit.
* **Overall Model Significance (`Prob (F-statistic) = 0.00`):** The probability of these results occurring by chance is virtually zero, confirming the overall model is highly significant.
* **Feature Significance ($p$-values):**
* **TV ($p = 0.000$):** Highly statistically significant ($< 0.05$). It carries the most predictive weight with a coefficient of **3.5617** (every $\$1$ spent on TV yields roughly $\$3.56$ in sales).
* **Social Media ($p = 0.843$):** Statistically **insignificant** ($> 0.05$) with a notably higher standard error (**0.024**).


* **Multicorrelation Warning:** The *Condition Number* exceeded 30, signaling a redundant feature in the system. Given its high $p$-value and standard error, **Social Media** was deduced to be the redundant feature.

---

## Strategic Marketing Recommendations

>  **Core Decision:** **Aggressively shift and allocate remaining marketing budgets directly to the TV advertising channel.**

### Business Context for Stakeholders:

1. **Unmatched ROI:** The OLS model proves that **TV is the definitive driver of sales**. For every unit of budget invested in TV, sales scale up reliably by a factor of **3.56**.
2. **Eliminate Waste:** **Social Media performance is statistical noise** within this dataset. Its high $p$-value ($0.843$) implies that changes in Social Media spend have no reliable, predictable impact on net Sales. Continuing to fund it represents inefficient capital allocation.
3. **High Predictability:** Thanks to a $99.9\%$ $R$-squared metric and perfectly validated model diagnostics, marketing leadership can treat TV revenue forecasts with an exceptionally high degree of confidence.