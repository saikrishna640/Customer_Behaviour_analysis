# 🛒 Customer_Shopping_Behavior_Analysis
This project shows the customer behavior analysis made through Python, SQL. 

### 📄 Project Overview
This project analyzes a retail dataset of **3,900 customer transactions** to identify revenue drivers, customer retention patterns, and product performance. The goal was to move beyond simple reporting and use **SQL-based segmentation** to answer critical business questions, such as "Do subscribers actually spend more?" and "Which age group is most valuable?".

### 🛠️ Tools & Technologies
* **Python (Pandas):** Data cleaning, missing value imputation, and feature engineering.
* **MySQL:** Advanced data analysis using Window Functions, CTEs, and Aggregations.
* **Statistics:** Group-wise median imputation for handling missing data.

---

### 🧹 Data Cleaning & Preparation (Python)
Before analysis, the raw dataset required processing to ensure accuracy:
* **Handling Missing Values:** Identified 37 missing entries in `Review Rating`. Implemented a **Group-wise Imputation** strategy, filling missing values with the median rating of the specific *Product Category* (e.g., a missing rating for a 'Blouse' was filled with the median rating of 'Clothing').
* **Feature Engineering:** Created an `age_group` column (Teen, Young Adult, Adult, Senior) to allow for demographic segmentation.
* **Standardization:** Renamed columns to `snake_case` for consistent SQL querying.

---

### 🔍 Key SQL Insights
The analysis revealed several counter-intuitive findings that contradict standard business assumptions:

#### 1. Young Adults are the Top Spenders
Contrary to the expectation that older demographics have more disposable income, the **Young Adult** group generated the highest total revenue (**$62,143**), followed by Middle-Aged ($59,197).

#### 2. The "Subscription Paradox"
Surprisingly, **Subscribers spend slightly less on average ($59.49)** compared to Non-Subscribers ($59.86). This indicates that the current loyalty program is not effectively incentivizing higher basket sizes.

#### 3. Express Shipping Correlates with Higher Value
Customers who opt for **Express Shipping** have a higher Average Order Value (**$60.47**) compared to Standard shippers ($58.46), suggesting that convenience-focused shoppers are less price-sensitive.

#### 4. The "Volume Drivers" (Top Products)
Using SQL Window Functions (`ROW_NUMBER()`), the following items were identified as the top 3 best-sellers in their categories:
* **Accessories:** Jewelry, Sunglasses, Belts
* **Clothing:** Blouses, Pants, Shirts
* **Footwear:** Sandals, Shoes, Sneakers
* **Outerwear:** Jackets, Coats

---

### 💡 Business Recommendations
Based on the data, I propose the following strategic actions:

1.  **Pivot Marketing to Young Adults:** Shift ad spend to target the "Young Adult" demographic with trend-focused campaigns, as they are the primary revenue engine.
2.  **Revamp the Subscription Model:** The loyalty program is currently underperforming. Introduce tiered benefits (e.g., "Free Express Shipping" for subscribers) to raise the average spend of this cohort.
3.  **Prioritize "Class A" Inventory:** Ensure 100% stock availability for **Jewelry, Blouses, and Sandals**, as these specific SKUs drive the bulk of transaction volume.
4.  **Upsell Express Shipping:** Prominently feature Express Shipping at checkout, as users selecting this option tend to purchase higher-value baskets.

---

### 💻 How to Run This Project
1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/yourusername/shopping-behavior-analysis.git](https://github.com/yourusername/shopping-behavior-analysis.git)
    ```
2.  **Load Data:**
    * Run the Python script `data_cleaning.py` to process the raw CSV.
    * Import the cleaned CSV into your MySQL database.
3.  **Run SQL Analysis:**
    * Execute the queries in `analysis_queries.sql` to generate the insights.

---
*Author: [Your Name]*
