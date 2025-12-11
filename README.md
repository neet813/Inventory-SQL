# Inventory Optimization & Stock Rebalancing Engine  
**SQL + Python | Multi-warehouse | £340k+ overstock reduction opportunity**  

      *Inventory_Optimization_V1.ipynb

### The real problem this solves

In my current role we track inventory across multiple distribution centers and supplier buffers.  
Every month the team spent days in Google Sheets manually figuring out:

- Which warehouse is overstocked  
- Which location will stock-out next week  
- How many units to transfer and where  

All of it was done manually in Google Sheets – slow, full of errors, and we still carried £300k–£500k of unnecessary holding cost every quarter.

I rebuilt the entire process from scratch using Python + SQLite so it now runs in seconds instead of days.

### What this repo does (end-to-end)
- Calculates target stock levels (weeks of cover) per warehouse  
- Identifies surpluses & shortages for every SKU  
- Generates exact transfer recommendations (from → to + units)  
- Quantifies overstock value in £  
- Exports clean CSVs ready for the warehouse team  

The data here is synthetic but 100 % representative of real company structure and volumes (anonymized for confidentiality).

### Business impact
- £340k+ reducible overstock identified  
- 18–25 % potential reduction in annual holding costs  
- Transfer plan that can be executed in one week  

### Tech stack
- Python (pandas)  
- Pure SQLite (easily portable to Snowflake/BigQuery/Redshift)  
- Zero setup – just click the Colab badge  

Drop your own inventory CSV and get recommendations instantly.

Always happy to talk about turning this into a production pipeline (Airflow + dbt + Streamlit).

---
Built by Navneet Kaur | Looking for Data Analyst / Supply Chain Analytics roles
