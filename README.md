# 🏠 California Housing Price Prediction
### Machine Learning Model Comparison (Day 6 Baseline)

This project explores the **California Housing Dataset** to predict median house values. I compared a simple **Linear Regression** model against a more complex **Random Forest Regressor** to determine which handles spatial and numerical data more effectively.

## 🚀 Final Results
| Model | $R^2$ Score (Accuracy) | Status |
| :--- | :--- | :--- |
| **Random Forest** | **79.00%** | 🏆 **Winner** |
| **Linear Regression** | **61.28%** | Baseline |

---

## 🛠️ Data Engineering & Cleaning
To improve model performance and fix visual errors in the charts, I performed the following steps in a unified data pipeline:

1.  **Unit Scaling:** Divided `median_house_value` by **1,000** to work with prices in $k$ (thousands), making the charts much easier to read.
2.  **Outlier Removal:** Filtered out the **"500k Wall"** (houses capped at exactly $500,000). This removed "fake" data points that were confusing the linear model's slope.
3.  **Missing Values:** Handled nulls in `total_bedrooms` using the **median** of the column to ensure no rows were wasted.
4.  **Categorical Encoding:** Applied **One-Hot Encoding** to the `ocean_proximity` column, turning text categories into binary (True/False) features.
5.  **Feature Engineering:** Created a `rooms_per_household` ratio to give the model better context on house density vs. total neighborhood size.

---

## 📈 Key Insights
* **The Linear Regression Struggle:** Before filtering, the LR model predicted impossible negative prices. Even after filtering, it struggled to capture the "curves" in the data, as seen in the scattered Actual vs. Predicted plot.
* **The Random Forest Advantage:** The Forest model was significantly better at identifying complex patterns (like the premium price of being "Near Ocean") without being told specifically how to calculate it.

---

## 📂 Project Structure
* `housing.csv`: The raw dataset.
* `analysis.ipynb`: The Jupyter Notebook containing the cleaning, training, and visualization code.
* `README.md`: This summary file.

---

### English & Russian Definitions
* **Model Evaluation:** The process of using different metrics to understand a machine learning model's performance.

* **Linearity:** The assumption that the relationship between two variables can be explained with a straight line.


