# 💼 Sales Insights Data Analysis Project

![Tableau](https://img.shields.io/badge/TABLEAU-E97627?style=for-the-badge&logo=Tableau&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)

> **"Unlocking hidden patterns in sales data to drive profitability and operational efficiency."**

---

## 🧐 The Business Problem
A computer hardware manufacturer is facing challenges in tracking their sales in a dynamically growing market. The sales director is currently relying on verbal reports and Excel sheets, leading to:
* ❌ Lack of visualization of real-time data.
* ❌ Difficulty in tracking regional performance.
* ❌ Inability to identify declining profit margins in specific markets.

**The Solution:** An interactive **Tableau Dashboard** powered by a **MySQL** database to visualize Revenue, Profit, and Sales Trends.

---

## 📊 Interactive Dashboard Views
*Below are the insights generated from the project.*

### 1. Revenue Analysis Dashboard
> **Goal:** Track top-line performance and volume trends.

![Revenue Analysis]([INSERT YOUR REVENUE DASHBOARD IMAGE LINK HERE])

* **Total Revenue:** 985M
* **Total Sales Qty:** 2.4M
* **Key Insight:** **Delhi NCR** and **Mumbai** are the undisputed leaders in revenue generation.
* **Trend Alert:** Sales quantity shows a noticeable decline in 2020, warranting investigation into supply chain or market demand shifts.

### 2. Profit Analysis Dashboard
> **Goal:** Identify bottom-line health and profitability hotspots.

![Profit Analysis]([INSERT YOUR PROFIT DASHBOARD IMAGE LINK HERE])

* **Profit Margin King:** **Surat** yields the highest profit margin (**4.86%**) despite having lower sales volume than major cities.
* **Loss Warning:** **Kanpur** is currently operating at a loss with a negative margin of **-0.5%**.
* **Customer Segmentation:** **75.6%** of revenue is driven by **Brick & Mortar** stores, indicating a massive opportunity to expand the **E-Commerce** (24.4%) channel.

---

## ⚙️ Data Architecture (Star Schema)
The data is modeled in MySQL using a **Star Schema** to ensure optimal query performance for the dashboard.

* **Fact Table:** `transactions` (contains `sales_amount`, `order_date`, `currency`, `profit_margin`)
* **Dimension Tables:** `customers`, `products`, `markets`, `date`

---

## 🧹 SQL & Data Transformation (ETL)
Raw data often contains discrepancies. Key SQL transformations included:

1.  **Currency Normalization:** The dataset included transactions in both **USD** and **INR**. I used SQL to convert all USD transactions to INR using a static exchange rate calculation.
2.  **Data Cleaning:** Filtered out invalid records (e.g., negative sales amounts or market codes like 'Mark097' that did not exist in the master table).

```sql
-- Example: Cleaning and Normalizing Currency
SELECT 
    transactions.product_code, 
    customer.custmer_name, 
    CASE 
        WHEN transactions.currency = 'USD' THEN transactions.sales_amount * 75 
        ELSE transactions.sales_amount 
    END as normalized_sales_amount
FROM transactions
INNER JOIN customers ON transactions.customer_code = customers.customer_code;
