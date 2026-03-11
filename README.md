# Inventory Optimization & Stock Rebalancing Engine  
**SQL + Python | Multi-warehouse | £340k+ overstock reduction opportunity**

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/neet813/Inventory-SQL/blob/main/Inventory_Optimization_V1.ipynb)

### The real problem this solves
Inspired by inefficiencies I observed in warehouse operations — built on synthetic but representative data, anonymized for confidentiality.  
Every month the team spent days in Google Sheets manually figuring out:
- Which warehouse was overstocked
- Which location would stock-out next week
- How many units to transfer and where

It was slow, full of errors, and we still carried £300k–£500k of unnecessary holding cost every quarter.

I rebuilt the entire process from scratch using Python + SQLite.  
What used to take days now runs in **under 3 seconds**.

### What this repo does (end-to-end)
- Calculates target stock levels (weeks of cover) per warehouse  
- Identifies surpluses & shortages for every SKU  
- Generates exact transfer recommendations (from → to + units)  
- Quantifies overstock value in £  
- Exports clean CSVs ready for the warehouse team  

Data is synthetic but 100 % representative of real company volumes and structure (anonymized for confidentiality).

### Business impact
- £340k+ reducible overstock identified  
- 18–25 % potential reduction in annual holding costs  
- Transfer plan executable in one week  

Top Overstocked SKUs

![Inventory-SQL
](Overstock-table.png)

Overstock Value by Warehouse

![Inventory-SQL
](Overstock-per-Warehouse_Visualisation.png)

### 🧠 The Logic Behind the Engine (Developer’s Notes)

I built this tool to move from **Reactive** to **Strategic** inventory management. Here is why I made certain technical decisions:

* **Why "Weeks of Cover" (WoC)?**: I chose WoC over "Static Min/Max levels" because it is dynamic. If a product's sales double, the target stock automatically scales. This prevents stockouts during seasonal peaks.
* **Calculating the £340k Opportunity**: This isn't a guess. I calculated this using: `(Current Stock - Target Stock) * Unit Cost`. It represents "Trapped Capital" that could be used for other business investments.
* **SQL Portability**: I used **SQLite** so the project runs instantly in Colab, but the queries use **ANSI-SQL** (CTEs and Window Functions). This means the logic is ready to be copied into enterprise tools like **Snowflake, BigQuery, or Redshift**.
* **Synthetic but Scalable**: While the data is synthetic to protect confidentiality, the schema (Warehouse ID, SKU, Lead Time) is modeled exactly after real-world ERP exports.

### 🛠️ Tech Stack & Skills
* **SQL:** Advanced CTEs, Window Functions (`SUM OVER`), and Conditional Aggregation.
* **Python:** Pandas for data cleaning and Matplotlib/Seaborn for the "Overstock vs. Warehouse" visualizations.
* **Deployment:** Google Colab for an interactive, "Zero-Setup" user experience.

---
**Building a bridge between raw warehouse data and CFO-level financial insights.**

—
Built by Navneet Kaur | Actively looking for Data Analyst & Supply Chain Analytics roles
