# 📊 Sales Insights Data Analysis Project

## Project Overview
This project is a data analysis dashboard built using **Tableau** and **SQL**. The goal is to provide actionable insights into sales performance, helping stakeholders make data-driven decisions. The dashboard analyzes sales trends, market performance, and revenue distribution.

## 🛠️ Tech Stack
* **Visualization:** Tableau Public / Desktop
* **Database:** MySQL (Relational Database)
* **Data Modeling:** Star Schema

## 📂 Data Structure & Modeling
The data is modeled using a **Star Schema** architecture to ensure efficient query performance in Tableau.

* **Fact Table:**
    * `transactions` (Contains transactional data like sales amount, quantity, order dates).
* **Dimension Tables:**
    * `customers` (Customer details).
    * `products` (Product codes and categories).
    * `markets` (Regional market information).
    * `date` (Time-period details).

## ⚙️ Data Transformation (ETL)
Based on the raw data analysis, several transformations were performed to ensure data accuracy:
1.  **Currency Normalization:** The raw sales data included transactions in multiple currencies (e.g., USD and INR). A custom calculation (`Normalized value`) was created to convert all currency into a distinct standard currency for accurate aggregation.
2.  **Data Cleaning:** Filtered out invalid sales values (e.g., negative or zero values) to prevent skewing the analysis.

## 📈 Key Insights (To be updated)
* *Revenue by Market*
* *Sales Quantity trends over time*
* *Top 5 Customers and Products*

## 🚀 How to Run
1.  Download the `.twb` or `.twbx` file from this repository.
2.  Open the file in **Tableau Desktop** or **Tableau Public**.
3.  Ensure the data connection to the MySQL database is active (or use the extracted data source if provided).

