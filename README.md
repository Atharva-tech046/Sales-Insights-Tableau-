<div align="center">

  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2Q0...../giphy.gif" width="100%" height="20" alt="divider"/>

  <h1>💼 Sales Insights Data Analysis</h1>

  <p>
    <a href="https://www.tableau.com/">
      <img src="https://img.shields.io/badge/TABLEAU-E97627?style=for-the-badge&logo=Tableau&logoColor=white" />
    </a>
    <a href="https://www.mysql.com/">
      <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
    </a>
    <a href="#">
      <img src="https://img.shields.io/badge/ETL-Data_Cleaning-green?style=for-the-badge" />
    </a>
  </p>

  <h3>
    <i>"Unlocking the hidden patterns in sales data to drive profitability."</i>
  </h3>

  <img src="https://media.giphy.com/media/LmqMkEnVqFpIXS6T7i/giphy.gif" width="600" alt="Dashboard Demo">

</div>

<br />

## 🧐 The Business Problem
A computer hardware manufacturer is facing challenges in tracking their sales in a dynamically growing market. The sales director is currently relying on verbal reports and excel sheets, which are leading to:
* ❌ Lack of visualization of real-time data.
* ❌ Difficulty in tracking regional performance.
* ❌ Inability to identify declining profit margins in specific markets.

**The Solution:** An interactive **Tableau Dashboard** powered by a **MySQL** database to visualize Revenue, Profit, and Sales Trends.

---

## 📂 Interactive Dashboard Views
*Click the arrows below to expand and view the analysis.*

<details>
<summary><b>💰 View 1: Revenue Analysis (Click to Expand)</b></summary>
<br>

> **Goal:** Track total volume and revenue trends.

![Revenue Screenshot]([INSERT LINK TO YOUR REVENUE DASHBOARD IMAGE])

* **Total Revenue:** ₹985M
* **Total Sales Qty:** 2.4M
* **Top Markets:** **Delhi NCR** and **Mumbai** dominate the revenue charts.
* **Trend Alert:** Observed a significant decline in sales volume in mid-2020.
</details>

<details>
<summary><b>📉 View 2: Profitability & Margins (Click to Expand)</b></summary>
<br>

> **Goal:** Identify where we are actually making money.

![Profit Screenshot]([INSERT LINK TO YOUR PROFIT DASHBOARD IMAGE])

* **Profit Margin King:** **Surat** has the highest profit margin (**4.86%**) despite lower volume.
* **Loss Maker:** **Kanpur** is currently operating at a negative margin (**-0.5%**).
* **Customer Insight:** **75.6%** of revenue comes from **Brick & Mortar** stores, indicating a slow adoption of E-Commerce (**24.4%**).
</details>

---

## ⚙️ Technical Architecture (Star Schema)
The data was modeled in MySQL using a Star Schema for optimized query performance.

```mermaid
graph TD;
    Transactions[FACT: Transactions] --> Customers[DIM: Customers];
    Transactions --> Products[DIM: Products];
    Transactions --> Markets[DIM: Markets];
    Transactions --> Date[DIM: Date];
