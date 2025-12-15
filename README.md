# 🚖 NYC Taxi Trip Analysis & Fraud Detection

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/Library-Pandas-150458)
![Scikit-Learn](https://img.shields.io/badge/ML-Scikit--Learn-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 👤 Author
**Adar Zilbershtein** Data Analyst | Information Systems Student  
[<img src="https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin">](https://www.linkedin.com/in/adar-zilbershtein/)

---

## 📌 Project Overview
This project performs a comprehensive analysis of **NYC Yellow Taxi trip data (2023)**, processing over **1.6 million validated records**. The primary goal was to uncover operational patterns, analyze tipping behaviors across payment methods, and implement a rule-based algorithm to detect fraudulent anomalies.

Using **Python** and **Pandas**, raw data was cleaned and transformed into actionable insights, helping to identify potential revenue leakage and service efficiency gaps.

## 💡 Key Business Insights

### 🚨 Fraud & Anomaly Detection
A custom `fraud_score` logic was implemented to flag suspicious rides. Out of the analyzed dataset:
* **14,898 rides** were flagged as "High Risk" (Score ≥ 1).
* **Key Fraud Indicators Identified:**
    * **Money Laundering Patterns:** Rides with short distances (<1 mile) but excessive fares (>$50).
    * **Price Gouging:** Identified ~0.5% of rides with a "Fare per Mile" exceeding $50.
    * **Pricing Anomalies:** Using Linear Regression, I detected significant deviations (residuals) where the actual price did not match the expected distance/time model.

### 💰 Payment & Tipping Culture
Analysis revealed a critical disparity in driver compensation based on payment type:
* **Credit Card:** **95.6%** of transactions included a tip (Avg tip: ~$4.46).
* **Cash:** **0.0%** recorded tips. This suggests that cash tips are systematically underreported or non-existent in the digital record.
* **Weekend Dynamics:** Surprisingly, average total fares are slightly lower on weekends ($29.21) compared to weekdays ($29.97).

### ✈️ Airport Economics
* **JFK Airport:** High-value route with an average fare of **$92.67** (Avg distance: 18.2 miles).
* **Newark Airport:** Significantly more expensive (**$126.67**) for a similar distance due to cross-state surcharges.

---

## 🛠️ Technical Methodology

### 1. Data Cleaning & Preprocessing
* **Dataset:** Processed a heavy CSV file (`2023_Taxi_5M.csv`).
* **Filtering:** Removed realistic outliers (negative fares, distances > 100 miles, 0 passenger counts).
* **Type Casting:** Optimized memory usage by converting datetime strings to datetime objects.

### 2. Feature Engineering
Created complex metrics to drive the analysis:
* `fraud_score`: A composite metric summing up 5 different suspicion flags.
* `fare_per_mile`: Efficiency metric to spot outliers.
* `trip_duration_min`: Derived from pickup/dropoff timestamps.
* `residual`: The difference between actual fare and the predicted fare (Calculated using `scikit-learn` Linear Regression).

### 3. Exploratory Data Analysis (EDA)
* Visualized rush hour demand curves.
* compared tipping rates across different `RateCodeID` types.
* Analyzed weekend vs. weekday profitability.

---

## 💻 Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-learn (Linear Regression for anomaly detection)

## 🚀 How to Run
1.  Clone the repository.
2.  Install dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  Run the Jupyter Notebook:
    ```bash
    jupyter notebook TaxiAnalysis.ipynb
    ```

---
*Feel free to reach out via [LinkedIn](https://www.linkedin.com/in/adar-zilbershtein/) for any questions regarding this project.*
