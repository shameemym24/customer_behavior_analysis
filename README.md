

# 🛍️ Customer Shopping Behavior Data Analytics Project

## 🧭 Overview  
This project explores **customer shopping behavior** using end-to-end data analytics — from **data loading and cleaning in Python**, **SQL analysis**, to **Power BI dashboarding** and **presentation reporting with Gamma**.  

The goal was to uncover **what drives customer spending, loyalty, and product performance**, and to communicate insights clearly for **data-driven business decisions**.

---

## 📂 Dataset
**File:** `customer_shopping_behavior.csv`  
**Records:** ~3,900 rows × 10 columns  
**Source:** Simulated retail transaction data  

| Column | Description |
|---------|-------------|
| `Customer_ID` | Unique ID for each customer |
| `Age_Group` | Age bracket (e.g., 18–25, 26–35) |
| `Gender` | Male / Female |
| `Item_Purchased` | Product name |
| `Category` | Product category |
| `Purchase_Amount` | Amount spent per transaction |
| `Discount_Applied` | Yes / No |
| `Shipping_Type` | Standard / Express |
| `Subscription_Status` | Subscribed / Not Subscribed |
| `Review_Rating` | Customer satisfaction rating (1–5) |

---

## 🧰 Tools & Technologies

| Task | Tool |
|------|------|
| 🐍 Data Cleaning & EDA | **Python (Pandas, NumPy, Matplotlib, Seaborn)** |
| 💾 SQL Queries | **PostgreSQL / MySQL / SQL Server** |
| 📊 Dashboard | **Power BI** |
| 🧾 Reporting | **Gamma App** |
| 📝 Documentation | **Jupyter Notebook & GitHub** |

---

## 🔍 Project Workflow

### 1️⃣ Data Loading (Python)
Loaded and explored the dataset using **Pandas**.

```python
import pandas as pd
df = pd.read_csv("customer_shopping_behavior.csv")
df.info()
df.describe()
````

---

### 2️⃣ Exploratory Data Analysis (EDA)

Performed univariate and bivariate analysis to understand sales patterns, customer demographics, and purchasing behavior.

#### 🔹 Sample Visuals:

<div align="center">
  <img src="images/sales_by_category.png" width="600" alt="Sales by Category">
  <p><em>Figure 1: Sales distribution across product categories</em></p>
</div>

<div align="center">
  <img src="images/revenue_by_gender.png" width="600" alt="Revenue by Gender">
  <p><em>Figure 2: Revenue comparison between male and female customers</em></p>
</div>

---

### 3️⃣ Data Cleaning

* Removed duplicates and handled missing values.
* Standardized formats and encoded categorical fields.
* Created derived features for further analysis.

```python
df.drop_duplicates(inplace=True)
df['Discount_Applied'] = df['Discount_Applied'].map({'Yes': 1, 'No': 0})
```

---

### 4️⃣ SQL Analysis

The cleaned data was loaded into **PostgreSQL** for deeper querying and segmentation.

#### 🔹 Example Queries

```sql
-- Total revenue by gender
SELECT gender, SUM(purchase_amount) AS total_revenue
FROM customer
GROUP BY gender;

-- Top 5 products by average review rating
SELECT item_purchased, ROUND(AVG(review_rating),2) AS avg_rating
FROM customer
GROUP BY item_purchased
ORDER BY avg_rating DESC
LIMIT 5;
```

📄 Full SQL Script → [`customer_behavior_sql_queries.sql`](./customer_behavior_sql_queries.sql)

#### 🔹 SQL Insights:

* Subscribed customers generated **32% higher revenue** on average.
* Express shipping correlated with **higher purchase values**.
* Discounts boosted sales volume but reduced **average purchase amount**.

---

### 5️⃣ Dashboard (Power BI)

Created an **interactive Power BI dashboard** to visualize:

* Sales trends by category, age, and gender
* Customer segmentation by loyalty and subscription
* Product performance and review scores

<div align="center">
  <img src="images/powerbi_dashboard_main.png" width="720" alt="Customer Shopping Behavior Power BI Dashboard">
  <p><em>Figure 3: Power BI Dashboard Overview</em></p>
</div>

#### 💡 Key Metrics:

| Metric                      | Value             | Insight                          |
| --------------------------- | ----------------- | -------------------------------- |
| 💰 **Total Revenue**        | $2.1M             | Driven by Electronics & Clothing |
| 👥 **Top Customer Segment** | Age 26–35         | Accounts for 42% of purchases    |
| 💳 **Avg Purchase Value**   | $540              | Higher for subscribed customers  |
| 🚚 **Top Shipping Type**    | Express           | 18% higher average spend         |
| 🛒 **Discount Impact**      | +25% Sales Volume | but -8% Avg Spend                |

---

### 6️⃣ Reporting (Gamma)

Created a **Gamma presentation** to summarize the project workflow and insights for stakeholders.
The presentation included:

* Objectives and approach
* Key findings and visuals
* Power BI dashboard highlights
* Business recommendations

📎 Deliverable: `customer_behavior_report.gamma` (or export to PDF)

---

## 📈 Results & Business Insights

✅ **Female customers** spent more overall, but males placed slightly more orders.
✅ **Subscribed users** consistently outperformed non-subscribers in both revenue and repeat purchases.
✅ **Discounts** increased conversion but reduced average profit per transaction.
✅ **Express shipping** was linked to higher-value purchases and better satisfaction.

<div align="center">
  <img src="images/revenue_trends.png" width="650" alt="Revenue Trends">
  <p><em>Figure 4: Monthly revenue trend visualization</em></p>
</div>

---

## ⚙️ How to Run the Project

1️⃣ **Clone this repository**

```bash
git clone https://github.com/shameemym24/customer-shopping-behavior.git
```

2️⃣ **Install dependencies**

```bash
pip install pandas numpy matplotlib seaborn sqlalchemy psycopg2
```

3️⃣ **Run Jupyter Notebook**

```bash
jupyter notebook Customer_Shopping_Behavior_Analysis.ipynb
```

4️⃣ **Execute SQL Queries**

* Load cleaned dataset into PostgreSQL/MySQL/SQL Server.
* Run queries from `customer_behavior_sql_queries.sql`.

5️⃣ **Open Power BI Dashboard**

* Load `customer_behavior_dashboard.pbix` to explore visuals interactively.

6️⃣ **Review Gamma Report**

* Open `customer_behavior_report.gamma` or export the final presentation as PDF.

---

## 🧾 Deliverables

| File                                        | Description                        |
| ------------------------------------------- | ---------------------------------- |
| `Customer_Shopping_Behavior_Analysis.ipynb` | Python Notebook for EDA & cleaning |
| `customer_behavior_sql_queries.sql`         | SQL script for analysis            |
| `customer_behavior_dashboard.pbix`          | Power BI dashboard                 |
| `customer_shopping_behavior.csv`            | Source dataset                     |
| `customer_behavior_report.gamma`            | Final business report              |

---

## 👩‍💻 About the Author
Hey, I'm Shameem Yousuf -- Data Analyst skilled in SQL, Python, Power BI, and Excel with hands-on experience in data cleaning, visualization, and reporting.

📍 Dubai, UAE

📧 [shameem.yousuf47@gmail.com](mailto:shameem.yousuf47@gmail.com)

🔗 [LinkedIn](https://www.linkedin.com/in/shameem90)
---

⭐ *“Turning data into insights, and insights into action.”*


