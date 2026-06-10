# AtliQ Bank: Target Market Identification & A/B Testing

## 📌 Project Overview
This project focuses on identifying an untapped target market for AtliQ Bank's new credit card and validating its success through statistical A/B testing. The analysis is broken down into two main phases:
1. **Phase 1: Target Market Identification (EDA & Data Cleaning)** - Querying customer data via MySQL, handling missing values, and identifying high-potential customer segments.
2. **Phase 2: A/B Testing** - Conducting hypothesis testing on a 2-month campaign to determine if the newly launched credit card significantly increased average transaction amounts.

## 🛠️ Tech Stack & Tools
* **Programming Language:** Python
* **Database:** MySQL
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Statsmodels, MySQL-Connector
* **Statistical Methods:** Two-Sample Z-Test, Effect Size & Sample Size Calculation

## 📊 Phase 1: Finding the Target Market
In this phase, customer data, credit profiles, and transaction logs were merged and analyzed. 
* **Data Cleaning:** Handled missing `annual_income` values by imputing the median income specific to each customer's `occupation`. Removed duplicate records and handled outliers in the transaction amounts using category-wise means.
* **Key Insights:** * Customers in the **18-25 age group** account for ~25% of the customer base.
  * Their average annual income is less than 50k, and they have limited credit history.
  * Despite currently low credit card usage and transaction amounts, their top spending categories (Electronics, Fashion & Apparel, Beauty & Personal Care) indicate a strong potential for a tailored credit product.

## 🧪 Phase 2: A/B Testing the New Credit Card
To target the 18-25 demographic, a new credit card was launched in a 2-month trial campaign. 
* **Experiment Design:** Using `statsmodels`, the required sample size was calculated for a minimum effect size of 0.4 standard deviations. 100 customers were selected for the test group, yielding a ~40% conversion rate (40 active users). A mutually exclusive control group of 40 users was tracked on existing cards.
* **Hypothesis Testing:** A one-tailed, two-sample Z-test was performed on the daily average transaction amounts.
  * **Null Hypothesis ($H_0$):** The new credit card does not increase the average transaction amount.
  * **Alternate Hypothesis ($H_1$):** The test group using the new credit card has a significantly larger average transaction amount than the control group.
* **Results:** The calculated p-value was less than the 0.05 significance level. We successfully rejected the null hypothesis, proving that the new credit card significantly increased user transaction amounts.

## 🚀 How to Run the Project
1. Clone the repository: `git clone https://github.com/rutikasalunke/AtliQ-Bank-Credit-Card-Analysis.git`
2. Install the required dependencies: `pip install -r requirements.txt`
3. Ensure your local MySQL server is running with the `e_master_card` database populated.
4. Open the Jupyter Notebooks in the `/notebooks` directory to view the analysis step-by-step.