# Inventory Optimization & Stock Rebalancing Engine  
**SQL + Python | Multi-warehouse | £340k+ overstock reduction opportunity**

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/neet813/Inventory-SQL/blob/main/Inventory_Optimization_V1.ipynb)

### The real problem this solves
In my current role we track inventory across multiple distribution centers and supplier buffers.  
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

### Tech stack
- Python (pandas, numpy)  
- Pure SQLite (easily portable to Snowflake/BigQuery/Redshift)  
- Zero setup – runs instantly in Colab  

Drop your own inventory CSV and get recommendations immediately.

Always happy to discuss productionizing this (Airflow + dbt + Streamlit dashboard).

—
Built by Navneet Kaur | Actively looking for Data Analyst & Supply Chain Analytics roles
