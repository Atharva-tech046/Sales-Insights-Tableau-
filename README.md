<div align="center">
  <h1 align="center">🚀 Sales Insights Data Analysis</h1>

  <h3>
    <a href="#-live-dashboard">View Dashboard</a>
    <span> | </span>
    <a href="#-sql-analysis">View SQL Queries</a>
  </h3>

  <p align="center">
    <img src="https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=Tableau&logoColor=white" />
    <img src="https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white" />
    <img src="https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=Power%20BI&logoColor=black" />
  </p>
  
  <br />
  
  <img src="https://media.giphy.com/media/LmqMkEnVqFpIXS6T7i/giphy.gif" width="600" alt="Data Analysis Animation">
  
  <p align="center">
    <i>An end-to-end data analysis project to unlock sales insights using <b>SQL</b> and <b>Tableau</b>.</i>
  </p>
</div>

---

## 📖 Table of Contents
- [Project Overview](#-project-overview)
- [Interactive Dashboards](#-interactive-dashboards)
- [SQL Analysis & Data Model](#-sql-analysis--data-model)
- [Key Insights](#-key-insights)
- [Tech Stack](#-tech-stack)

---

## 🧐 Project Overview
This project tackles the challenge of tracking sales performance in a rapidly growing hardware market. By analyzing transactional data, the dashboard helps stakeholders track key performance indicators (KPIs) like **Revenue**, **Sales Quantity**, and **Profit Margins** across different regions and time periods.

> **Goal:** To move beyond static reports and provide an interactive tool for data-driven decision making.

---

## 📊 Interactive Dashboards

<details>
<summary><b>📈 Dashboard 1: Revenue Analysis (Click to Expand)</b></summary>
<br>

> **Focus:** Top-line performance and volume tracking.

![Revenue Dashboard]([INSERT LINK TO YOUR REVENUE DASHBOARD IMAGE HERE])

* **Total Revenue:** 985M
* **Sales Quantity:** 2.4M
* **Key Insight:** **Delhi NCR** and **Mumbai** are the leading revenue contributors, but revenue has seen a declining trend in 2020.
</details>

<details>
<summary><b>💰 Dashboard 2: Profit Analysis (Click to Expand)</b></summary>
<br>

> **Focus:** Bottom-line health and profitability.

![Profit Dashboard]([INSERT LINK TO YOUR PROFIT DASHBOARD IMAGE HERE])

* **Total Profit:** 24.7M
* **Market Profitability:** **Surat** leads with a **4.86%** profit margin, while **Kanpur** is operating at a loss (**-0.5%**).
* **Customer Segmentation:** **75.6%** of sales come from Brick & Mortar stores.
</details>

---

## ⚙️ SQL Analysis & Data Model

We used **MySQL** for the initial data exploration and ETL (Extract, Transform, Load). The data is structured in a **Star Schema**.

### 🌟 Star Schema Structure
* **Fact Table:** `transactions` (Sales amounts, dates, currency)
* **Dimensions:** `customers`, `products`, `markets`, `date`

<details>
<summary><b>🔍 Click to see Example SQL Queries</b></summary>

```sql
-- 1. Calculating Total Revenue for 2020
SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date ON transactions.order_date = date.date 
WHERE date.year = 2020;

-- 2. Finding Markets with Negative Profit
SELECT market_code, SUM(profit_margin) as total_profit
FROM transactions
GROUP BY market_code
HAVING total_profit < 0;
